<script>
export default {
    data() {
        return {
            footerItems: [
                {
                    text: "Il Gruppo",
                    url: "#",
                },
                {
                    text: "Note Legali",
                    url: "#",
                },
                {
                    text: "Chi siamo",
                    url: "#",
                },
                {
                    text: "Condizioni d'uso",
                    url: "#",
                },
                {
                    text: "Privacy",
                    url: "#",
                },
                {
                    text: "Scrivici",
                    url: "#",
                },
                {
                    text: "Pubblicità",
                    url: "#",
                },
            ],
        }
    },
}
</script>

<template>
    <footer>
        <div class="content bg-light-green padding">
            <ul>
                <li v-for="(item, index) in footerItems" :key="index">{{ item.text }}</li>
            </ul>
            <div class="copyright">© 1994-2022 Vita Società Editoriale S.p.A.</div>
        </div>
    </footer>
</template>

<style scoped>
.content {
    border-top: 1px solid black;
}

ul {
    list-style-type: none;
}

li {
    font-size: 16px;
    font-weight: 700;
    line-height: 24px;
    margin-bottom: 16px;
}

.copyright {
    font-size: 14px;
    line-height: 24px;
    font-weight: 400;
}

@media (min-width: 991px) {
    .content {
        border-top: 0;
        display: flex;
        justify-content: space-between;
    }

    ul {
        display: flex;
    }

    li {
        font-size: 14px;
        font-weight: 400;
        margin-right: 16px;
    }
}
</style>
