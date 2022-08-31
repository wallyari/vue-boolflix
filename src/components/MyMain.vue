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
                                {{series.vote_average}}-
                            </li>                    
                        </ul>


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
    }

    
}
</script>

<style lang="scss" scoped>
main{
    background-color: #434343;
    height: calc(100vh - 80px);
    width: 100%;
}
</style> 