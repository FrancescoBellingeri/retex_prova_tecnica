<script>
import ContentBlock from "./ContentBlock.vue"

export default {
    components: {
        ContentBlock,
    },
    data() {
        return {
            cardsData: [
                {
                    title: "Roccella Jonica, la Lampedusa che l'Italia ignora",
                    category: "MIGRANTI",
                    backgroundImage: "/public/download-1.jpg",
                    author: "Alessandro Puglia",
                    authorImage: "/public/alessandro-puglia.jpg",
                    date: "29 Giugno 2022",
                },
                {
                    title: "Il collasso dei ghiacciai negli scatti del fotografo ambientale Fabiano Ventura",
                    category: "ALLARMI",
                    /* backgroundImage: "/public/collasso-ghiacciai.jpg", */
                    author: "Gilda Sciortino",
                    authorImage: "/public/gilda-sciortino.jpg",
                    date: "14 Luglio 2022",
                },
                {
                    title: "Gli startupper? Li trovi al bistrot. Così il DumBo incuba relazioni",
                    category: "ESPERIMENTI",
                    /* backgroundImage: "/public/startupper.jpg", */
                    author: "Diletta grella",
                    authorImage: "/public/diletta-grella.jpg",
                    date: "14 Luglio 2022",
                },
                {
                    title: "Nelle città italiane tutti in piazza per e con Kiev",
                    category: "UCRAINA",
                    /* backgroundImage: "/public/startupper.jpg", */
                    author: "Anna Spena",
                    authorImage: "/public/anna-spena.jpg",
                    date: "14 Luglio 2022",
                },
                {
                    title: "“Qui Odessa”, fotografie, progetti e solidarietà",
                    category: "PROGETTO ARCA",
                    /* backgroundImage: "/public/startupper.jpg", */
                    author: "Redazione",
                    authorImage: "/public/logo-vita.png",
                    date: "14 Luglio 2022",
                },
                {
                    title: "Storie fra ragazzi permeate di violenza. A Napoli 12enne sfregiata da 17enne",
                    category: "ADOLESCENTI",
                    /* backgroundImage: "/public/startupper.jpg", */
                    author: "Luca Cereda",
                    authorImage: "/public/luca-cereda.jpg",
                    date: "13 Luglio 2022",
                },
                {
                    title: "“Co-agitiamo”, Tiggiano una cooperativa di comunità contro lo spopolamento",
                    category: "ECONOMIA CIVILE",
                    /* backgroundImage: "/public/startupper.jpg", */
                    author: "Emiliano Moccia",
                    authorImage: "/public/emiliano-moccia.jpg",
                    date: "12 Luglio 2022",
                },
                {
                    title: "Troppi abusi nello sport minorile, il governo interviene",
                    category: "SPORT",
                    /* backgroundImage: "/public/startupper.jpg", */
                    author: "Diletta Grella",
                    authorImage: "/public/diletta-grella.jpg",
                    date: "14 Luglio 2022",
                },
                {
                    title: "Donne e nuove generazioni: con loro riparte l’Italia",
                    category: "SOCIETÀ",
                    /* backgroundImage: "/public/startupper.jpg", */
                    author: "Anna Spena",
                    authorImage: "/public/anna-spena.jpg",
                    date: "14 Luglio 2022",
                },
                {
                    title: "Essere troppo seri non è cosa molto seria",
                    subtitle: "[ Detto Africano ]",
                },
                {},

                // Aggiungi altre card qui
            ],
        }
    },
}
</script>

<template>
    <ContentBlock
        v-for="(item, index) in cardsData"
        :key="index"
        :title="item.title"
        :category="item.category"
        :backgroundImage="item.backgroundImage"
        :author="item.author"
        :authorImage="item.authorImage"
        :date="item.date" />
</template>

<style scoped></style>
