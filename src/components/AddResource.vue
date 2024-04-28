<template>
    <base-dialog v-if="invalidData">
        <template #default>
            <p>Invalid Input</p>
        </template>
        <template #bodies>
            <p>Unfortunately you have entered wrong input</p>
        </template>
        <template #actions>
            <base-button @click="confirmError">OKAY
        </base-button>
        </template>

    </base-dialog>
    <base-card>
        <form @submit.prevent="submitData">
            <div class="form-control">
                <label for="title">Title</label>
                <input id="title" name="title" type="text" ref="inputText"/>
            </div>
            <div class="form-control">
                <label for="description">Description</label>
                <textarea id="description" name="description" rows="3" ref="inputDesc"></textarea>
            </div>
            <div class="form-control">
                <label for="link">URL link</label>
                <input id="link" name="link" type="url" ref="inputLink"/>
            </div>
            <div>
                <base-button type="submit">
                    Add Resource
                </base-button>
            </div>
            
         </form>
    </base-card>
</template>

<script>
export default {
    data () {
        return {
            invalidData: false
        }
    },
    inject: ['addResource'],
    methods: {
        submitData(){
            const title = this.$refs.inputText.value
            const description = this.$refs.inputDesc.value
            const url = this.$refs.inputLink.value
            if (title === '' || description === '' || url === ''){
                this.invalidData = true
                return
            }
            this.addResource(title, description, url)
        },
        confirmError(){
            this.invalidData = false
        }
    }
}
</script>
<style scoped>
label {
  font-weight: bold;
  display: block;
  margin-bottom: 0.5rem;
}

input,
textarea {
  display: block;
  width: 100%;
  font: inherit;
  padding: 0.15rem;
  border: 1px solid #ccc;
}

input:focus,
textarea:focus {
  outline: none;
  border-color: #3a0061;
  background-color: #f7ebff;
}

.form-control {
  margin: 1rem 0;
}
</style>