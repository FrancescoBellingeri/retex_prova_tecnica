<script>
export default {}
</script>
<template>
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

            <h3
                :class="{
                    'text-white': backgroundImage || author === 'Redazione',
                    'font-large': backgroundImage || subtitle,
                    'font-medium': image || video,
                    'font-small': !(backgroundImage || image || video),
                }">
                {{ title }}
            </h3>
            <h5 v-if="subtitle" class="font-small" v-html="subtitle"></h5>

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
<style scoped></style>
