<template>
    <BlogSection v-if="title === 'Il Blog'" />
    <div
        v-if="title !== 'Il Blog'"
        class="card padding"
        :style="{
            backgroundImage: backgroundImage ? `url(${backgroundImage})` : '',
            backgroundColor:
                author === 'Redazione'
                    ? '#e63036'
                    : title === 'Il tuo supporto è fondamentale'
                    ? '#faf1de'
                    : title === 'Essere troppo seri non è cosa molto seria'
                    ? '#f4f4f4'
                    : '',
        }">
        <div class="content">
            <div v-if="video" class="video-container">
                <span class="play-video"><i class="fa-solid fa-play"></i></span>
                <img :src="video" alt="" class="video" />
            </div>
            <img v-if="image" :src="image" alt="immagine" class="main-img" />
            <span v-if="category" class="label bg-white">{{ category }}</span>
            <span v-if="sponsor" class="text-red sponsor"
                ><i class="fa-solid fa-bullhorn"></i> SPONSORED</span
            >
            <div class="player-container" v-if="audio">
                <button class="play-button"></button>
                <div ref="waveformContainer" class="waveform">
                    <div
                        v-for="(height, index) in barHeights"
                        :key="index"
                        class="bar"
                        :style="{ height: `${height}%` }"></div>
                </div>
                <span class="timestamp">-03:34</span>
            </div>

            <h3
                :class="{
                    'text-white': backgroundImage || author === 'Redazione',
                    'font-large': backgroundImage || subtitle,
                    'font-medium': image || video,
                    'font-small': !(backgroundImage || image || video),
                }">
                {{ title }}
            </h3>
            <h5 v-if="subtitle" class="font-small">{{ subtitle }}</h5>
            <div
                v-if="authorImage && author"
                :class="backgroundImage || author === 'Redazione' ? 'text-white' : ''"
                class="d-flex align-items-center">
                <img :src="authorImage" :alt="`immagine ${author}`" class="author-img" />
                <div>
                    <div v-if="author" class="author">Di {{ author }}</div>
                    <div v-if="date" class="date">{{ date }}</div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import BlogSection from "./BlogSection.vue"

export default {
    props: {
        title: String,
        subtitle: String,
        category: String,
        backgroundImage: String,
        image: String,
        video: String,
        author: String,
        authorImage: String,
        date: String,
        sponsor: Boolean,
        audio: String,
    },
    components: {
        BlogSection,
    },
    data() {
        return {
            barHeights: [],
            barWidth: 3, // Width of each bar including gap
        }
    },
    methods: {
        generateBars() {
            if (!this.$refs.waveformContainer) return

            const containerWidth = this.$refs.waveformContainer.offsetWidth
            const numberOfBars = Math.floor(containerWidth / this.barWidth)

            this.barHeights = Array.from({ length: numberOfBars }, () => Math.random() * 100)
        },
    },
    mounted() {
        this.generateBars()
        window.addEventListener("resize", this.generateBars)
    },
    beforeUnmount() {
        window.removeEventListener("resize", this.generateBars)
    },
}
</script>

<style scoped>
.card {
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    padding-top: 40px;
    padding-bottom: 24px;
    border-top: 1px solid black;
}

span {
    font-size: 10px;
    font-weight: 700;
}

.font-small {
    font-size: 14px;
    font-weight: 700;
    line-height: 24px;
    margin: 16px 0;
}

.font-medium {
    font-size: 20px;
    font-weight: 700;
    line-height: 30px;
    margin: 16px 0;
}

.font-large {
    font-size: 24px;
    font-weight: 700;
    line-height: 32px;
    margin: 16px 0;
}

.author-img {
    width: 32px;
    height: 32px;
    border-radius: 100%;
    margin-right: 16px;
}

.author {
    font-weight: 400;
    font-size: 14px;
    line-height: 24px;
}

.date {
    font-weight: 400;
    font-size: 10px;
    line-height: 16px;
}

.label {
    padding: 4px 12px;
}

.main-img {
    width: 100%;
    aspect-ratio: 16 / 16;
    object-fit: cover;
    object-position: center;
    border: 1px solid black;
    margin-bottom: 16px;
}

.video-container {
    position: relative;
    margin-bottom: 16px;
}

.play-video {
    position: absolute;
    bottom: 4px;
    right: 0;
    border: 1px solid black;
    background-color: white;
    width: 40px;
    height: 40px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 16px;
}

.video {
    width: 100%;
    aspect-ratio: 16 / 9;
    object-fit: cover;
    object-position: center;
    border: 1px solid black;
}

.player-container {
    display: flex;
    align-items: center;
    gap: 12px;
    background: white;
    padding: 8px 12px;
    border: 1px solid #e2e2e2;
    border-radius: 8px;
    width: 100%;
    margin-top: 16px;
}

.play-button {
    flex-shrink: 0;
    width: 0;
    height: 0;
    border-top: 8px solid transparent;
    border-bottom: 8px solid transparent;
    border-left: 12px solid #000;
    background: transparent;
    padding: 0;
    margin: 0;
    cursor: pointer;
}

.waveform {
    display: flex;
    align-items: center;
    gap: 2px;
    height: 32px;
    flex-grow: 1;
    overflow: hidden;
}

.bar {
    flex-grow: 1;
    background: #000;
    opacity: 0.7;
}

.timestamp {
    flex-shrink: 0;
    color: #000;
    font-size: 14px;
    min-width: 45px;
}
</style>
