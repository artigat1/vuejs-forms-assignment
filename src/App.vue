<template>
    <div class="container">
        <form>
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <div class="form-group">
                        <app-full-name v-model="userData.fullName"/>
                    </div>
                    <div class="form-group">
                        <label for="email">Email</label>
                        <input
                                class="form-control"
                                id="email"
                                placeholder="Email address"
                                type="text"
                                v-model.trim="userData.email"/>
                    </div>
                    <div class="form-group">
                        <label for="password">Password</label>
                        <input
                                class="form-control"
                                id="password"
                                type="password"
                                v-model.trim="userData.password"/>
                    </div>
                    <div class="form-group">
                        <label for="storeYes">
                            <input
                                    id="storeYes"
                                    type="radio"
                                    v-model="userData.storeData"
                                    value="yes"> Yes
                        </label>
                        <label for="storeNo">
                            <input
                                    id="storeNo"
                                    type="radio"
                                    v-model="userData.storeData"
                                    value="no"> No
                        </label>
                    </div>
                    <div class="row">
                        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                            <button @click.prevent="submitForm"
                                    class="btn btn-primary">Submit!
                            </button>
                        </div>
                    </div>
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
                        <p>Full Name: {{ userData.fullName }}</p>
                        <p>Mail: {{ userData.email }}</p>
                        <p>Password: {{ userData.password }}</p>
                        <p>Store in Database?: {{ userData.storeData }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import FullName from './FullName.vue';

    export default {

        components: {
            appFullName: FullName
        },

        data() {
            return {
                userData: {
                    fullName: '',
                    email: '',
                    password: '',
                    storeData: 'no'
                },
                isSubmitted: false
            }
        },

        methods: {
            submitForm() {
                this.isSubmitted = true;
            }
        }
    }
</script>

<style>
</style>
