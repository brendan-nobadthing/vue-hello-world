

<template>
 <div>
    <table>
      <thead>
        <tr>
          <th>Company</th>
          <th>Email</th>
          <th>Phone</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="company in companies" v-bind:key="company.id">
          <td>{{company.name}}</td>
          <td>{{company.email}}</td>
          <td>{{company.phone}}</td>
        </tr>
      </tbody>
    </table>
 </div>
</template>


<script>
import axios from 'axios';

export default {
  name: 'companies',
  data: function() {
    return { companies: [] }
  },
  mounted: function() {
    axios.get('http://firebootcamp-crm-api.azurewebsites.net/api/company')
        .then(res => {
          const c = res.data;
          console.log('Got Companies', c);
          this.setCompanies(c);
        })
  },
  methods: {
    setCompanies: function (c) {
      this.companies = c;
    }
  }
}
</script>
