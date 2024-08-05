<template>
    <base-dialog v-if="inputInvalid" title="invalid Input" @close="confirmError">
        <template #default>
            <h2>FBI Warning</h2>
            <p>Pls check all inputs and make sure you enter at least a few characters into each input field.</p>
        </template>
        <template #actions>
            <base-button @click="confirmError">OKEY</base-button>
        </template>
    </base-dialog>
  <base-card>
    <form @submit.prevent="submitData">
      <div class="form-control">
        <label for="title">Title</label>
        <input id="title" name="title" type="text" ref="titleInput" />
      </div>
      <div class="form-control">
        <label for="description">Description</label>
        <textarea id="description" name="description" rows="3" ref="descriptionInput"></textarea>
      </div>
      <div class="form-control">
        <label for="link">Link</label>
        <input id="link" name="link" type="url" ref="linkInput" />
      </div>
      <div>
        <base-button type="submit">Add Resource</base-button>
      </div>
    </form>
  </base-card>
</template>

<script>
export default {
  name: 'AddResource',
  data() {
    return {
        inputInvalid : false
    }
  },
  inject : ['addResource'],
  methods: {
    submitData() {
      const enterTitle = this.$refs.titleInput.value;
      const enterDescription = this.$refs.descriptionInput.value;
      const enterLink = this.$refs.linkInput.value;

      if(enterTitle.trim() === '' || enterDescription.trim() === '' || enterLink.trim() === '')
      {
        return this.inputInvalid = true;
      }

      this.addResource(enterTitle, enterDescription, enterLink);
    },
    confirmError() {
        this.inputInvalid = false;
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
