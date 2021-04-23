<template>
    <div class="form-fill">
        <div class="form-fill--event-container">
            <HeadingText>Shift Your Career into Overdrive!</HeadingText>
            <div class="form-fill--careers">
                <div class="form-fill--career-info">
                    <h3 class="form-fill--event-text">
                        We're seeking friendly, happy individuals up for the
                        challenge to change the way people view the automotive
                        industry. If you agree that a customer's time is
                        valuable and positive human interaction is important,
                        then we want to hear from you!
                    </h3>
                    <div
                        v-for="(event, index) in inputs"
                        :key="index"
                        class="form"
                    >
                        <h3 class="form-fill--place-holder-text">{{event.placeHolder}}</h3>
                        <input />
                    </div>
                    <button class="form-fill--submit-button" v-on:click="submitForm">I'm Interested</button>
                    <div v-if="loading == true">
                        <h4>Loading...</h4>
                    </div>
                    <div v-if="submitted == true">
                        <h4>Submitted!</h4>
                    </div>
                </div>
                <img
                    :src="require('@/assets/careers.jpg')"
                    alt="Chapman Careers"
                    class="career-photo"
                />
            </div>
        </div>
    </div>
</template>

<script>
import HeadingText from '@/components/heading-text';

export default {
    name: 'FormFill',
    components: {
        HeadingText,
    },
    data() {
        return {
            submitted: false,
            loading: false,
            inputs: [
                {
                    placeHolder: 'Name (required)',
                },
                {
                    placeHolder: 'Phone Number',
                },
            ],
        };
    },
    methods: {
        submitForm() {
            this.submitted = false;
            this.loading = true;
            setTimeout(() => {
                this.loading = false;
                this.submitted = true;
            }, 1500);
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
.form-fill--careers {
    display: flex;
}
.form-fill--career-info {
    display: flex;
    flex-direction: column;
    align-items: center;
}
.form-fill--place-holder-text {
    margin: 5px;
}
.form {
    display: flex;
    flex-direction: column;
    width: 100%;
    input {
        margin-bottom: 10px;
        width: calc(100% - 20px);
    }
}
.form-fill--submit-button {
        width: calc(100% - 20px);
        background-color: rgb(255, 208, 0);
        border: none;
        height: 30px;
        font-size: 1rem;
        font-weight: bold;
}
.career-photo {
    width: 50%;
}
.banner-img {
    width: 100%;
}
.event {
    margin-top: 2rem;
}
.event-name {
    margin-bottom: 1rem;
}
.event-text {
}
</style>
