<script>
import ContentBlock from "./ContentBlock.vue"
import ContentBlockDesktop from "./ContentBlockDesktop.vue"

export default {
    components: {
        ContentBlock,
        ContentBlockDesktop,
    },
    data() {
        return {
            cardsData: [
                {
                    id: 1,
                    title: "Roccella Jonica, la Lampedusa che l'Italia ignora",
                    category: "MIGRANTI",
                    backgroundImage: "/download-1.jpg",
                    useFlexColumn: false,
                    author: "Alessandro Puglia",
                    authorImage: "/alessandro-puglia.jpg",
                    date: "29 Giugno 2022",
                },
                {
                    id: 2,
                    title: "Il collasso dei ghiacciai negli scatti del fotografo ambientale Fabiano Ventura",
                    category: "ALLARMI",
                    video: "/collasso-ghiacciai.png",
                    backgroundImageDesktopOnly: "/collasso-ghiacciai.png",
                    useFlexColumn: true,
                    author: "Gilda Sciortino",
                    authorImage: "/gilda-sciortino.jpg",
                    date: "14 Luglio 2022",
                },
                {
                    id: 3,
                    title: "Gli startupper? Li trovi al bistrot. Così il DumBo incuba relazioni",
                    category: "ESPERIMENTI",
                    backgroundImageDesktopOnly: "/startupper.jpg",
                    useFlexColumn: true,
                    author: "Diletta grella",
                    authorImage: "/diletta-grella.jpg",
                    date: "14 Luglio 2022",
                    audio: true,
                },
                {
                    id: 4,
                    title: "Nelle città italiane tutti in piazza per e con Kiev",
                    category: "UCRAINA",
                    backgroundImageDesktopOnly: "/ucraina.png",
                    useFlexColumn: true,
                    author: "Anna Spena",
                    authorImage: "/anna-spena.jpg",
                    date: "14 Luglio 2022",
                },
                {
                    id: 5,
                    title: "Il tuo supporto è fondamentale",
                    subtitle: `Dai il tuo contributo <i class="fa-solid fa-arrow-right"></i>`,
                },
                {
                    id: 6,
                    title: "'Qui Odessa', fotografie, progetti e solidarietà",
                    category: "PROGETTO ARCA",
                    useFlexColumn: true,
                    author: "Redazione",
                    authorImage: "/logo-vita.png",
                    date: "14 Luglio 2022",
                },
                {
                    id: 7,
                    title: "Storie fra ragazzi permeate di violenza. A Napoli 12enne sfregiata da 17enne",
                    category: "ADOLESCENTI",
                    backgroundImageDesktopOnly: "/17enne.jpg",
                    useFlexColumn: true,
                    author: "Luca Cereda",
                    authorImage: "/luca-cereda.jpg",
                    date: "13 Luglio 2022",
                },
                {
                    id: 8,
                    title: "'Co-agitiamo', Tiggiano una cooperativa di comunità contro lo spopolamento",
                    category: "ECONOMIA CIVILE",
                    backgroundImageDesktopOnly: "/cooperativa.jpg",
                    useFlexColumn: true,
                    author: "Emiliano Moccia",
                    authorImage: "/emiliano-moccia.jpg",
                    date: "12 Luglio 2022",
                },
                {
                    id: 9,
                    title: "Troppi abusi nello sport minorile, il governo interviene",
                    category: "SPORT",
                    backgroundImageDesktopOnly: "/abusi-sport.jpg",
                    useFlexColumn: true,
                    author: "Diletta Grella",
                    authorImage: "/diletta-grella.jpg",
                    date: "14 Luglio 2022",
                    audio: true,
                },
                {
                    id: 10,
                    title: "Donne e nuove generazioni: con loro riparte l'Italia",
                    category: "SOCIETÀ",
                    backgroundImageDesktopOnly: "/donne-nuove-generazioni.jpg",
                    image: "/donne-nuove-generazioni.jpg",
                    useFlexColumn: false,
                    author: "Anna Spena",
                    authorImage: "/anna-spena.jpg",
                    date: "14 Luglio 2022",
                    interview_with: "Mariangela Cassano",
                },
                {
                    id: 11,
                    title: "Essere troppo seri non è cosa molto seria",
                    subtitle: "[ Detto Africano ]",
                    backgroundImageDesktopOnly: "/detto-africano.png",
                },
                {
                    id: 12,
                    title: "Il Blog",
                },
                {
                    id: 13,
                    title: "La Kasbah mazarese nella quale si gusta la cultura araba",
                    category: "IMPRESA SOCIALE",
                    backgroundImageDesktopOnly: "/kasbah.png",
                    video: "/kasbah.png",
                    useFlexColumn: true,
                    author: "Giovanni Gavardi",
                    authorImage: "/giovanni-gavardi.jpg",
                    date: "14 Luglio 2022",
                },
                {
                    id: 14,
                    title: "Sostenibilità sociale: accordo tra Dynamo Academy e Acsi",
                    sponsored: true,
                    useFlexColumn: false,
                    author: "Dynamo Academy",
                    authorImage: "/dynamo-academy.png",
                },
                {
                    id: 15,
                    title: "Uccisa ad Haiti suor Luisa, era l'angelo dei bambini",
                    category: "PERSONE",
                    backgroundImageDesktopOnly: "/morte-haiti.jpg",
                    useFlexColumn: false,
                    author: "Lucia Capuzzi",
                    authorImage: "/lucia-capuzzi.jpg",
                    date: "1 Luglio 2022",
                },
                {
                    id: 16,
                    title: "Il fundraising in rotta verso Giardini-Naxos",
                    category: "NETWORKING",
                    useFlexColumn: false,
                    author: "Redazione",
                    authorImage: "/logo-vita.png",
                    date: "1 Luglio 2022",
                },
                {
                    id: 17,
                    title: "Lisa, il modello Croce Rossa per l'inclusione lavorativa",
                    category: "SOICIETÀ CIVILE",
                    backgroundImageDesktopOnly: "/Lisa.jpg",
                    useFlexColumn: false,
                    author: "Francesca Palazzo",
                    authorImage: "/francesca-palazzo.png",
                    date: "1 Luglio 2022",
                },
            ],
            cardsOnlyDesktop: [
                {
                    id: 0,
                    title: "Gli anziani del Sicomoro spopolano su TikTok",
                    category: "INNOVAZIONE",
                    backgroundImage: "/anziani.jpg",
                    author: "Luigi Alfonso",
                    authorImage: "/luigi-alfonso.jpg",
                    date: "1 Luglio 2022",
                },
                {
                    id: 1,
                    title: "'Emergenza sordi': quando un'app ti salva la vita",
                    category: "DISABILITÀ",
                    backgroundImage: "/emergenza-sordi.jpg",
                    author: "Sara Bellingeri",
                    authorImage: "/sara-bellingeri.jpg",
                    date: "1 Luglio 2022",
                },
                {
                    id: 2,
                    title: "Diego, il fruttivendolo che ha scelto la cooperazione sociale",
                    category: "TRAIETTORIE",
                    backgroundImage: "/fruttivendolo.jpg",
                    author: "Giampaolo Cerri",
                    authorImage: "/giampaolo-cerri.jpg",
                    date: "1 Luglio 2022",
                },
                {
                    id: 3,
                    title: "Pedalare 'Sicily Coast to Coast' per essere più inclusivi",
                    category: "SOCIALE",
                    backgroundImage: "/pedalare.jpg",
                    author: "Giovanni Gamba",
                    authorImage: "/giovanni-gamba.jpg",
                    date: "1 Luglio 2022",
                },
                {
                    id: 4,
                    title: "Leopoli, andata + ritorno",
                    category: "UCRAINA",
                    backgroundImage: "/leopoli.png",
                    author: "Gilda Sciortino",
                    authorImage: "/gilda-sciortino.jpg",
                    date: "14 Luglio 2022",
                },
            ],
            isMobile: false,
        }
    },
    mounted() {
        this.checkMobile()
        window.addEventListener("resize", this.checkMobile)
    },
    beforeDestroy() {
        window.removeEventListener("resize", this.checkMobile)
    },
    methods: {
        checkMobile() {
            this.isMobile = window.innerWidth <= 991
        },
        getGridClasses(index) {
            if (window.innerWidth <= 991) {
                return "col-100" // Mobile, tutti gli elementi occupano 100%
            }

            switch (index) {
                case 0:
                    return "col-100"
                case 4:
                    return "col-100"
                case 5:
                case 6:
                case 7:
                case 8:
                    return "col-33"
                case 9:
                    return "col-66"
                case 10:
                case 12:
                case 11:
                    return "col-100"
                case 13:
                case 14:
                case 15:
                case 16:
                    return "col-25"
            }
        },
    },
}
</script>

