<template>
  <div>
    <Dashboard>
      <template v-slot:brandIcon>
        <IconCustomers class="fill-white"/>
      </template>
      <template v-slot:brandName>Test Business Name</template>
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
import Dashboard from '@/components/Dashboard.vue';
import MenuItem from '@/components/MenuItem.vue';
import IconCustomers from '@/components/icons/IconCustomers.vue';
import CustomersIcon from '@/components/icons/IconCustomers.vue';

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

