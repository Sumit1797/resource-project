<template>
    <base-card>
        <base-button @click="setSelectedTab('stored-resource')" :mode="storedResMode">Stored Resources</base-button>
        <base-button @click="setSelectedTab('add-resource')" :mode="addResMode">Add Resource</base-button>
    </base-card>
    <KeepAlive>
        <component :is="selectedTab"></component>
    </KeepAlive>
</template>
<script>
import StoredResource from './StoredResource.vue'
import AddResource from './AddResource.vue'
export default{
    components:{
        StoredResource,
        AddResource
    },
    computed:{
        storedResMode(){
            return this.selectedTab === 'stored-resource' ? null : 'flat'
        },
        addResMode(){
            return this.selectedTab === 'add-resource' ? null : 'flat'
        }
    },
    data () {
        return {
            selectedTab: 'stored-resource',
            storedresources: [
                {
                    id: 'offciial-1', 
                    title: 'this is an initial title',
                    description: 'a short description',
                    link: 'https://vuejs.org'
                },
                {
                    id: 'offciial-2', 
                    title: 'this is an initial title',
                    description: 'a short description for 2nd course',
                    link: 'https://google.com'
                }
            ]
        }
    },
    provide () {
        return {
            resources: this.storedresources,
            addResource: this.addResource,
            removeResource: this.removeResource
        }
    },
    methods:{
        setSelectedTab(tab){
            this.selectedTab = tab
        },
        addResource(title, desc, url){
            const id = this.data

            var res = {
                id,
                title,
                desc,
                url
            }

            this.storedresources.unshift(res)
        },
        removeResource(id){
            console.log(id)
            alert('here')
            const ind = this.storedresources.findIndex(res => res.id == id)
            this.storedresources.splice(ind, 1)

            // this.storedresources.
        }
    }
}
</script>