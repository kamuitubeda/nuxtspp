<script setup>
import { ref } from 'vue';
import AppMenuItem from './AppMenuItem.vue';
const model = ref([
    {
        label: 'Home',
        items: [{ label: 'Dashboard', icon: 'pi pi-fw pi-home', to: '/' }]
    },
    {
        label: 'Manajemen Santri',
        items: [
            {
                label: 'Kelas',
                icon: 'pi pi-fw pi-building',
                to: '/kelas'
            },
            {
                label: 'Santri',
                icon: 'pi pi-fw pi-id-card',
                to: '/santri'
            }
        ]
    },
    {
        label: 'Manajemen Keuangan',
        items: [
            {
                label: 'Rekening',
                icon: 'pi pi-fw pi-book',
                to: '/rekening'
            },
            {
                label: 'Tagihan',
                icon: 'pi pi-fw pi-credit-card',
                to: '/tagihan'
            }
        ]
    },
    {
        label: 'Laporan',
        items: [
            {
                label: 'Harian',
                icon: 'pi pi-fw pi-file-export',
                to: '/laporan/harian'
            },
            {
                label: 'Bulanan',
                icon: 'pi pi-fw pi-file-export',
                to: '/laporan/bulanan'
            }
        ]
    },
    {
        label: 'Lain-lain',
        items: [
            {
                label: 'Pegawai',
                icon: 'pi pi-fw pi-user',
                to: '/pegawai'
            },
            {
                label: 'Pengaturan',
                icon: 'pi pi-fw pi-wrench',
                to: '/pengaturan'
            }
        ]
    }
]);
</script>

<template>
    <ul class="layout-menu">
        <template v-for="(item, i) in model" :key="item">
            <app-menu-item v-if="!item.separator" :item="item" :index="i"></app-menu-item>
            <li v-if="item.separator" class="menu-separator"></li>
        </template>
    </ul>
</template>

<style lang="scss" scoped></style>
