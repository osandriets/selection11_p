<template>
    <div>
        <div class="row">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <div class="form-group">
                    <label for="firstName">First Name</label>
                    <input
                            type="text"
                            id="firstName"
                            class="form-control"
                            :value="firstName"
                            v-on:input="updateFirstName($event.target.value)">
                </div>
            </div>
        </div>
        <div class="row">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <div class="form-group">
                    <label for="lastName">Last Name</label>
                    <input
                            type="text"
                            id="lastName"
                            class="form-control"
                            :value="lastName"
                            v-on:input="updateLastName($event.target.value)"
                    >
                </div>
            </div>
        </div>
    </div>
</template>
<script>
    export default {
        data: function () {
            return{
                firstName: '',
                lastName: ''
            }
        },
        props: ['name'],
        methods: {
            updateName: function () {
                var fullName = this.firstName + ' ' + this.lastName;
                this.$emit('input', fullName);
            },
            updateFirstName: function (value) {
                this.firstName = value;
                this.updateName();
            },
            updateLastName: function (value) {
                this.lastName = value;
                this.updateName();
            }


        }
    }
</script>
<style>

</style>