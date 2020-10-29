<template>
  <q-page padding>
    <div class="row">
      <CardUser class="col-12 col-md-6" v-for="user in users" :key="user.id" :user="user" />
    </div>
  </q-page>
</template>

<script>
import CardUser from 'components/CardUser'
export default {
  name: 'PageCases',
  components: {
    CardUser
  },
  data () {
    return {
      users: [
        {
          id: 1
          // name: 'Maria'
        },
        {
          id: 2
          // name: 'João'
        },
        {
          id: 3
          // name: 'Carlos'
        },
        {
          id: 4
          // name: 'Ana'
        }
      ]
    }
  },
  methods: {
    listUsers () {
      this.$axios.get('https://jsonplaceholder.typicode.com/users').then(response => {
        this.users = response.data
      })
    }
  },
  beforeMount () {
    this.listUsers()
  }
}
</script>
