<template>
    <div class="container">
        <form v-if="!isSubmitted">
            <app-full-name v-model="name" :name="name"></app-full-name>
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <div class="form-group">
                        <label for="mail">Mail</label>
                        <input
                                type="text"
                                id="mail"
                                class="form-control"
                                v-model="mail"
                        >
                    </div>
                </div>
            </div>
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <div class="form-group">
                    <label for="password">Password</label>
                    <input
                            type="password"
                            id="password"
                            class="form-control"
                            v-model="password"
                    >
                </div>
                </div>
            </div>
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <label>Store in Database?</label>
                    <label for="storeYes">
                    <input
                                type="radio"
                                id="storeYes"
                                value="Yes"
                                v-model="store"> Yes
                    </label>
                    <label for="storeNo">
                        <input
                                type="radio"
                                id="storeNo"
                                value="No"
                                v-model="store"> No
                    </label>

                </div>
            </div>
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <button
                            class="btn btn-primary"
                            @click.prevent="submitted"
                    >Submit!
                    </button>
                </div>
            </div>
        </form>
        <hr>
        <div class="row" v-if="isSubmitted">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <div class="panel panel-default">
                    <div class="panel-heading">
                        <h4>Your Data</h4>
                    </div>
                    <div class="panel-body">
                        <p>Full Name: {{ name }}</p>
                        <p>Mail: {{ mail }} </p>
                        <p>Password: {{ password}}</p>
                        <p>Store in Database?: {{ store }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import FullName from './components/FullName.vue';

    export default {
        data: function () {
            return{
                isSubmitted: false,
                name: '',
                mail: '',
                password: '',
                store: 'Yes'
            }
        },
        components: {
          appFullName: FullName
        },
        methods: {
            submitted(){
                this.isSubmitted = true;
            }
        }
    }
</script>

<style>
</style>
