<template>
    <div class="container">
        <form v-if="!isSubmitted">
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <div class="form-group">
                        <label for="firstName">First Name</label>
                        <input
                                type="text"
                                id="firstName"
                                class="form-control"
                                v-model="userData.firstName">
                    </div>

                    <div class="form-group">
                    <label for="lastName">Last Name</label>
                    <input
                            type="text"
                            id="lastName"
                            class="form-control"
                            v-model="userData.lastName">
                    </div>

                    <div class="form-group">
                        <label for="mail">Mail</label>
                        <input
                                type="text"
                                id="mail"
                                class="form-control"
                                v-model="userData.mail">
                    </div>

                    <div class="form-group">
                        <label for="password">Password</label>
                        <input
                                type="password"
                                id="password"
                                class="form-control"
                                v-model="userData.password">
                    </div>

                    <div class="row">
                        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3 form-group">
                            <p>Store Data?</p>
                            <label for="yes">
                                <input
                                        type="radio"
                                        id="yes"
                                        value="Yes"
                                        v-model="storeInDataBase"> Yes
                            </label>
                            <label for="no">
                                <input
                                        type="radio"
                                        id="no"
                                        value="No"
                                        v-model="storeInDataBase"> No
                            </label>
                        </div>
                    </div>

                    <div class="row">
                        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                            <button
                                    type="submit"
                                    class="btn btn-primary"
                                    @click.prevent="submitted">Submit!
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
                        <p>Full Name: {{ userData.firstName}} {{ userData.lastName }}</p>
                        <p>Mail: {{ userData.mail }} </p>
                        <p>Password: {{ userData.password }} </p>
                        <p>Store in Database?: {{ storeInDataBase }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                userData: {
                    fullName: {
                      firstName: '',
                      lastName: ''
                    },
                    mail: '',
                    password: ''
                },
                storeInDataBase: 'No',
                isSubmitted: false
            }
        },
        methods: {
            submitted() {
                this.isSubmitted = true;
            }
        }
    }
</script>

<style>
</style>
