<template>
    <ul>
        <LearningResource v-for="resource in storedResources" :key="resource.id" :title="resource.title"
            :description="resource.description" :link="resource.link" />
    </ul>
</template>

<script>
import LearningResource from './components/learning-resources/LearningResource.vue'
export default {
    components: {
        LearningResource
    },
    data() {
        return {
            storedResources: [
                {
                    id: 'official-guide',
                    title: 'Official Guide',
                    description: 'The official vue.js documentation',
                    link: 'https://vuejs.org',
                },
                {
                    id: 'google',
                    title: 'Google',
                    description: 'Googling is important',
                    link: 'https://www.google.com',
                },

            ]
        }
    }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

* {
    box-sizing: border-box;
}

html {
    font-family: 'Roboto', sans-serif;
}

body {
    margin: 0;
}
</style>