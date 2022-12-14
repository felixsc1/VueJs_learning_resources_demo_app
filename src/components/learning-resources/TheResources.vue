<!-- Allows switching between two tabs (displaying either StoredResources or AddResource component) -->

<template>
    <base-card>
        <!-- note: we can add click listener to our custom button component even though no events are emitted there 
    -> any props or methods provided here will "fall through" to the root element of the custom component-->
        <base-button @click="setSelectedTab('stored-resources')" :mode="storedResButtonMode">Stored
            Resources</base-button>
        <base-button @click="setSelectedTab('add-resource')" :mode="addResButtonMode">Add Resource</base-button>
    </base-card>
    <!-- keep alive caches the data, so that inputs don't get lost when switching tabs -->
    <keep-alive>
        <component :is="selectedTab"></component>
    </keep-alive>
</template>

<script>
import StoredResources from './StoredResources.vue'
import AddResource from './AddResource.vue'

export default {
    components: {
        StoredResources,
        AddResource
    },
    data() {
        return {
            selectedTab: 'stored-resources',
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
    },
    provide() {
        return {
            resources: this.storedResources,
            addResource: this.addResource
        }
    },
    computed: {
        storedResButtonMode() {
            return this.selectedTab === 'stored-resources' ? null : 'flat'
        },
        addResButtonMode() {
            return this.selectedTab === 'add-resource' ? null : 'flat'
        }
    },
    methods: {
        setSelectedTab(tab) {
            this.selectedTab = tab;
        },
        addResource(title, description, link) {
            const newResource = {
                id: new Date().toISOString(),
                title: title,
                description: description,
                link: link
            }
            // unshift is like push, but adds it to beginning of the array
            this.storedResources.unshift(newResource)
            this.selectedTab = 'stored-resources'
        }
    }
}
</script>