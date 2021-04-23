<template>
    <div class="form-fill">
        <div class="form-fill--event-container">
            <HeadingText>Shift Your Career into Overdrive!</HeadingText>
            <div class="form-fill--careers">
                <div class="form-fill--career-info">
                    <h4 class="form-fill--event-text">
                        We're seeking friendly, happy individuals up for the
                        challenge to change the way people view the automotive
                        industry. If you agree that a customer's time is
                        valuable and positive human interaction is important,
                        then we want to hear from you!
                    </h4>
                    <div
                        v-for="(event, index) in inputs"
                        :key="index"
                        class="form"
                    >
                        <h3 class="form-fill--place-holder-text">
                            {{ event.placeHolder }}
                        </h3>
                        <input />
                    </div>
                    <button
                        class="form-fill--submit-button"
                        v-on:click="submitForm"
                    >
                        I'm Interested
                    </button>
                    <div v-if="loading == true">
                        <h3>Loading...</h3>
                    </div>
                    <div v-if="submitted == true">
                        <h4>Submitted!</h4>
                    </div>
                </div>
                <div class="form-fill--image-container">
                    <img
                        :src="require('@/assets/careers.jpg')"
                        alt="Chapman Careers"
                        class="career-photo"
                    />
                </div>
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
            setTimeout(() => {
                this.submitted = false;
            }, 2500);
        },
    },
};
</script>
<style lang="scss" scoped>
@import './form-fill.scss';
</style>
