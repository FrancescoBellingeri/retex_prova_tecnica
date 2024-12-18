<script>
export default {}
</script>

<template>
    <header>
        <div class="container">
            <div class="row">
                <div class="col-100 h-44"></div>
                <div class="col-100 h-40">
                    <button class="btn">Contribuisci</button>
                    <button class="btn">Abbonati</button>
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

.btn {
    height: 100%;
    background-color: white;
    width: 50%;
    border-width: 1px 0;
    border-style: solid;
    border-color: black;
}

.btn:first-child {
    border-right: 1px solid black;
}
</style>
