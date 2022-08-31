<template>
        <main>
            <div class="container">
                    <div class="row">
                        <div class="col text-white">
                    <!-- CARD FILM -->
                        <ul>
                            <li></li>
                            <li v-for="(film,index) in filmList" :key="index">
                                {{film.title}}-
                                {{film.original_title}}-
                                {{film.original_language}}-
                                {{film.vote_average}}-

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
        filmList: Array
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