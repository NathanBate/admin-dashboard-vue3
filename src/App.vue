<template>
  <div>
    <Dashboard :show-search="true" :show-user-menu="true">
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
      <template v-slot:content>
        <div>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Mauris tempus nisi nunc, eget vehicula tellus rutrum id. Fusce mollis nulla et est luctus egestas. Cras lorem tortor, dignissim sit amet imperdiet eu, venenatis vel sapien. Integer sit amet orci ex. Nunc nec lectus et nunc fringilla tincidunt venenatis ut erat. Nullam luctus non orci a porttitor. Sed dignissim non mi eu tempus. Integer feugiat, leo in blandit iaculis, justo nisl mollis sapien, eu ultricies magna mi a ex. Maecenas porttitor tincidunt risus, sed bibendum lacus consectetur ac. Duis id nunc sit amet nunc hendrerit feugiat. Fusce ante purus, iaculis ut ipsum eu, tempor venenatis tortor. Aliquam ullamcorper augue in semper laoreet. Fusce pellentesque ligula sit amet ante fringilla euismod. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus.

          Suspendisse viverra suscipit lorem, vel posuere metus posuere eget. Phasellus at lacinia quam. Nam et ante fermentum, venenatis libero eget, porttitor ex. Sed sit amet porta risus. Vivamus sed nibh at augue malesuada auctor. Sed in facilisis nibh. Curabitur varius est enim, a pharetra lectus faucibus sit amet. Donec congue elementum efficitur. Aenean nec enim at velit blandit tempus eu sed ligula.

          Vestibulum porttitor elit vitae ligula finibus sollicitudin. Vivamus lacinia vel arcu sed aliquam. Nunc aliquam quam at augue auctor malesuada. Integer id tristique tortor. Ut ut suscipit elit. Morbi vulputate aliquam lacus. Aliquam erat volutpat. Proin tristique sapien eget accumsan egestas. Mauris feugiat dolor orci, id venenatis metus egestas at. Nam non dictum dolor. Nunc in justo cursus diam lobortis euismod. Vivamus fermentum iaculis magna, non vulputate erat luctus quis. Fusce nec massa sit amet augue pellentesque mattis nec quis risus.

          Vivamus vitae bibendum turpis, eu lobortis odio. Vivamus quam tellus, elementum id rhoncus molestie, auctor quis felis. In vel quam cursus, luctus tellus ut, hendrerit lectus. Aenean vitae urna erat. Phasellus suscipit semper lacus, eu malesuada quam sodales quis. Mauris euismod vel nulla non ornare. Suspendisse dignissim sodales felis, in iaculis mi pulvinar at. Aenean neque sapien, lacinia eu tincidunt in, porta eget nibh. Aliquam ultrices arcu magna, a finibus felis pharetra in. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Aliquam ullamcorper mattis lacus nec imperdiet. Aenean vel sapien vitae dolor pellentesque scelerisque vitae a urna. Cras rutrum convallis nibh, et pharetra ipsum vestibulum sed. Etiam nec tincidunt erat, eu malesuada quam. Morbi sed sapien ultricies, molestie enim vel, malesuada dolor.

          Vivamus vel nisl ultrices risus faucibus rutrum non id metus. Fusce sagittis arcu sed pulvinar efficitur. Aliquam vulputate diam sed dictum luctus. Nulla fermentum molestie faucibus. Duis a venenatis diam. Morbi massa arcu, varius ac euismod at, vehicula a quam. Praesent ex nisl, placerat quis enim sit amet, iaculis lacinia urna. Phasellus pharetra enim mi, vitae tincidunt lectus eleifend at. Morbi rhoncus sem vel velit varius dapibus in quis nisl. Mauris vulputate tortor tortor, in tincidunt elit pharetra in. Donec in semper velit. Cras scelerisque velit finibus, tempor tortor in, scelerisque mi.
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Mauris tempus nisi nunc, eget vehicula tellus rutrum id. Fusce mollis nulla et est luctus egestas. Cras lorem tortor, dignissim sit amet imperdiet eu, venenatis vel sapien. Integer sit amet orci ex. Nunc nec lectus et nunc fringilla tincidunt venenatis ut erat. Nullam luctus non orci a porttitor. Sed dignissim non mi eu tempus. Integer feugiat, leo in blandit iaculis, justo nisl mollis sapien, eu ultricies magna mi a ex. Maecenas porttitor tincidunt risus, sed bibendum lacus consectetur ac. Duis id nunc sit amet nunc hendrerit feugiat. Fusce ante purus, iaculis ut ipsum eu, tempor venenatis tortor. Aliquam ullamcorper augue in semper laoreet. Fusce pellentesque ligula sit amet ante fringilla euismod. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus.

          Suspendisse viverra suscipit lorem, vel posuere metus posuere eget. Phasellus at lacinia quam. Nam et ante fermentum, venenatis libero eget, porttitor ex. Sed sit amet porta risus. Vivamus sed nibh at augue malesuada auctor. Sed in facilisis nibh. Curabitur varius est enim, a pharetra lectus faucibus sit amet. Donec congue elementum efficitur. Aenean nec enim at velit blandit tempus eu sed ligula.

          Vestibulum porttitor elit vitae ligula finibus sollicitudin. Vivamus lacinia vel arcu sed aliquam. Nunc aliquam quam at augue auctor malesuada. Integer id tristique tortor. Ut ut suscipit elit. Morbi vulputate aliquam lacus. Aliquam erat volutpat. Proin tristique sapien eget accumsan egestas. Mauris feugiat dolor orci, id venenatis metus egestas at. Nam non dictum dolor. Nunc in justo cursus diam lobortis euismod. Vivamus fermentum iaculis magna, non vulputate erat luctus quis. Fusce nec massa sit amet augue pellentesque mattis nec quis risus.

          Vivamus vitae bibendum turpis, eu lobortis odio. Vivamus quam tellus, elementum id rhoncus molestie, auctor quis felis. In vel quam cursus, luctus tellus ut, hendrerit lectus. Aenean vitae urna erat. Phasellus suscipit semper lacus, eu malesuada quam sodales quis. Mauris euismod vel nulla non ornare. Suspendisse dignissim sodales felis, in iaculis mi pulvinar at. Aenean neque sapien, lacinia eu tincidunt in, porta eget nibh. Aliquam ultrices arcu magna, a finibus felis pharetra in. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Aliquam ullamcorper mattis lacus nec imperdiet. Aenean vel sapien vitae dolor pellentesque scelerisque vitae a urna. Cras rutrum convallis nibh, et pharetra ipsum vestibulum sed. Etiam nec tincidunt erat, eu malesuada quam. Morbi sed sapien ultricies, molestie enim vel, malesuada dolor.

          Vivamus vel nisl ultrices risus faucibus rutrum non id metus. Fusce sagittis arcu sed pulvinar efficitur. Aliquam vulputate diam sed dictum luctus. Nulla fermentum molestie faucibus. Duis a venenatis diam. Morbi massa arcu, varius ac euismod at, vehicula a quam. Praesent ex nisl, placerat quis enim sit amet, iaculis lacinia urna. Phasellus pharetra enim mi, vitae tincidunt lectus eleifend at. Morbi rhoncus sem vel velit varius dapibus in quis nisl. Mauris vulputate tortor tortor, in tincidunt elit pharetra in. Donec in semper velit. Cras scelerisque velit finibus, tempor tortor in, scelerisque mi.
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Mauris tempus nisi nunc, eget vehicula tellus rutrum id. Fusce mollis nulla et est luctus egestas. Cras lorem tortor, dignissim sit amet imperdiet eu, venenatis vel sapien. Integer sit amet orci ex. Nunc nec lectus et nunc fringilla tincidunt venenatis ut erat. Nullam luctus non orci a porttitor. Sed dignissim non mi eu tempus. Integer feugiat, leo in blandit iaculis, justo nisl mollis sapien, eu ultricies magna mi a ex. Maecenas porttitor tincidunt risus, sed bibendum lacus consectetur ac. Duis id nunc sit amet nunc hendrerit feugiat. Fusce ante purus, iaculis ut ipsum eu, tempor venenatis tortor. Aliquam ullamcorper augue in semper laoreet. Fusce pellentesque ligula sit amet ante fringilla euismod. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus.

          Suspendisse viverra suscipit lorem, vel posuere metus posuere eget. Phasellus at lacinia quam. Nam et ante fermentum, venenatis libero eget, porttitor ex. Sed sit amet porta risus. Vivamus sed nibh at augue malesuada auctor. Sed in facilisis nibh. Curabitur varius est enim, a pharetra lectus faucibus sit amet. Donec congue elementum efficitur. Aenean nec enim at velit blandit tempus eu sed ligula.

          Vestibulum porttitor elit vitae ligula finibus sollicitudin. Vivamus lacinia vel arcu sed aliquam. Nunc aliquam quam at augue auctor malesuada. Integer id tristique tortor. Ut ut suscipit elit. Morbi vulputate aliquam lacus. Aliquam erat volutpat. Proin tristique sapien eget accumsan egestas. Mauris feugiat dolor orci, id venenatis metus egestas at. Nam non dictum dolor. Nunc in justo cursus diam lobortis euismod. Vivamus fermentum iaculis magna, non vulputate erat luctus quis. Fusce nec massa sit amet augue pellentesque mattis nec quis risus.

          Vivamus vitae bibendum turpis, eu lobortis odio. Vivamus quam tellus, elementum id rhoncus molestie, auctor quis felis. In vel quam cursus, luctus tellus ut, hendrerit lectus. Aenean vitae urna erat. Phasellus suscipit semper lacus, eu malesuada quam sodales quis. Mauris euismod vel nulla non ornare. Suspendisse dignissim sodales felis, in iaculis mi pulvinar at. Aenean neque sapien, lacinia eu tincidunt in, porta eget nibh. Aliquam ultrices arcu magna, a finibus felis pharetra in. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Aliquam ullamcorper mattis lacus nec imperdiet. Aenean vel sapien vitae dolor pellentesque scelerisque vitae a urna. Cras rutrum convallis nibh, et pharetra ipsum vestibulum sed. Etiam nec tincidunt erat, eu malesuada quam. Morbi sed sapien ultricies, molestie enim vel, malesuada dolor.

          Vivamus vel nisl ultrices risus faucibus rutrum non id metus. Fusce sagittis arcu sed pulvinar efficitur. Aliquam vulputate diam sed dictum luctus. Nulla fermentum molestie faucibus. Duis a venenatis diam. Morbi massa arcu, varius ac euismod at, vehicula a quam. Praesent ex nisl, placerat quis enim sit amet, iaculis lacinia urna. Phasellus pharetra enim mi, vitae tincidunt lectus eleifend at. Morbi rhoncus sem vel velit varius dapibus in quis nisl. Mauris vulputate tortor tortor, in tincidunt elit pharetra in. Donec in semper velit. Cras scelerisque velit finibus, tempor tortor in, scelerisque mi.
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Mauris tempus nisi nunc, eget vehicula tellus rutrum id. Fusce mollis nulla et est luctus egestas. Cras lorem tortor, dignissim sit amet imperdiet eu, venenatis vel sapien. Integer sit amet orci ex. Nunc nec lectus et nunc fringilla tincidunt venenatis ut erat. Nullam luctus non orci a porttitor. Sed dignissim non mi eu tempus. Integer feugiat, leo in blandit iaculis, justo nisl mollis sapien, eu ultricies magna mi a ex. Maecenas porttitor tincidunt risus, sed bibendum lacus consectetur ac. Duis id nunc sit amet nunc hendrerit feugiat. Fusce ante purus, iaculis ut ipsum eu, tempor venenatis tortor. Aliquam ullamcorper augue in semper laoreet. Fusce pellentesque ligula sit amet ante fringilla euismod. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus.

          Suspendisse viverra suscipit lorem, vel posuere metus posuere eget. Phasellus at lacinia quam. Nam et ante fermentum, venenatis libero eget, porttitor ex. Sed sit amet porta risus. Vivamus sed nibh at augue malesuada auctor. Sed in facilisis nibh. Curabitur varius est enim, a pharetra lectus faucibus sit amet. Donec congue elementum efficitur. Aenean nec enim at velit blandit tempus eu sed ligula.

          Vestibulum porttitor elit vitae ligula finibus sollicitudin. Vivamus lacinia vel arcu sed aliquam. Nunc aliquam quam at augue auctor malesuada. Integer id tristique tortor. Ut ut suscipit elit. Morbi vulputate aliquam lacus. Aliquam erat volutpat. Proin tristique sapien eget accumsan egestas. Mauris feugiat dolor orci, id venenatis metus egestas at. Nam non dictum dolor. Nunc in justo cursus diam lobortis euismod. Vivamus fermentum iaculis magna, non vulputate erat luctus quis. Fusce nec massa sit amet augue pellentesque mattis nec quis risus.

          Vivamus vitae bibendum turpis, eu lobortis odio. Vivamus quam tellus, elementum id rhoncus molestie, auctor quis felis. In vel quam cursus, luctus tellus ut, hendrerit lectus. Aenean vitae urna erat. Phasellus suscipit semper lacus, eu malesuada quam sodales quis. Mauris euismod vel nulla non ornare. Suspendisse dignissim sodales felis, in iaculis mi pulvinar at. Aenean neque sapien, lacinia eu tincidunt in, porta eget nibh. Aliquam ultrices arcu magna, a finibus felis pharetra in. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Aliquam ullamcorper mattis lacus nec imperdiet. Aenean vel sapien vitae dolor pellentesque scelerisque vitae a urna. Cras rutrum convallis nibh, et pharetra ipsum vestibulum sed. Etiam nec tincidunt erat, eu malesuada quam. Morbi sed sapien ultricies, molestie enim vel, malesuada dolor.

          Vivamus vel nisl ultrices risus faucibus rutrum non id metus. Fusce sagittis arcu sed pulvinar efficitur. Aliquam vulputate diam sed dictum luctus. Nulla fermentum molestie faucibus. Duis a venenatis diam. Morbi massa arcu, varius ac euismod at, vehicula a quam. Praesent ex nisl, placerat quis enim sit amet, iaculis lacinia urna. Phasellus pharetra enim mi, vitae tincidunt lectus eleifend at. Morbi rhoncus sem vel velit varius dapibus in quis nisl. Mauris vulputate tortor tortor, in tincidunt elit pharetra in. Donec in semper velit. Cras scelerisque velit finibus, tempor tortor in, scelerisque mi.
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Mauris tempus nisi nunc, eget vehicula tellus rutrum id. Fusce mollis nulla et est luctus egestas. Cras lorem tortor, dignissim sit amet imperdiet eu, venenatis vel sapien. Integer sit amet orci ex. Nunc nec lectus et nunc fringilla tincidunt venenatis ut erat. Nullam luctus non orci a porttitor. Sed dignissim non mi eu tempus. Integer feugiat, leo in blandit iaculis, justo nisl mollis sapien, eu ultricies magna mi a ex. Maecenas porttitor tincidunt risus, sed bibendum lacus consectetur ac. Duis id nunc sit amet nunc hendrerit feugiat. Fusce ante purus, iaculis ut ipsum eu, tempor venenatis tortor. Aliquam ullamcorper augue in semper laoreet. Fusce pellentesque ligula sit amet ante fringilla euismod. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus.

          Suspendisse viverra suscipit lorem, vel posuere metus posuere eget. Phasellus at lacinia quam. Nam et ante fermentum, venenatis libero eget, porttitor ex. Sed sit amet porta risus. Vivamus sed nibh at augue malesuada auctor. Sed in facilisis nibh. Curabitur varius est enim, a pharetra lectus faucibus sit amet. Donec congue elementum efficitur. Aenean nec enim at velit blandit tempus eu sed ligula.

          Vestibulum porttitor elit vitae ligula finibus sollicitudin. Vivamus lacinia vel arcu sed aliquam. Nunc aliquam quam at augue auctor malesuada. Integer id tristique tortor. Ut ut suscipit elit. Morbi vulputate aliquam lacus. Aliquam erat volutpat. Proin tristique sapien eget accumsan egestas. Mauris feugiat dolor orci, id venenatis metus egestas at. Nam non dictum dolor. Nunc in justo cursus diam lobortis euismod. Vivamus fermentum iaculis magna, non vulputate erat luctus quis. Fusce nec massa sit amet augue pellentesque mattis nec quis risus.

          Vivamus vitae bibendum turpis, eu lobortis odio. Vivamus quam tellus, elementum id rhoncus molestie, auctor quis felis. In vel quam cursus, luctus tellus ut, hendrerit lectus. Aenean vitae urna erat. Phasellus suscipit semper lacus, eu malesuada quam sodales quis. Mauris euismod vel nulla non ornare. Suspendisse dignissim sodales felis, in iaculis mi pulvinar at. Aenean neque sapien, lacinia eu tincidunt in, porta eget nibh. Aliquam ultrices arcu magna, a finibus felis pharetra in. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Aliquam ullamcorper mattis lacus nec imperdiet. Aenean vel sapien vitae dolor pellentesque scelerisque vitae a urna. Cras rutrum convallis nibh, et pharetra ipsum vestibulum sed. Etiam nec tincidunt erat, eu malesuada quam. Morbi sed sapien ultricies, molestie enim vel, malesuada dolor.

          Vivamus vel nisl ultrices risus faucibus rutrum non id metus. Fusce sagittis arcu sed pulvinar efficitur. Aliquam vulputate diam sed dictum luctus. Nulla fermentum molestie faucibus. Duis a venenatis diam. Morbi massa arcu, varius ac euismod at, vehicula a quam. Praesent ex nisl, placerat quis enim sit amet, iaculis lacinia urna. Phasellus pharetra enim mi, vitae tincidunt lectus eleifend at. Morbi rhoncus sem vel velit varius dapibus in quis nisl. Mauris vulputate tortor tortor, in tincidunt elit pharetra in. Donec in semper velit. Cras scelerisque velit finibus, tempor tortor in, scelerisque mi.
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Mauris tempus nisi nunc, eget vehicula tellus rutrum id. Fusce mollis nulla et est luctus egestas. Cras lorem tortor, dignissim sit amet imperdiet eu, venenatis vel sapien. Integer sit amet orci ex. Nunc nec lectus et nunc fringilla tincidunt venenatis ut erat. Nullam luctus non orci a porttitor. Sed dignissim non mi eu tempus. Integer feugiat, leo in blandit iaculis, justo nisl mollis sapien, eu ultricies magna mi a ex. Maecenas porttitor tincidunt risus, sed bibendum lacus consectetur ac. Duis id nunc sit amet nunc hendrerit feugiat. Fusce ante purus, iaculis ut ipsum eu, tempor venenatis tortor. Aliquam ullamcorper augue in semper laoreet. Fusce pellentesque ligula sit amet ante fringilla euismod. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus.
          <br><br><br>
          Suspendisse viverra suscipit lorem, vel posuere metus posuere eget. Phasellus at lacinia quam. Nam et ante fermentum, venenatis libero eget, porttitor ex. Sed sit amet porta risus. Vivamus sed nibh at augue malesuada auctor. Sed in facilisis nibh. Curabitur varius est enim, a pharetra lectus faucibus sit amet. Donec congue elementum efficitur. Aenean nec enim at velit blandit tempus eu sed ligula.

          Vestibulum porttitor elit vitae ligula finibus sollicitudin. Vivamus lacinia vel arcu sed aliquam. Nunc aliquam quam at augue auctor malesuada. Integer id tristique tortor. Ut ut suscipit elit. Morbi vulputate aliquam lacus. Aliquam erat volutpat. Proin tristique sapien eget accumsan egestas. Mauris feugiat dolor orci, id venenatis metus egestas at. Nam non dictum dolor. Nunc in justo cursus diam lobortis euismod. Vivamus fermentum iaculis magna, non vulputate erat luctus quis. Fusce nec massa sit amet augue pellentesque mattis nec quis risus.

          Vivamus vitae bibendum turpis, eu lobortis odio. Vivamus quam tellus, elementum id rhoncus molestie, auctor quis felis. In vel quam cursus, luctus tellus ut, hendrerit lectus. Aenean vitae urna erat. Phasellus suscipit semper lacus, eu malesuada quam sodales quis. Mauris euismod vel nulla non ornare. Suspendisse dignissim sodales felis, in iaculis mi pulvinar at. Aenean neque sapien, lacinia eu tincidunt in, porta eget nibh. Aliquam ultrices arcu magna, a finibus felis pharetra in. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Aliquam ullamcorper mattis lacus nec imperdiet. Aenean vel sapien vitae dolor pellentesque scelerisque vitae a urna. Cras rutrum convallis nibh, et pharetra ipsum vestibulum sed. Etiam nec tincidunt erat, eu malesuada quam. Morbi sed sapien ultricies, molestie enim vel, malesuada dolor.

          Vivamus vel nisl ultrices risus faucibus rutrum non id metus. Fusce sagittis arcu sed pulvinar efficitur. Aliquam vulputate diam sed dictum luctus. Nulla fermentum molestie faucibus. Duis a venenatis diam. Morbi massa arcu, varius ac euismod at, vehicula a quam. Praesent ex nisl, placerat quis enim sit amet, iaculis lacinia urna. Phasellus pharetra enim mi, vitae tincidunt lectus eleifend at. Morbi rhoncus sem vel velit varius dapibus in quis nisl. Mauris vulputate tortor tortor, in tincidunt elit pharetra in. Donec in semper velit. Cras scelerisque velit finibus, tempor tortor in, scelerisque mi.

        </div>
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

