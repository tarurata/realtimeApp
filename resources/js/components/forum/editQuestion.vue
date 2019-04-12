<template>
    <v-container fluid>
        <v-card>
            <v-form>
              <v-text-field
                label="Title"
                v-model="form.title"
                type="text"
                required
              ></v-text-field>


              <markdown-editor v-model="form.body"></markdown-editor>

              <v-card-actions>
                  <v-btn icon samll>
                      <v-icon color="teal">save</v-icon>
                  </v-btn>

                  <v-btn icon samll @click="cancel">
                      <v-icon>cancel</v-icon>
                  </v-btn>
              </v-card-actions>
            </v-form>
        </v-card>
    </v-container>
</template>

<script>
    
export default{
    props:['data'],
    data(){
        return{
            form:{
                title: null,
                body: null
            }
        }
    },
    methods(){
        cancel(){
            EventBus.$emit('cancelEditing')
        }
    },
    created(){
        this.form = this.data
    }
}


</script>

<style>

</style>

