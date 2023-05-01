# Admin Dashboard Vue

## Install

```shell
npm install @nathanbate/admin-dashboard
```

## Preview

![Preview of the Admin Dashboard](https://github.com/NathanBate/admin-dashboard-vue3/blob/main/Admin-Dashboard-Preview.png)

## Use

More details coming soon

Make sure to include css somewhere:

```javascript
import '@nathanbate/admin-dashboard-vue/dist/assets/index.css'
```

Here is a basic vue component

```vue
<template>
  <div>
    <Dashboard :show-search="true" :show-user-menu="true">
      <template v-slot:brandIcon>
        <IconCustomers class="fill-white"/>
      </template>
      <template v-slot:brandName>A New World</template>
      <template v-slot:menuItems>
        <MenuItem item-link="/customers">
          <template v-slot:icon>
            <CustomersIcon class="fill-white"/>
          </template>
          <template v-slot:label>
            Customers
          </template>
        </MenuItem>
        <MenuItem item-link="#" :top-level="false">
          <template v-slot:label>
            Sublink 1
          </template>
        </MenuItem>
        <MenuItem item-link="/customer/report" :top-level="false" :link-active="true">
          <template v-slot:label>
            Sublink 2
          </template>
        </MenuItem>
        <MenuItem />
      </template>
    </Dashboard>
  </div>

</template>

<script>
import Dashboard from '@nathanbate/admin-dashboard-vue/src/components/Dashboard.vue'
import MenuItem from '@nathanbate/admin-dashboard-vue/src/components/MenuItem.vue';
import IconCustomers from '@nathanbate/admin-dashboard-vue/src/components/icons/IconCustomers.vue';
import CustomersIcon from '@nathanbate/admin-dashboard-vue/src/components/icons/IconCustomers.vue';

export default {
  name: "AdminDashboardDemoApp",
  components: {
    CustomersIcon,
    IconCustomers,
    Dashboard : Dashboard,
    MenuItem : MenuItem,
    CustomerTestIcon : IconCustomers,
  },
}
</script>
```