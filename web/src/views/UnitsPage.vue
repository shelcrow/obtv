<!--
  Licensed under the Apache License, Version 2.0 (the "License");
  you may not use this file except in compliance with the License.
  You may obtain a copy of the License at

     http://www.apache.org/licenses/LICENSE-2.0

  Unless required by applicable law or agreed to in writing, software
  distributed under the License is distributed on an "AS IS" BASIS,
  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
  See the License for the specific language governing permissions and
  limitations under the License.
-->

<template>
    <div class="unit-search-container">
        <div class="unit-count">
            <br/>
            <strong>{{ returnItemsCount }} Units</strong>
        </div>
        <div class="unit-search-sidebar">
            <component-unit-filter></component-unit-filter>
        </div>
        <div class="unit-search-body">
            <component-unit-list></component-unit-list>
        </div>
    </div>
</template>


<script>
import UnitFilter from "../components/UnitFilter.vue";
import UnitList from "../components/UnitList.vue";
export default {
  components: {
    "component-unit-list": UnitList,
    "component-unit-filter": UnitFilter
  },
  computed: {
    returnItemsCount() {
      return this.$store.state.returnItemsCount;
    }
  },
  created () {
      this.message = 'bye!'
  }
};

</script>


<style scoped>
.unit-search-container {
  margin-top: 20px;
  display: grid;
  grid-template-columns: 0px 250px 15px auto 25px;
  grid-template-rows: 25px auto;
}

.unit-search-sidebar {
  grid-column: 2 / 3;
  grid-row: 1 / 3;
}

.unit-search-body {
  grid-column: 4 / span 2;
  grid-row: 1 / span 2;
}

.nav-link {
  display: inline;
  padding: 0;
  padding-right: 5px;
}

#sort-by-button {
  float: right;
}

.unit-count {
  grid-column: 4 / 5;
  grid-row: 1 / 2;
  font-family: "Roboto Condensed";
}

a {
  color: #4285f4;
}

</style>