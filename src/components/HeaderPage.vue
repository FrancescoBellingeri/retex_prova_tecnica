<script>
import Filter from "./Filter.vue"

export default {
    components: {
        Filter,
    },
    data() {
        return {
            navbarItems: [
                { text: "Tutti i temi", href: "#", active: true },
                { text: "Ambiente", href: "#", active: false },
                { text: "Economia", href: "#", active: false },
                { text: "Mondo", href: "#", active: false },
                { text: "Non Profit", href: "#", active: false },
                { text: "Politica", href: "#", active: false },
                { text: "Società", href: "#", active: false },
                { text: "Welfare", href: "#", active: false },
            ],
            filterAreOpen: false,
        }
    },
    methods: {
        openFilter() {
            this.filterAreOpen = !this.filterAreOpen
        },
    },
}
</script>

<template>
    <div class="layout-container">
        <header class="header-fixed">
            <div class="container">
                <div class="row">
                    <div class="col-100 h-44 display-mobile"></div>
                    <div class="col-100 h-40">
                        <div class="h-100">
                            <button class="btn h-100 bg-white">Contribuisci</button>
                            <button class="btn h-100 bg-white">Abbonati</button>
                        </div>
                        <button class="btn h-100 bg-white display-desktop">
                            <i class="fa-regular fa-user"></i> Accedi
                        </button>
                    </div>
                    <div class="col-100 h-52 d-flex">
                        <button
                            v-if="!filterAreOpen"
                            class="bars text-red h-100 bg-white"
                            @click="openFilter()">
                            <i class="fa-solid fa-bars"></i>
                        </button>
                        <button
                            v-if="filterAreOpen"
                            class="bars text-red h-100 bg-white"
                            @click="openFilter()">
                            <i class="fa-solid fa-xmark"></i>
                        </button>
                        <input class="h-100" type="text" />
                        <button v-if="!filterAreOpen" class="search text-red h-100 bg-white">
                            <i class="fa-solid fa-magnifying-glass"></i>
                        </button>
                    </div>
                    <div class="col-100 h-52 padding-x display-desktop bg-white">
                        <div class="h-100 d-flex justify-content-between align-items-center">
                            <ul>
                                <li
                                    v-for="(item, index) in navbarItems"
                                    :key="index"
                                    :class="
                                        item.active
                                            ? 'border-bottom-red'
                                            : 'border-bottom-transparent'
                                    ">
                                    {{ item.text }}
                                </li>
                            </ul>
                            <div class="h-100 d-flex align-items-center">
                                Aa
                                <span class="mountain-icon"
                                    ><img src="/mountain.png" alt=""
                                /></span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </header>

        <main class="main-content">
            <div class="col-100 padding bg-light-green">
                <h1 class="d-flex margin-bottom-10">
                    {{ navbarItems[0].text }}
                    <span class="display-mobile"><i class="fa-solid fa-angle-down"></i></span>
                </h1>
                <ul>
                    <li v-for="(item, index) in navbarItems.slice(1)" :key="index" class="label">
                        {{ item.text }}
                    </li>
                </ul>
            </div>
        </main>
    </div>
    <Filter v-if="filterAreOpen" />
</template>

<style scoped>
.header-fixed {
    position: fixed;
    top: 0;
    width: 100%;
    background-color: white;
    z-index: 10;
}

.main-content {
    padding-top: 136px;
}

.h-44 {
    height: 44px;
}

.h-40 {
    height: 40px;
}

.h-52 {
    height: 52px;
}

.btn {
    width: 50%;
    border-width: 1px 0;
    border-style: solid;
    border-color: black;
}

.btn:first-child {
    border-right: 1px solid black;
}

.h-52 input {
    flex-grow: 1;
}

.bars {
    border-left: 0;
    border-top: 0;
    border-right: 1px solid black;
    border-bottom: 1px solid black;
    padding: 0 20px;
    cursor: pointer;
}

.search {
    border-left: 1px solid black;
    border-top: 0;
    border-right: 0;
    border-bottom: 1px solid black;
    padding: 0 20px;
}

input {
    border-top: 0;
    border-left: 0;
    border-right: 0;
    border-bottom: 1px solid black;
}

.fa-angle-down {
    vertical-align: middle;
    font-size: 16px;
}

ul {
    list-style-type: none;
    display: flex;
    flex-wrap: wrap;
}

li {
    margin: 4px;
    font-size: 10px;
}

span {
    margin-left: 5px;
}

.col-100.bg-light-green {
    padding-top: 24px;
    padding-bottom: 24px;
}

@media (min-width: 991px) {
    .main-content {
        padding-top: 144px;
    }

    .header-fixed {
        height: 144px;
    }
    .col-100.h-40 {
        display: flex;
        justify-content: space-between;
        padding: 0 40px;
    }

    .btn {
        width: auto;
        border: 0;
    }

    .btn:first-child {
        border-right: 0;
        margin-right: 10px;
    }

    .bars,
    .search,
    input {
        border-top: 1px solid black;
    }

    .mountain-icon {
        border: 1px solid black;
        border-radius: 4px;
        box-shadow: -2px 2px 0px 0px black;
        width: 30px;
        height: 30px;
        display: flex;
        align-items: center;
        justify-content: center;
        margin-left: 8px;
    }

    .mountain-icon img {
        height: 17px;
        width: 20px;
    }

    ul {
        list-style-type: none;
        display: flex;
        height: 100%;
    }

    li {
        margin: 0px 4px 0px 0px;
        height: 100%;
        display: flex;
        align-items: center;
        font-size: 18px;
        font-weight: bold;
    }

    .border-bottom-red {
        border-bottom: 5px solid #e63036;
    }

    .border-bottom-transparent {
        border-bottom: 5px solid white;
    }

    .col-100.bg-light-green {
        display: flex;
        justify-content: space-between;
        border-top: 1px solid black;
    }

    .col-100.bg-light-green ul {
        height: auto;
    }

    .col-100.bg-light-green li {
        font-size: 10px;
    }

    .col-100.bg-light-green ul li:nth-child(1) {
        background-color: #e2f1e8;
    }

    .col-100.bg-light-green ul li:nth-child(3) {
        background-color: #f1dada;
    }

    .col-100.bg-light-green ul li:nth-child(5) {
        background-color: #f1f1e2;
    }

    .col-100.bg-light-green ul li:last-child {
        margin: 0;
    }

    .padding-x {
        padding: 0 40px;
    }
}
</style>
