<script>
export default {}
</script>

<template>
    <header>
        <div class="container">
            <div class="row">
                <div class="col-100 h-44"></div>
                <div class="col-100 h-40">
                    <button class="btn h-100 bg-white">Contribuisci</button>
                    <button class="btn h-100 bg-white">Abbonati</button>
                </div>
                <div class="col-100 h-52">
                    <button class="bars text-red h-100 bg-white">
                        <i class="fa-solid fa-bars"></i>
                    </button>
                    <input class="h-100" type="text" />
                    <button class="search text-red h-100 bg-white">
                        <i class="fa-solid fa-magnifying-glass"></i>
                    </button>
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

.col-100.h-52 {
    display: flex;
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
</style>
