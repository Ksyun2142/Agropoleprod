<template>

  <div id="app">
    <router-view></router-view>
  </div>

</template>

<script>
export default {
  name: 'App'
}
</script>

<script>
import DisplayForm from './DisplayForm';
import EditForm from './EditForm';
import { FIELD_LIST,
         ORG_LIST,
         PLANTS_LIST,
         YEARS_LIST } from './constants';
import { mapActions, mapGetters } from 'vuex';

export default {
  name: 'App',
  components: {
    DisplayForm,
    EditForm,
  },
  FARMING_FIELDS: FIELD_LIST,
  ORGS: ORG_LIST,
  PLANTS: PLANTS_LIST,
  YEARS: YEARS_LIST,
  data() {
    return {
      isEditForm: false,
      editData: null,
    }
  },
  computed: {
    ...mapGetters([
        'tableData',
    ])
  },
  created() {
    this.fetchTableData();
  },
  methods: {
    ...mapActions([
      'fetchTableData',
    ]),
    handleChangeDisplayingMode() {
      if (this.editData) {
        this.isEditForm = !this.isEditForm;
      } else {
        this.$message({
          message: 'Для редактирования необходимо выбрать ячейку',
          type: 'warning'
        });
      }
    },
    handleSelectCell(cell) {
      this.editData = cell;
    },
    handleClearForm() {
      this.editData = null;
    }
  },
}
</script>

<template>
  <div id="app">
  <div class="wh">
    <main class="main">
      <h2 class="form-title">СЕВООБОРОТ</h2>
      <display-form
          v-if="!isEditForm"
          :orgs="this.$options.ORGS"
          :farmingFields="this.$options.FARMING_FIELDS"
          :plants="this.$options.PLANTS"
          :years="this.$options.YEARS"
          :table-data="tableData"
          @toggle-edit="handleChangeDisplayingMode"
          @select-cell="handleSelectCell"
          @clear-form="handleClearForm"
      />
      <edit-form
          v-else
          :years="this.$options.YEARS"
          :farmingFields="this.$options.FARMING_FIELDS"
          :editData="editData"
          @toggle-edit="handleChangeDisplayingMode"/>
    </main>
  </div>
  </div>
</template>

<style lang="scss" scoped >
#app {
  font-family: DINPro, sans-serif;
  color: #008c83;
  font-weight: normal;
  font-size: 14px;
  text-align: center;

  position: absolute;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
  height: auto;

}

.main {
  width: 1024px;
  height: 100%;
  margin-top: 20px;
  margin-left: auto;
  margin-right: auto;
  background:white;

}
.wh{
min-height: 100%;
  background-color: white;
  border: 1px solid white;
}

td {
  vertical-align: middle !important;
}

.form-title {
  padding-top: 15px;
  color: #d8a331;
  font-size: 20px;
  font-family: DINPro-Medium, sans-serif;
  width: 25%;
  text-align: left;
}

table {
  text-align: left;
}

thead, tbody, tfoot, tr, td, th {
  border-color: #06aa9f !important;
}

h6, .h6, h5, .h5, h4, .h4, h3, .h3, h2, .h2, h1, .h1 {
  margin-top: 0 !important;
  margin-bottom: 0 ;
  font-weight: 500 !important;
  line-height: 1.2 !important;
}

.el-input__inner {
  color: #06aa9f !important;
  border-color: #06aa9f !important;
  border-radius: 0 !important;
}

</style>
