<template>
    <div
        class="card padding"
        :style="backgroundImage ? { backgroundImage: `url(${backgroundImage})` } : {}">
        <div class="content">
            <span v-if="category" class="label bg-white">{{ category }}</span>
            <h3 :class="backgroundImage ? 'text-white' : ''">{{ title }}</h3>
            <div
                v-if="authorImage && author && date"
                :class="backgroundImage ? 'text-white' : ''"
                class="d-flex align-items-center">
                <img :src="authorImage" :alt="`immagine ${author}`" class="author-img" />
                <div>
                    <div v-if="author" class="author">Di {{ author }}</div>
                    <div class="date">{{ date }}</div>
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
</style>
