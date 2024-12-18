<template>
    <div
        class="card padding"
        :style="{
            backgroundImage: backgroundImage ? `url(${backgroundImage})` : '',
            backgroundColor: author === 'Redazione' ? '#e63036' : '',
        }">
        <div class="content">
            <div v-if="video" class="video-container">
                <span class="play-video"><i class="fa-solid fa-play"></i></span>
                <img :src="video" alt="" class="video" />
            </div>
            <img v-if="image" :src="image" alt="immagine" class="main-img" />
            <span v-if="category" class="label bg-white">{{ category }}</span>
            <h3 :class="backgroundImage || author === 'Redazione' ? 'text-white' : ''">
                {{ title }}
            </h3>
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
            <!-- Mostra il player audio se audioUrl è presente -->
            <audio v-if="audioUrl" controls :src="audioUrl"></audio>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        title: String,
        category: String,
        backgroundImage: String,
        image: String,
        video: String,
        author: String,
        authorImage: String,
        date: String,
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
}

h3 {
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
</style>
