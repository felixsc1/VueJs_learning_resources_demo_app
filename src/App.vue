<template>
    <ul></ul>
</template>

<script>
export default {
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