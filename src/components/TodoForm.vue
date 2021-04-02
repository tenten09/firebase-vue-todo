<template>
  <div>
    <b-container>
      <b-input-group>
        <b-form-input type="text" v-model="value"/>
        <!-- <b-form-input type="text" v-model="value" key="type" /> -->

        <!-- <b-row class="my-1" v-for="type in types" :key="type">
          <b-col sm="3">
            <label :for="`type-${type}`">Type <code>{{ type }}</code>:</label>
          </b-col>

          <b-col sm="9">
            <b-form-input :id="`type-${type}`" :type="type"/>
          </b-col>
        </b-row> -->
        <b-input-group-append>
          <b-button variant="info" @click="handleAddTodo">送信</b-button>
        </b-input-group-append>
      </b-input-group>
    </b-container>
  </div>
</template>

<script>
  export default {
    name: 'TodoForm',
    data() {
      return {
        value: '',
        types: [
          'date',
          'time',
        ],
      };
    },
    methods: {
      handleAddTodo() {
        this.$emit('handleParentAddTodo', this.value);
        this.value = "";
      }
    }
  };
</script>

<style scoped>

</style>