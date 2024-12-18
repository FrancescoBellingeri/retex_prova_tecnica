<script>
export default {
    data() {
        return {
            blogs: [
                {
                    title: "Il Becco dell'oca",
                    author: "Paolo Dell'oca",
                    img: "/public/becco-dell'oca.jpg",
                },
                {
                    title: "Disarmato",
                    author: "Pasquale Pugliese",
                    img: "/public/disarmato.jpg",
                },
                {
                    title: "Battitiperminuto",
                    author: "Lorenzo Maria Alvaro",
                    img: "/public/battitiperminuto.jpg",
                },
                {
                    title: "La zanzarella",
                    author: "Elena Zanella",
                    img: "/public/zanzarella.jpg",
                },
                {
                    title: "Impact Q&A",
                    author: "Laura Orestano",
                    img: "/public/impactQ&A.jpg",
                },
            ],
            isDesktop: window.innerWidth >= 991, // Inizializza con lo stato attuale
        }
    },
    computed: {
        getVisibleBlogs() {
            return this.isDesktop ? this.blogs : this.blogs.slice(0, 4)
        },
    },
    methods: {
        handleResize() {
            this.isDesktop = window.innerWidth >= 991
        },
    },
    mounted() {
        window.addEventListener("resize", this.handleResize) // Aggiungi il listener
    },
    beforeDestroy() {
        window.removeEventListener("resize", this.handleResize) // Rimuovi il listener
    },
}
</script>

<template>
    <div class="grid-container">
        <div class="grid-item header text-red">Il Blog</div>

        <div v-for="(blog, index) in getVisibleBlogs" :key="index" class="grid-item">
            <img :src="blog.img" :alt="blog.title" class="blog-img" />
            <div class="blog-content">
                <h3>{{ blog.title }}</h3>
                <p>{{ blog.author }}</p>
            </div>
        </div>

        <div class="grid-item footer" v-if="!isDesktop">
            <div>Tutti i blog</div>
            <div class="arrow">&#8594;</div>
        </div>
    </div>
</template>

<style scoped>
.grid-container {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-template-rows: auto;
    border-top: 1px solid black;
}

.grid-item {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    padding: 24px 0;
    outline: 1px solid black;
}

.header {
    font-size: 24px;
    font-weight: 700;
    line-height: 28px;
}

.blog-img {
    width: 64px;
    height: 64px;
    border-radius: 100%;
    margin-bottom: 16px;
}

.blog-content h3,
.footer {
    font-size: 16px;
    font-weight: 700;
    line-height: 28px;
}

.blog-content p {
    font-size: 14px;
    font-weight: 400;
    line-height: 24px;
}

.arrow {
    width: 20px;
    height: 20px;
    font-size: 24px;
}

/* Stile per desktop */
@media (min-width: 991px) {
    .grid-container {
        grid-template-columns: repeat(auto-fit, minmax(150px, 1fr)); /* Adatta la griglia */
    }
}
</style>
