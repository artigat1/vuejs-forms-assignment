<template>
    <div class="row">
        <div class="col-xs-6 col-sm-4 col-sm-offset-2 col-md-3 col-md-offset-3">
            <label for="firstName">First Name</label>
            <input
                    @input="updated()"
                    class="form-control"
                    id="firstName"
                    placeholder="First name"
                    type="text"
                    v-model.trim="firstName"/>
        </div>
        <div class="col-xs-6 col-sm-4 col-sm-offset-2 col-md-3 col-md-offset-3">
            <label for="lastName">Last Name</label>
            <input
                    @input="updated()"
                    class="form-control"
                    id="lastName"
                    placeholder="Last name"
                    type="text"
                    v-model.trim="lastName"/>
        </div>
    </div>
</template>

<script>
    export default {
        name: "FullName",
        
        props: ['value'],
        
        data() {
            return {
                firstName: '',
                lastName: ''
            }
        },
        
        computed: {
            fullName() {
                return `${this.firstName} ${this.lastName}`.trim();
            }
        },
        
        methods: {
            
            updated() {
                this.$emit('input', this.fullName);
            }
        }
    }
</script>

<style scoped>

</style>
