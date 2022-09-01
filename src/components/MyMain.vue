<template>
        <main>
            <div class="container">
                    <div class="row">
                        <div class="col text-white">
                    <!-- CARD FILM -->
                        <ul>
                            <li>FILM</li>                            
                            <li v-for="(film,index) in filmList" :key="index">
                                {{film.title}}-
                                {{film.original_title}}-
                                {{film.original_language}}-
                                <img class="flags" v-if="avaibleFlags.includes(film.original_language)"
                                :src="require('../assets/images/'+ film.original_language + '.png')">
                                <span v-else>
                                {{film.original_language}}  
                                </span>
                                {{film.vote_average}}-
                            </li>                    
                        </ul>
                        </div>
                        <div class="col text-white">
                    <!-- SERIES FILM -->
                        <ul>
                            <li>SERIES</li>                            
                            <li v-for="(series,index) in seriesList" :key="index">
                                {{series.name}}-
                                {{series.original_name}}-
                                {{series.original_language}}-
                                <img class="flags" v-if="avaibleFlags.includes(series.original_language)"
                                :src="require('../assets/images/'+ series.original_language + '.png')">
                                {{series.vote_average}}-
                            </li>                    
                        </ul>
<img src="" alt="">

                        </div>
                </div>
            </div>
        </main>
</template>

<script>
export default {
    Name: 'MyMain',
    props:{
        filmList: Array,
        seriesList:Array
    },
    data(){
        return{
            avaibleFlags:['it','en','fr']
        }
    }    
}
</script>

<style lang="scss" scoped>
main{
    background-color: #434343;
    height: calc(100vh - 80px);
    width: 100%;
}
.flags{
    width: 30px;
}

</style> 