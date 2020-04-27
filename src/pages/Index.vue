<template>
  <q-page>
    <template>
      <h2 class="text-h2 row justify-center">Cuidados básicos</h2>
      <Cards />
      <h2 class="text-h2 row justify-center">Vídeos oficiais OMS</h2>
      <Carrousel />
      <h2 class="text-h2 row justify-center">Dados oficiais</h2>
      <q-card>
      <q-table :data="data" :columns="columns" row-key="name" :pagination.sync="pagination" :filter="filter">
        <template v-slot:top-right>
          <q-input borderless dense debounce="300" v-model="filter" placeholder="Search">
            <template v-slot:append>
              <q-icon name="search" />
            </template>
          </q-input>
        </template>
      </q-table>
      </q-card>
    </template>
  </q-page>
</template>

<script>
import Cards from '../components/Cards'
import Carrousel from '../components/Carrousel'

export default {

  name: 'PageIndex',

  components: {
    Cards,
    Carrousel
  },

  data () {
    return {
      filter: '',
      pagination: {
        sortBy: 'desc',
        descending: false,
        page: 1,
        rowsPerPage: 10
      },
      columns: [

        { name: 'country', align: 'center', label: 'País', field: 'country', sortable: true },
        { name: 'cases', label: 'Casos', field: 'cases', sortable: true },
        { name: 'todayCases', label: 'Casos Hoje', field: 'todayCases', sortable: true },
        { name: 'deaths', label: 'Deaths', field: 'deaths', sortable: true },
        { name: 'todayDeaths', label: 'Mortes hoje', field: 'todayDeaths', sortable: true },
        { name: 'recovered', label: 'Recuperados', field: 'recovered', sortable: true },
        { name: 'active', label: 'Ativos', field: 'active', sortable: true },
        { name: 'critical', label: 'Críticos', field: 'critical', sortable: true },
        { name: 'tests', label: 'Testes', field: 'tests', sortable: true }

        // { name: 'country', align: 'center', label: 'Country', field: 'country', sortable: true },
        // { name: 'cases', label: 'Cases', field: 'cases', sortable: true },
        // { name: 'todayCases', label: 'Today Cases', field: 'todayCases', sortable: true },
        // { name: 'deaths', label: 'Deaths', field: 'deaths', sortable: true },
        // { name: 'todayDeaths', label: 'Today Deaths', field: 'todayDeaths', sortable: true },
        // { name: 'recovered', label: 'Recovered', field: 'recovered', sortable: true },
        // { name: 'active', label: 'Active', field: 'active', sortable: true },
        // { name: 'critical', label: 'Critical', field: 'critical', sortable: true },
        // { name: 'tests', label: 'Tests', field: 'tests', sortable: true }

      ],
      data: []
    }
  },

  methods: {
    loadData () {
      this.$axios.get('https://corona.lmao.ninja/v2/countries?sort=country')
        .then((response) => {
          this.data = response.data
        })
        .catch(() => {
          this.$q.notify({
            color: 'negative',
            position: 'top',
            message: 'Loading failed',
            icon: 'report_problem'
          })
        })
    }
  },

  created () {
    this.loadData()
  }
}
</script>
