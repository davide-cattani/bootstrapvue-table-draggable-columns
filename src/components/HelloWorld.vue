<template>
  <div>
    <b-table striped hover bordered :fields="fields" :items="items">

      <!--draggable columns-->
      <template #thead-top="">
        <draggable tag="b-tr" v-model="fields">
          <b-th v-for="(field, i) in fields" :key="i" class="draggable text-center">
            <b-icon-grip-horizontal font-scale="1.5"/>
          </b-th>
        </draggable>
      </template>

    </b-table>
  </div>
</template>

<script>
import draggable from "vuedraggable";

export default {
  components: {
    draggable
  },
  data() {
    return {
      fields: [
        'age', 'first_name', 'last_name'
      ],
      items: [
        {age: 40, first_name: 'Dickerson', last_name: 'Macdonald'},
        {age: 21, first_name: 'Larsen', last_name: 'Shaw'},
        {age: 89, first_name: 'Geneva', last_name: 'Wilson'},
        {age: 38, first_name: 'Jami', last_name: 'Carney'}
      ]
    }
  }
}
</script>

<style>
.table td, th {
  border-width: 1px;
  border-style: solid;
  border-top: none;
  border-bottom-width: 0;
}

.table thead th:not(.draggable) {
  padding-top: 0;
  border-top-width: 0;
}

.table thead th.draggable {
  padding-bottom: 0;
  padding-top: 0;
  border-bottom-width: 0;
}

th svg {
  color: grey;
  cursor: ew-resize;
}

</style>
