<template>
    <div class="form-fill">
        <div v-for="(event, index) in inputs" :key="index" class="form">
            <input :placeHolder="event.placeHolder"/>
        </div>
        <button v-on:click="submitForm">Submit</button>
        <div v-if="loading == true">
            <h4>Loading...</h4>
        </div>
        <div v-if="submitted == true">
            <h4>Submitted!</h4>
        </div>
    </div>
</template>

<script>
export default {
    name: 'FormFill',
    data() {
        return {
            submitted: false,
            loading: false,
            inputs: [
                {
                    placeHolder: 'First Name',
                },
                {  
                    placeHolder: 'Last Name',
                },
                {
                    placeHolder: 'Phone Number',
                },
                {
                    placeHolder: 'Email',
                },
            ],
        };
    },
    methods: {
        submitForm() {
        this.loading = true
        setTimeout(()=> { 
        this.loading = false
        this.submitted = true
        }, 1500)
        },
    },
};
</script>
<style lang="scss" scoped>
.form-fill {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-top: 15px;
}
.form {
display: flex;
flex-direction: column;
    input {
        margin: 10px;
    }
}
</style>