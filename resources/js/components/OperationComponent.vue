<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-6">
                <div class="card bg-info">
                    <div class="card-header text-center">CRUD OPERATION VUE</div>
                    <p class="text-center alert alert-danger" v-bind:class="{hidden: hasError}"> 
                        Llene los datos por favor</p>
                    <div class="card-body">
                        <div class="form-group">
                            <label for="name">Name:</label>
                            <input type="text" class="form-control" id="name" name="name"
                                 placeholder="Ingrese su nombre" v-model="newItem.name" >       
                        </div>
                        <div class="form-group">
                            <label for="age">Age:</label>
                            <input type="number" class="form-control" id="age" name="age"
                                 placeholder="Ingrese su edad" v-model="newItem.age" >       
                        </div>
                        <div class="form-group">
                            <label for="profesion">Profesion:</label>
                            <input type="text" class="form-control" id="profesion" name="profesion"
                                 placeholder="Ingrese su Profesion" v-model="newItem.profesion" >       
                        </div>
                        <button class="btn btn-primary" @click.prevent="createItem()">
                              ADD
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data: function(){
            return{
                newItem: {'name': '', 'age': '', 'prefesion': ''},
                hasError: true,
            }
        },
        methods:{
            createItem: function createItem(){
                var input = this.newItem;
                if( input['name'] == '' || input['age'] == '' || input['profesion'] == '' )
                {
                    this.hasError = false;
                }else{
                    this.hasError = true;
                    
                }
            }
        },
        mounted() {
            console.log('Component mounted.')
        }
    }
</script>
