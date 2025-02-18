<script setup lang="ts">
import {ref} from "vue";
import MegaMenu from 'primevue/megamenu';

const items = ref([
  {
    label: 'کوچینگ',
    icon: 'pi pi-lightbulb',
    items: [
      [
        {
          items: [{label: 'کوچینگ کسب و کار'}]
        }
      ],
      [
        {
          items: [{label: 'کوچینگ زندگی'}]
        },
      ],
      [
        {
          items: [{label: 'کوچینگ سرمایه'}]
        }
      ],
    ]
  },
  {
    label: 'توسعه فردی',
    icon: 'pi pi-face-smile',
    items: [
      [
        {
          items: [{label: 'تغییر شخصیت'}]
        }
      ],
      [
        {
          items: [{label: 'تغییر ذهنیت'}]
        }
      ],
      [
        {
          items: [{label: 'باور های کوانتومی'}]
        }
      ],
      [
        {
          items: [{label: 'مراقبه توان بخشی'}]
        }
      ]
    ]
  },
  {
    label: 'فناوری',
    icon: 'pi pi-desktop',
    items: [
      [
        {
          label: 'برنامه نویسی وب',
          items: [{label: 'Laravel'}, {label: 'Vue.js'}, {label: '.Net'}, {label: 'React.js'}]
        }
      ],
      [
        {
          label: 'برنامه نویسی اندروید',
          items: [{label: 'Flutter'}, {label: 'Java'}, {label: 'React Native'}]
        }
      ],
      [
        {
          label: 'Dev Ops',
          items: [{label: 'داکر'}, {label: 'لینوکس'}]
        }
      ],
      [
        {
          label: 'هک و امنیت',
          items: [{label: 'پاینتون برای امنیت'}, {label: 'شبکه'}, {label: 'JS برای امنیت'}]
        }
      ]
    ]
  }
]);


</script>
<template>
  <div class="card z-[100]">
    <MegaMenu
        :model="items"
    />
  </div>
</template>

<style scoped>
::v-deep(.p-megamenu) {
  background-color: oklch(0.274 0.006 286.033) !important;
  border-radius: 0px;
  border: none !important;
}

::v-deep(.p-megamenu-overlay) {
  border: none !important;
  margin-top: 1rem !important;
}

::v-deep(.p-megamenu .p-menuitem) {
  color: #fff !important;
  background-color: oklch(0.21 0.006 285.885) !important;
  border: none !important;
}

::v-deep(.p-megamenu .p-menuitem:hover) {
  background-color: #334155 !important;
}
</style>

