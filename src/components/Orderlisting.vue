<template>
  <div class="orderlisting">
    <table class="orderlisting__table">
      <thead class="orderlisting__thead">
        <tr class="orderlisting__thead--row">
          <th class="orderlisting__thead--item" v-for="key in columns">
            {{ key }}
            <span class="arrow">
            </span>
          </th>
          <th></th>
        </tr>
      </thead>
      <tbody class="orderlisting__tbody">
        <tr class="orderlisting__tbody--row" v-for="entry in gridData">
          <td class="orderlisting__tbody--item" v-for="key in columns">
            {{ entry[key] | isValueSet }}
          </td>
          <td class="orderlisting__tbody--item">
            <a class="orderlisting__tbody--link" href="" @click.prevent="removeItem">Remove Item</a>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: 'orderlisting',
  data () {
    return {
      columns: ['sku', 'description', 'brand', 'list price', 'discount', 'net price', 'qty', 'total'],
      gridData: [
        {
          sku: 'TN SO 000015',
          description: 'Magnetic contactor -9A (5.5 kW, 7.5 HCP), control voltage 230 Vac',
          brand: 'Schneider Electric',
          'list price': 'THB 880',
          discount: '30%',
          'net price': 'THB 660',
          qty: '16',
          total: 'THB 50,079,8823'
        },
        {
          sku: 'TN SO 000015',
          description: 'Magnetic contactor -9A (5.5 kW, 7.5 HCP), control voltage 230 Vac',
          brand: 'Schneider Electric',
          'list price': 'THB 880',
          discount: '30%',
          'net price': 'THB 660',
          qty: '16',
          total: 'THB 50,079,8823'
        },
        {
          sku: 'TN SO 000015',
          description: 'Magnetic contactor -9A (5.5 kW, 7.5 HCP), control voltage 230 Vac',
          brand: 'Schneider Electric',
          'list price': 'THB 880',
          discount: '30%',
          'net price': 'THB 660',
          qty: '16',
          total: 'THB 50,079,8823'
        },
        {
          sku: 'TN SO 000015',
          description: 'Magnetic contactor -9A (5.5 kW, 7.5 HCP), control voltage 230 Vac',
          brand: 'Schneider Electric',
          'list price': '',
          discount: '30%',
          'net price': '',
          qty: '16',
          total: ''
        },
        {
          sku: 'TN SO 000015',
          description: 'Magnetic contactor -9A (5.5 kW, 7.5 HCP), control voltage 230 Vac',
          brand: 'Schneider Electric',
          'list price': 'THB 880',
          discount: '30%',
          'net price': 'THB 660',
          qty: '16',
          total: 'THB 50,079,8823'
        }
      ]
    }
  },
  methods: {
    removeItem: function () {
      console.log('Item removed')
    }
  },
  filters: {
    isValueSet: function (value) {
      if (!value) return 'Set Price'
      return value
    }
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
.orderlisting {
  border: 1px solid rgba(201, 201, 201, 0.69);
  border-radius: 4px;
  background-color: #FFFFFF;
  margin-top: 17px;
}

.orderlisting__table {
  width: 100%;
  height: 100%;
  text-align: left;
  border-spacing: 0;
}

.orderlisting__thead--row {
  height: 50px;
  text-transform: uppercase;
}

.orderlisting__tbody {
  overflow-x: auto;
}

.orderlisting__tbody--row {
  height: 64px;
  box-shadow: 0 -1px 0 0 rgba(#C9C9C9, 0.4);

  &:nth-child(even) {
    background-color: rgba(#F8F8F8, 0.4);
  }
}

.orderlisting__thead--item {
  color: #626272;
  font-family: Montserrat;
  font-size: 8px;
  font-weight: bold;
  line-height: 11px;
  padding-left: 15px;
}

.orderlisting__tbody--item {
  color: #8899AA;
  font-family: Montserrat;
  font-size: 11px;
  line-height: 15px;
  padding-left: 15px;

  &:last-of-type {
    padding-right: 15px;
  }
}

.orderlisting__tbody--link {
  text-decoration: underline;
  color: #626272;
  font-family: Montserrat;
  font-size: 10px;
  line-height: 13px;
}
</style>
