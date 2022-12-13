<!-- Allows switching between two tabs (displaying either StoredResources or AddResource component) -->

<template>
    <base-card>
        <!-- note: we can add click listener to our custom button component even though no events are emitted there 
    -> any props or methods provided here will "fall through" to the root element of the custom component-->
        <base-button @click="setSelectedTab('stored-resources')">Stored Resources</base-button>
        <base-button @click="setSelectedTab('add-resource')">Add Resource</base-button>
    </base-card>
    <component :is="selectedTab"></component>
</template>

<script>
export default {
    data() {
        return {
            selectedTab: 'stored-resources',
        }
    },
    methods: {
        setSelectedTab(tab) {
            this.selectedTab = tab;
        }
    }
}
</script>