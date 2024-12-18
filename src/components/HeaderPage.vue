<script>
export default {
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
        }
    },
}
</script>

<template>
    <header>
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
                    <button class="bars text-red h-100 bg-white">
                        <i class="fa-solid fa-bars"></i>
                    </button>
                    <input class="h-100" type="text" />
                    <button class="search text-red h-100 bg-white">
                        <i class="fa-solid fa-magnifying-glass"></i>
                    </button>
                </div>
                <div class="padding col-100 h-52 display-desktop">
                    <div class="h-100 d-flex justify-content-between align-items-center">
                        <ul>
                            <li
                                v-for="(item, index) in navbarItems"
                                :key="index"
                                :class="
                                    item.active ? 'border-bottom-red' : 'border-bottom-transparent'
                                ">
                                {{ item.text }}
                            </li>
                        </ul>
                        <div class="h-100 d-flex align-items-center">
                            Aa <img src="/public/Toggle.png" alt="toggle" />
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </header>
</template>

<style scoped>
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

@media (min-width: 991px) {
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

    img {
        height: 30px;
        width: auto;
        margin-left: 5px;
    }

    ul {
        list-style-type: none;
        display: flex;
        height: 100%;
    }

    li {
        margin: 0px 10px 0px 0px;
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
}
</style>
