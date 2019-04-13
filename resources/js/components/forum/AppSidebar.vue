<template>
    <v-card>
         <v-toolbar color="cyan" dark dense class="mt-2">
              <v-toolbar-title>Categories</v-toolbar-title>
        </v-toolbar>   

        <v-list>
            <v-list-tile >
                <v-list-tile-content>
                    <v-list-title>Category</v-list-title>
                </v-list-tile-content>
            </v-list-tile>
            <v-list-tile v-for="category in categories" :key="category.id">
                <v-list-tile-content>
                    <v-list-title>{{category.name}}</v-list-title>
                </v-list-tile-content>
            </v-list-tile>
        </v-list>

    </v-card>
</template>

<script>
    
export default{
    data(){
        return {
            categories: {}
        }
    },
    created(){
        axios.get('/api/category')
        .then(res => this.categories = res.data.data)
        .catch(error => console.log('error.respons.data'))
    }
}


</script>

<style>

</style>


