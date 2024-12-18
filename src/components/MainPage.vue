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
                    backgroundImage: "/download-1.jpg",
                    author: "Alessandro Puglia",
                    authorImage: "/alessandro-puglia.jpg",
                    date: "29 Giugno 2022",
                },
                {
                    title: "Il collasso dei ghiacciai negli scatti del fotografo ambientale Fabiano Ventura",
                    category: "ALLARMI",
                    video: "/collasso-ghiacciai.png",
                    author: "Gilda Sciortino",
                    authorImage: "/gilda-sciortino.jpg",
                    date: "14 Luglio 2022",
                },
                {
                    title: "Gli startupper? Li trovi al bistrot. Così il DumBo incuba relazioni",
                    category: "ESPERIMENTI",
                    /* backgroundImage: "/startupper.jpg", */
                    author: "Diletta grella",
                    authorImage: "/diletta-grella.jpg",
                    date: "14 Luglio 2022",
                    audio: true,
                },
                {
                    title: "Nelle città italiane tutti in piazza per e con Kiev",
                    category: "UCRAINA",
                    /* backgroundImage: "/startupper.jpg", */
                    author: "Anna Spena",
                    authorImage: "/anna-spena.jpg",
                    date: "14 Luglio 2022",
                },
                {
                    title: "Il tuo supporto è fondamentale",
                    subtitle: `Dai il tuo contributo <i class="fa-solid fa-arrow-right"></i>`,
                },
                {
                    title: "“Qui Odessa”, fotografie, progetti e solidarietà",
                    category: "PROGETTO ARCA",
                    /* backgroundImage: "/startupper.jpg", */
                    author: "Redazione",
                    authorImage: "/logo-vita.png",
                    date: "14 Luglio 2022",
                },
                {
                    title: "Storie fra ragazzi permeate di violenza. A Napoli 12enne sfregiata da 17enne",
                    category: "ADOLESCENTI",
                    /* backgroundImage: "/startupper.jpg", */
                    author: "Luca Cereda",
                    authorImage: "/luca-cereda.jpg",
                    date: "13 Luglio 2022",
                },
                {
                    title: "“Co-agitiamo”, Tiggiano una cooperativa di comunità contro lo spopolamento",
                    category: "ECONOMIA CIVILE",
                    /* backgroundImage: "/startupper.jpg", */
                    author: "Emiliano Moccia",
                    authorImage: "/emiliano-moccia.jpg",
                    date: "12 Luglio 2022",
                },
                {
                    title: "Troppi abusi nello sport minorile, il governo interviene",
                    category: "SPORT",
                    /* backgroundImage: "/startupper.jpg", */
                    author: "Diletta Grella",
                    authorImage: "/diletta-grella.jpg",
                    date: "14 Luglio 2022",
                    audio: true,
                },
                {
                    title: "Donne e nuove generazioni: con loro riparte l’Italia",
                    category: "SOCIETÀ",
                    image: "/donne-nuove-generazioni.jpg",
                    author: "Anna Spena",
                    authorImage: "/anna-spena.jpg",
                    date: "14 Luglio 2022",
                },
                {
                    title: "Essere troppo seri non è cosa molto seria",
                    subtitle: "[ Detto Africano ]",
                },
                {
                    title: "Il Blog",
                },
                {
                    title: "La Kasbah mazarese nella quale si gusta la cultura araba",
                    category: "IMPRESA SOCIALE",
                    video: "/kasbah.png",
                    author: "Giovanni Gavardi",
                    authorImage: "/giovanni-gavardi.jpg",
                    date: "14 Luglio 2022",
                },
                {
                    title: "Sostenibilità sociale: accordo tra Dynamo Academy e Acsi",
                    sponsored: true,
                    /* backgroundImage: "/startupper.jpg", */
                    author: "Dynamo Academy",
                    authorImage: "/dynamo-academy.png",
                },
                {
                    title: "Uccisa ad Haiti suor Luisa, era l'angelo dei bambini",
                    category: "PERSONE",
                    /* backgroundImage: "/startupper.jpg", */
                    author: "Lucia Capuzzi",
                    authorImage: "/lucia-capuzzi.jpg",
                    date: "1 Luglio 2022",
                },
                {
                    title: "Il fundraising in rotta verso Giardini-Naxos",
                    category: "NETWORKING",
                    /* backgroundImage: "/startupper.jpg", */
                    author: "Redazione",
                    authorImage: "/logo-vita.png",
                    date: "1 Luglio 2022",
                },
                {
                    title: "Lisa, il modello Croce Rossa per l'inclusione lavorativa",
                    category: "SOICIETÀ CIVILE",
                    /* backgroundImage: "/startupper.jpg", */
                    author: "Francesca Palazzo",
                    authorImage: "/francesca-palazzo.png",
                    date: "1 Luglio 2022",
                },

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
        :subtitle="item.subtitle"
        :category="item.category"
        :backgroundImage="item.backgroundImage"
        :image="item.image"
        :video="item.video"
        :author="item.author"
        :authorImage="item.authorImage"
        :date="item.date"
        :audio="item.audio"
        :sponsor="item.sponsored" />
    <div class="display-mobile">
        <span class="mountain-icon"><img src="/mountain.png" alt="" /></span>
    </div>
</template>

<style scoped>
.mountain-icon {
    border: 1px solid black;
    border-radius: 4px;
    box-shadow: -2px 2px 0px 0px black;
    width: 54px;
    height: 54px;
    display: flex;
    align-items: center;
    justify-content: center;
    position: fixed;
    right: 16px;
    bottom: 40px;
    background-color: white;
}

.mountain-icon img {
    height: 17px;
    width: 20px;
}
</style>
