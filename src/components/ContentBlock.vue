<script>
import BlogSection from "./BlogSection.vue"

export default {
    props: {
        id: Number,
        title: String,
        subtitle: String,
        category: String,
        backgroundImage: String,
        backgroundImageDesktopOnly: String,
        image: String,
        video: String,
        author: String,
        authorImage: String,
        date: String,
        sponsor: Boolean,
        audio: Boolean,
        customClass: String,
        useFlexColumn: Boolean,
        index: Number,
        interview_with: String,
    },
    components: {
        BlogSection,
    },
    data() {
        return {
            barHeights: [],
            barWidth: 3,
            isDesktop: window.innerWidth >= 991,
        }
    },
    methods: {
        generateBars() {
            if (!this.$refs.waveformContainer) return

            const containerWidth = this.$refs.waveformContainer.offsetWidth
            const numberOfBars = Math.floor(containerWidth / this.barWidth)

            this.barHeights = Array.from({ length: numberOfBars }, () => Math.random() * 100)
        },
        getBackgroundImage() {
            if (this.isDesktop) {
                return this.backgroundImageDesktopOnly || this.backgroundImage
            }

            if (!this.isDesktop && this.backgroundImage) {
                return this.backgroundImage
            }

            return null
        },
        handleResize() {
            this.isDesktop = window.innerWidth >= 991
        },
        moveContent() {
            if (this.isDesktop && this.id === 10) {
                return "half-width-right"
            }

            if (this.isDesktop && this.id === 13) {
                return "center-y half-width-right"
            }

            if (this.isDesktop && (this.id === 1 || this.id === 2)) {
                return "moved-to-bottom"
            }

            return null
        },
    },
    mounted() {
        this.generateBars()
        window.addEventListener("resize", this.generateBars)
        window.addEventListener("resize", this.handleResize)
    },
    beforeUnmount() {
        window.removeEventListener("resize", this.generateBars)
        window.removeEventListener("resize", this.handleResize)
    },
}
</script>

<template>
    <div :class="customClass">
        <BlogSection v-if="title === 'Il Blog'" />
        <div
            v-if="title !== 'Il Blog'"
            class="card padding overlay-container"
            :class="id === 1 || id === 13 ? 'h-500' : ''"
            :style="{
                backgroundImage: getBackgroundImage() ? `url(${getBackgroundImage()})` : '',
                backgroundColor:
                    author === 'Redazione'
                        ? '#e63036'
                        : title === 'Il tuo supporto è fondamentale'
                        ? '#faf1de'
                        : title === 'Essere troppo seri non è cosa molto seria'
                        ? '#f4f4f4'
                        : '',
            }">
            <div
                class="overlay"
                v-if="
                    (!isDesktop && backgroundImage) ||
                    (isDesktop && (backgroundImageDesktopOnly || backgroundImage))
                "></div>
            <div class="content" :class="moveContent()">
                <div v-if="video && !isDesktop" class="video-container">
                    <span class="play-video"><i class="fa-solid fa-play"></i></span>
                    <img :src="video" alt="" class="video" />
                </div>
                <div v-if="image && !isDesktop" class="container-main-img">
                    <img :src="image" alt="immagine" class="main-img" />
                    <div v-if="interview_with" class="interview">
                        <div>Intervista a</div>
                        <h3>{{ interview_with }}</h3>
                    </div>
                </div>
                <span
                    v-if="category"
                    class="label bg-white"
                    :style="{
                        backgroundColor:
                            category === 'ALLARMI'
                                ? '#e2f1e8'
                                : category === 'ESPERIMENTI' ||
                                  category === 'ADOLESCENTI' ||
                                  category === 'SPORT' ||
                                  category === 'SOCIETÀ' ||
                                  category === 'SOCIETÀ CIVILE'
                                ? '#e2f0f1'
                                : category === 'UCRAINA'
                                ? '#f1dada'
                                : category === 'ECONOMIA CIVILE'
                                ? '#f0e2f1'
                                : category === 'IMPRESA SOCIALE'
                                ? '#f5e6e0'
                                : category === 'PERSONE'
                                ? '#f1dada'
                                : '',
                    }"
                    >{{ category }}</span
                >
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

                <div
                    :class="{
                        'd-flex justify-content-between align-items-center': isDesktop && id === 5,
                    }">
                    <h3
                        :class="{
                            'text-white':
                                backgroundImage ||
                                (isDesktop && backgroundImageDesktopOnly) ||
                                author === 'Redazione',
                            'font-large': backgroundImage || subtitle,
                            'font-medium': image || video,
                            'font-small': !(backgroundImage || image || video),
                        }">
                        {{ title }}
                    </h3>
                    <h5
                        v-if="subtitle"
                        :class="id === 11 && isDesktop ? 'text-white' : ''"
                        class="subtitle"
                        v-html="subtitle"></h5>
                </div>

                <div
                    v-if="authorImage && author"
                    :class="{
                        'flex-column-desktop': useFlexColumn,
                        'text-white':
                            backgroundImage ||
                            (isDesktop && backgroundImageDesktopOnly) ||
                            author === 'Redazione',
                    }"
                    class="d-flex align-items-center align-items-start-lg justify-content-between-lg">
                    <img :src="authorImage" :alt="`immagine ${author}`" class="author-img" />
                    <div>
                        <div v-if="author" class="author">Di {{ author }}</div>
                        <div v-if="date" class="date">{{ date }}</div>
                    </div>
                </div>
                <div
                    v-if="isDesktop && authorImage && author && id !== 1"
                    :class="{
                        'text-white':
                            backgroundImage ||
                            (isDesktop && backgroundImageDesktopOnly) ||
                            author === 'Redazione',
                    }">
                    <i class="fa-solid fa-arrow-right"></i>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
.h-500 {
    height: 500px !important;
    min-height: 500px !important;
}

.card {
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    display: flex;
    flex: 1;
    position: relative;
    flex-direction: column;
    padding-top: 40px;
    padding-bottom: 24px;
    border-top: 1px solid black;
}

.content {
    position: relative;
    z-index: 2;
}

.overlay-container {
    position: relative;
    overflow: hidden;
}

.overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.4);
    z-index: 1;
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

.subtitle {
    font-size: 14px;
    font-weight: 600;
    line-height: 15px;
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

.container-main-img {
    position: relative;
}

.interview {
    position: absolute;
    bottom: 64px;
    left: 64px;
    color: white;
    font-size: 32px;
    line-height: 32px;
}

.interview h3 {
    margin-top: 16px;
}

@media (min-width: 991px) {
    .font-large {
        font-size: 40px;
        font-weight: 700;
        line-height: 54px;
        margin: 16px 0;
    }

    .font-medium {
        font-size: 32px;
        font-weight: 700;
        line-height: 46px;
        margin: 16px 0;
    }

    .font-small {
        font-size: 24px;
        font-weight: 700;
        line-height: 32px;
        margin: 16px 0;
    }

    .subtitle {
        font-weight: 700;
    }

    .flex-column-desktop {
        flex-direction: column;
    }

    .align-items-start-lg {
        align-items: flex-start;
    }

    .flex-column-desktop .author {
        margin-top: 16px;
    }

    .fa-arrow-right {
        margin-top: 16px;
    }

    .half-width-right {
        width: 50%;
        margin-left: auto;
        margin-right: 0;
    }

    .center-y {
        position: absolute;
        top: 50%;
        transform: translateY(-50%);
        right: 40px;
    }

    .moved-to-bottom {
        position: absolute;
        bottom: 16px;
    }
}
</style>
