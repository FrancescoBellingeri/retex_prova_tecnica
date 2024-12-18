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
                    video: "/public/collasso-ghiacciai.png",
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
                    title: "Il tuo supporto è fondamentale",
                    subtitle: "Dai il tuo contributo &#8594;",
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
                    image: "/public/donne-nuove-generazioni.jpg",
                    author: "Anna Spena",
                    authorImage: "/public/anna-spena.jpg",
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
                    video: "/public/kasbah.png",
                    author: "Giovanni Gavardi",
                    authorImage: "/public/giovanni-gavardi.jpg",
                    date: "14 Luglio 2022",
                },
                {
                    title: "Sostenibilità sociale: accordo tra Dynamo Academy e Acsi",
                    sponsored: true,
                    /* backgroundImage: "/public/startupper.jpg", */
                    author: "Dynamo Academy",
                    authorImage: "/public/dynamo-academy.png",
                },
                {
                    title: "Uccisa ad Haiti suor Luisa, era l'angelo dei bambini",
                    category: "PERSONE",
                    /* backgroundImage: "/public/startupper.jpg", */
                    author: "Lucia Capuzzi",
                    authorImage: "/public/lucia-capuzzi.jpg",
                    date: "1 Luglio 2022",
                },
                {
                    title: "Il fundraising in rotta verso Giardini-Naxos",
                    category: "NETWORKING",
                    /* backgroundImage: "/public/startupper.jpg", */
                    author: "Redazione",
                    authorImage: "/public/logo-vita.png",
                    date: "1 Luglio 2022",
                },
                {
                    title: "Lisa, il modello Croce Rossa per l'inclusione lavorativa",
                    category: "SOICIETÀ CIVILE",
                    /* backgroundImage: "/public/startupper.jpg", */
                    author: "Francesca Palazzo",
                    authorImage: "/public/francesca-palazzo.png",
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
        :category="item.category"
        :backgroundImage="item.backgroundImage"
        :image="item.image"
        :video="item.video"
        :author="item.author"
        :authorImage="item.authorImage"
        :date="item.date" />
</template>

<style scoped></style>
