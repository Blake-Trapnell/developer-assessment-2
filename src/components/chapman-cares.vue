<template>
    <div class="chapman-cares">
        <img
            :src="require('@/assets/making-strides.jpg')"
            alt="Making Strides"
            class="banner-img"
        />
        <img
            :src="require('@/assets/canine-companions.jpg')"
            alt="Canine Companions"
            class="banner-img"
        />
        <HeadingText>Chapman Cares</HeadingText>

        <img
            :src="require('@/assets/cares-banner.jpg')"
            alt="Chapman Cares"
            class="banner-img"
        />

        <div v-for="(event, index) in events" :key="index" class="event">
            <h3 class="event-name">{{ event.name }}</h3>
            <p class="event-text">{{ event.text }}</p>
            <img 
                v-bind:src='event.img'
            />
        </div>
    </div>
</template>

<script>
import HeadingText from '@/components/heading-text';

export default {
    name: 'ChapmanCares',
    components: {
        HeadingText,
    },
    data() {
        return {
            events: [
                {
                    name: 'Making Strides Against Cancer',
                    text:
                        'Thousands of people, young and old, participated in the Making Strides Against Breast Cancer event at Tempe Beach Park. As a sponsorship partner, Chapman Auto brought the Breast Cancer Pace Car, driven by Danica Patrick. Chapman Auto employees participated in the walk, helping to raise thousands of dollars for breast cancer research.',
                    img: require('@/assets/making-strides.jpg'),
                },
                {
                    name: 'Canine Companions For Independence',
                    text:
                        'Chapman Auto has been a proud supporter of Canine Companions for Independence for more than 10 years. From sponsoring a golf tournament to puppy training, Chapman Auto employees are proud to work with CCI as they help others live happy, independent lives.',
                    img: require('@/assets/canine-companions.jpg'),
                },
            ],
        };
    },
};
</script>

<style lang="scss" scoped>
.banner-img {
    width: 100%;
}
.event {
    margin-top: 2rem;
}
.event-name {
    margin-bottom: 1rem;
}
</style>
