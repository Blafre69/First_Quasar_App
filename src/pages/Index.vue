<template>
  <q-page class="full-width">
     <div class="row full-width">
      <div class="col">
        <q-input
          filled
          square
          :dense="dense"
          v-model="itemname"
          placeholder="Add Item"
          counter
        >
            <template v-slot:append>
              <q-btn round dense flat icon="add"  @click="addItem()"/>
            </template>
            <template v-slot:after>
              <q-btn round dense flat icon="delete" @click="itemname=''" class="cursor-pointer"/>
            </template>
        </q-input>
      </div>
    </div>
    <q-list padding class="text-primary" v-if="items.length > 0">
      <q-slide-item @left="deleteItem(index)"  v-for="(item, index) in items" v-bind:key="index" v-ripple separator>
        <template v-slot:left>
          Removed
        </template>
        <template v-slot:right></template>
        <q-item>
        <q-item-section avatar>
          <q-icon color="primary" name="list" />
        </q-item-section>

        <q-item-section>{{item.name}}</q-item-section>
        </q-item>
      </q-slide-item>
    </q-list>
  </q-page>
</template>

<script>
export default {
  name: 'PageIndex',
  data () {
    return {
      items: [],
      itemname: ''
    }
  },
  methods: {
    addItem () {
      this.items.push({
        name: this.itemname
      })
      console.log(this.items)
    },
    deleteItem (index) {
      console.log(index)
      this.items.slice(index, 1)
    }
  }
}
</script>
