<template>
    <div>
        <p>Form Fill</p>
    </div>
</template>

<script>
export default {
    name: 'FormFill',
    data() {
        return {
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
};
</script>
<style lang="scss" scoped>

</style>