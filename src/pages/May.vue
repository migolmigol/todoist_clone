<template>
  <q-page class="flex flex-center">
    <h1>May</h1>
    <ul id="example-1">
      <li v-for="(item, idx) in projectList" :key='idx'>
        {{ item.name }}
      </li>
    </ul>
    <img alt="Quasar logo" src="~assets/quasar-logo-full.svg">
  </q-page>
</template>

<script>
    export default {
        name: 'PageIndex',
        created() {
            this.loadData()
        },
        data() {
            return {
                token: '',
                projectList: []
            }
        },
        methods: {
            loadData() {
                const config = {
                    headers: {'Authorization': "Bearer " + this.token}
                }
                this.$axios.get('https://api.todoist.com/rest/v1/projects', config)
                    .then((response) => {
                        console.log('응답: ', response);
                        this.projectList = response.data
                    })
                    .catch(() => {
                        this.$q.notify({
                            color: 'negative',
                            position: 'top',
                            message: 'Loading failed',
                            icon: 'report_problem'
                        })
                    })
            },
        }
    }
</script>
