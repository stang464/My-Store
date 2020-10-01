<template>
  <div>
    <v-card>
      <v-card-title>
        <v-spacer></v-spacer>
        <v-text-field
          v-model="search"
          append-icon="mdi-magnify"
          label="Search"
          single-line
          hide-details
        ></v-text-field>
      </v-card-title>
      <v-data-table
        :headers="headers"
        :items="listdata"
        :items-per-page="5"
        :search="search"
        class="elevation-1"
      ></v-data-table>
    </v-card>
  </div>
</template>

<script>
export default {
  data() {
    return {
      search: '',
      headers: [
        {
          text: 'ชื่อร้าน',
          align: 'start',
          sortable: false,
          value: 'name',
        },
        {
          text: 'ประเภท',
          value: 'genre',
        },
        {
          text: 'Open',
          value: 'open',
        },
        {
          text: 'close',
          value: 'close',
        },
        {
          text: 'เบอร์โทร',
          value: 'phone',
        },
        {
          text: 'ที่อยู่',
          value: 'address.add',
        },
        {
          text: 'ตำบล/แขวง',
          value: 'address.sub_district',
        },
        {
          text: 'อำเภอ/เขต',
          value: 'address.district',
        },
        {
          text: 'จังหวัด',
          value: 'address.province',
        },
        {
          text: 'คำอธิบายร้าน',
          value: 'description',
        },
      ],
    }
  },
  computed: {
    listdata: {
      get() {
        return this.$nuxt.$store.state.list
      },
    },
  },
}
</script>
