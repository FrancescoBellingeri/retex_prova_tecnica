<script>
export default {
    props: {
        id: Number,
        title: String,
        category: String,
        backgroundImage: String,
        author: String,
        authorImage: String,
        date: String,
    },
}
</script>

<template>
    <div
        class="card padding overlay-container"
        :style="{
            backgroundImage: `url(${backgroundImage})`,
        }">
        <div class="overlay"></div>
        <div
            class="content"
            :class="{
                'moved-to-bottom': id === 4,
            }">
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

            <h3
                class="text-white"
                :class="{
                    'font-medium': id === 0 || id === 1 || id === 2 || id === 3,
                    'font-large': id === 4,
                }">
                {{ title }}
            </h3>

            <div
                v-if="authorImage && author"
                :class="{ 'flex-column-desktop align-items-start-lg': id === 4 }"
                class="d-flex align-items-center text-white">
                <img :src="authorImage" :alt="`immagine ${author}`" class="author-img" />
                <div>
                    <div v-if="author" :class="{ 'mt-16': id === 4 }" class="author">
                        Di {{ author }}
                    </div>
                    <div v-if="date" class="date">{{ date }}</div>
                </div>
            </div>
            <div v-if="id === 4" class="text-white" :class="{ 'mt-16': id === 4 }">
                <i class="fa-solid fa-arrow-right"></i>
            </div>
            <div v-if="id !== 4" class="text-white pos-abs-arrow">
                <i class="fa-solid fa-arrow-right"></i>
            </div>
        </div>
    </div>
</template>

<style scoped>
.card {
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    display: flex;
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

.font-medium {
    font-size: 18px;
    font-weight: 700;
    line-height: 28px;
    margin: 16px 0;
}

.font-large {
    font-size: 32px;
    font-weight: 700;
    line-height: 46px;
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

.flex-column-desktop {
    flex-direction: column;
}

.align-items-start-lg {
    align-items: flex-start;
}

.mt-16 {
    margin-top: 16px;
}

.moved-to-bottom {
    position: absolute;
    bottom: 16px;
}

.pos-abs-arrow {
    position: absolute;
    bottom: 50%;
    right: 16px;
}
</style>
