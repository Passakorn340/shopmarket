<template>
  <div class="container mt-4">
    <div class="row justify-content-center">
      <tt
        v-for="(item, index) in productData"
        :key="index"
        :image="item.image"
        :title="item.title"
        :tag="item.tag"
        @callbackshop="addtoTable"
      />
    </div>
    <b-modal id="bv-modal-example" hide-footer>
      <template #modal-title>Warning!!!</template>
      <div class="d-block text-center">
        <p>Order completed!</p>
      </div>
      <b-button class="mt-3" block @click="$bvModal.hide('bv-modal-example')">Close</b-button>
    </b-modal>
  </div>
</template>

<script>
import tt from "@/components/Shop-com.vue";

export default {
  props: {
    productData: Array
  },
  components: {
    tt
  },
  methods: {
    addtoTable(value) {
      this.$emit("update-table", value);
    },
    
  }
};
</script>

<style></style>
