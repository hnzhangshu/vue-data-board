<template>
  <div>
    <dashboardItem :dashboard="currentDashboard" mode="view" />
  </div>
</template>
<script>
import dashboardItem from './dashboardItem'
import { getdDashboardById } from '@/api/dashboard'

export default {
  components: { dashboardItem },
  data() {
    return {
      currentDashboard: undefined
    }
  },
  created() {
    console.log(this.$route.params.id)
    getdDashboardById(this.$route.params.id).then(resp => {
      this.currentDashboard = resp.data
    })
  }
}
</script>