<template>
    <div class="display-mobile">
        <span class="mountain-icon"><img src="/public/mountain.png" alt="" /></span>
    </div>
    <div class="flex-container">
        <!-- Prima card (index 0) -->
        <ContentBlock
            v-if="cardsData[0]"
            :index="0"
            :id="cardsData[0].id"
            :class="getGridClasses(0)"
            :title="cardsData[0].title"
            :subtitle="cardsData[0].subtitle"
            :category="cardsData[0].category"
            :backgroundImage="cardsData[0].backgroundImage"
            :backgroundImageDesktopOnly="cardsData[0].backgroundImageDesktopOnly"
            :image="cardsData[0].image"
            :video="cardsData[0].video"
            :author="cardsData[0].author"
            :authorImage="cardsData[0].authorImage"
            :date="cardsData[0].date"
            :audio="cardsData[0].audio"
            :useFlexColumn="cardsData[0].useFlexColumn"
            :sponsor="cardsData[0].sponsored"
            :interview_with="cardsData[0].interview_with" />

        <!-- Riga personalizzata per gli indici 1, 2 e 3 -->
        <div class="custom-row">
            <ContentBlock
                class="col-100 col-lg-66"
                v-if="cardsData[1]"
                :index="1"
                :id="cardsData[1].id"
                :title="cardsData[1].title"
                :subtitle="cardsData[1].subtitle"
                :category="cardsData[1].category"
                :backgroundImage="cardsData[1].backgroundImage"
                :backgroundImageDesktopOnly="cardsData[1].backgroundImageDesktopOnly"
                :image="cardsData[1].image"
                :video="cardsData[1].video"
                :author="cardsData[1].author"
                :authorImage="cardsData[1].authorImage"
                :date="cardsData[1].date"
                :useFlexColumn="cardsData[2].useFlexColumn"
                :audio="cardsData[1].audio"
                :sponsor="cardsData[1].sponsored"
                :interview_with="cardsData[1].interview_with" />

            <div class="col-100 col-lg-33">
                <ContentBlock
                    class="col-100"
                    v-if="cardsData[2]"
                    :index="2"
                    :id="cardsData[2].id"
                    :title="cardsData[2].title"
                    :subtitle="cardsData[2].subtitle"
                    :category="cardsData[2].category"
                    :backgroundImage="cardsData[2].backgroundImage"
                    :backgroundImageDesktopOnly="cardsData[2].backgroundImageDesktopOnly"
                    :image="cardsData[2].image"
                    :video="cardsData[2].video"
                    :author="cardsData[2].author"
                    :authorImage="cardsData[2].authorImage"
                    :date="cardsData[2].date"
                    :audio="cardsData[2].audio"
                    :useFlexColumn="cardsData[2].useFlexColumn"
                    :sponsor="cardsData[2].sponsored"
                    :interview_with="cardsData[2].interview_with" />

                <ContentBlock
                    class="col-100"
                    v-if="cardsData[3]"
                    :index="3"
                    :id="cardsData[3].id"
                    :title="cardsData[3].title"
                    :subtitle="cardsData[3].subtitle"
                    :category="cardsData[3].category"
                    :backgroundImage="cardsData[3].backgroundImage"
                    :backgroundImageDesktopOnly="cardsData[3].backgroundImageDesktopOnly"
                    :image="cardsData[3].image"
                    :video="cardsData[3].video"
                    :author="cardsData[3].author"
                    :authorImage="cardsData[3].authorImage"
                    :date="cardsData[3].date"
                    :useFlexColumn="cardsData[3].useFlexColumn"
                    :audio="cardsData[3].audio"
                    :sponsor="cardsData[3].sponsored"
                    :interview_with="cardsData[3].interview_with" />
            </div>
        </div>

        <!-- Resto delle card (da index 4 in poi) -->
        <ContentBlock
            v-for="(item, index) in cardsData.slice(4)"
            :key="index + 4"
            :index="index"
            :id="item.id"
            :class="getGridClasses(index + 4)"
            :title="item.title"
            :subtitle="item.subtitle"
            :category="item.category"
            :backgroundImage="item.backgroundImage"
            :backgroundImageDesktopOnly="item.backgroundImageDesktopOnly"
            :image="item.image"
            :video="item.video"
            :author="item.author"
            :authorImage="item.authorImage"
            :date="item.date"
            :useFlexColumn="item.useFlexColumn"
            :audio="item.audio"
            :sponsor="item.sponsored"
            :interview_with="item.interview_with" />
    </div>
    <div class="display-desktop flex-container">
        <!-- Prima colonna -->
        <div class="column column-1">
            <ContentBlockDesktop
                v-for="(item, index) in cardsOnlyDesktop.slice(0, 4)"
                :key="item.id"
                :id="item.id"
                :title="item.title"
                :category="item.category"
                :backgroundImage="item.backgroundImage"
                :author="item.author"
                :authorImage="item.authorImage"
                :date="item.date" />
        </div>

        <!-- Seconda colonna -->
        <div class="column column-2">
            <ContentBlockDesktop
                v-if="cardsOnlyDesktop[4]"
                :key="cardsOnlyDesktop[4].id"
                :id="cardsOnlyDesktop[4].id"
                :title="cardsOnlyDesktop[4].title"
                :category="cardsOnlyDesktop[4].category"
                :backgroundImage="cardsOnlyDesktop[4].backgroundImage"
                :author="cardsOnlyDesktop[4].author"
                :authorImage="cardsOnlyDesktop[4].authorImage"
                :date="cardsOnlyDesktop[4].date"
                class="full-height-card" />
        </div>
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
    z-index: 3;
    right: 16px;
    bottom: 40px;
    background-color: white;
}

.mountain-icon img {
    height: 17px;
    width: 20px;
}

@media (min-width: 991px) {
    .flex-container {
        display: flex;
        flex-wrap: wrap;
        width: 100%;
    }

    .custom-row {
        display: flex;
        flex-wrap: nowrap;
        width: 100%;
    }

    [class*="col-"] {
        display: flex;
        flex-direction: column;
    }

    .col-100 {
        width: 100%;
    }

    .col-66,
    .col-lg-66 {
        width: calc(100% / 3 * 2);
    }

    .col-33,
    .col-lg-33 {
        width: calc(100% / 3);
        display: flex;
        flex-direction: column;
    }

    .col-lg-33 > .col-100 {
        flex: 1;
        min-height: 0;
    }

    .column {
        flex: 1;
    }

    .column-1 {
        display: flex;
        flex-direction: column;
    }

    .column-2 {
        display: flex;
    }

    .full-height-card {
        flex: 1;
    }
}
</style>
