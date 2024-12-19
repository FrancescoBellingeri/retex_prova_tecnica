<script>
export default {
    data() {
        return {
            categories: [
                { title: "Articoli", description: "Trend, dati e novità del Terzo Settore." },
                {
                    title: "Storie",
                    description: "Letture ed approfondimenti dei fenomeni complessi.",
                },
                {
                    title: "Interviste",
                    description: "Racconti reali di persone ed organizzazioni.",
                },
                {
                    title: "Opinioni",
                    description: "Riflessioni e confronti dei nostri opinionisti.",
                },
                {
                    title: "Podcast",
                    description: "Un luogo per dare voce ai protagonisti della sostenibilità.",
                },
                {
                    title: "Bookazine",
                    description: "Una rivista da leggere e un libro da conservare.",
                },
            ],
            footerItems: [
                "Chi siamo",
                "Comitato editoriale",
                "Servizi",
                "Agenda / Eventi",
                "Mappa dell'attivismo",
                "Inchieste crowdfunding",
            ],
        }
    },
}
</script>

<template>
    <div class="container">
        <div class="grid">
            <div class="category" v-for="(category, index) in categories" :key="index">
                <h2>{{ category.title }}</h2>
                <p>{{ category.description }}</p>
            </div>
        </div>
        <div class="footer">
            <div class="footer-item" v-for="(item, index) in footerItems" :key="index">
                {{ item }}
            </div>
        </div>
    </div>
</template>

<style scoped>
.container {
    position: absolute;
    top: 92px;
    left: 0;
    width: 100%;
    background-color: white;
    z-index: 11;
    border-left: 1px solid black;
    border-bottom: 1px solid black;
}

.grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}

.category {
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    height: 313px;
    padding: 0 0 16px 40px;
    position: relative;
}

.category:not(:nth-child(3n)) {
    border-right: 1px solid black;
}

.category:nth-child(n + 4) {
    border-top: 1px solid black;
}

h2 {
    font-size: 48px;
    line-height: 46px;
    font-weight: 700;
}

p,
.footer-item {
    font-size: 14px;
    line-height: 24px;
    font-weight: 400;
}

.footer {
    display: flex;
    height: 130px;
    border-top: 1px solid black;
}

.footer-item {
    width: calc(100% / 3 * 2);
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
}

.footer-item:not(:last-child) {
    border-right: 1px solid black;
}

@media (max-width: 768px) {
    .container {
        border: none;
        top: 140px;
    }

    .grid {
        grid-template-columns: 1fr;
    }

    .category {
        height: 200px;
        padding: 0 20px 16px 20px;
        border-right: none !important;
        border-left: none !important;
        border-top: 1px solid black;
    }

    .category:first-child {
        border-top: none;
    }

    .category:nth-child(n + 4) {
        border-top: 1px solid black;
    }

    h2 {
        font-size: 32px;
        line-height: 36px;
    }

    .footer {
        display: flex;
        flex-wrap: wrap;
        height: auto;
        border-bottom: 1px solid black;
    }

    .footer-item {
        width: 50%;
        padding: 15px 0;
        border-top: 1px solid black;
        border-right: none;
    }

    .footer-item:nth-child(odd) {
        border-right: 1px solid black;
    }

    .footer-item:nth-child(even) {
        border-right: none;
    }

    .footer-item:nth-child(-n + 2) {
        border-top: 1px solid black;
    }
}
</style>
