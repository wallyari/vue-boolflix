<template>
    <header class="bg-black">
        <div class="container-fluid">
                <div class="row">
                    <div class="col text-uppercase">
                    <span class="text-danger fs-4">Boolfix</span> 
                    </div>

                    <div class="col d-flex justify-content-end">
                    <input type="text" placeholder="cerca qui" v-model="keyword">
                    <button @click="$emit('searchKeyword', keyword)">Cerca</button>
            </div>
            </div>
        </div>
    </header>

</template>

<script>
export default {
    name: "MyHeader",
    data(){
        return{
            keyword: '',

        }
    }

}
</script>

<style lang="scss" scoped>
    header{
        height: 70px;
        display: flex;
        align-items: center;
    }
</style> 