<script setup>
import { ref } from 'vue';
import { Head, Link, router } from '@inertiajs/vue3';
import ApplicationMark from '@/Components/ApplicationMark.vue';
import Banner from '@/Components/Banner.vue';
import Dropdown from '@/Components/Dropdown.vue';
import DropdownLink from '@/Components/DropdownLink.vue';
import NavLink from '@/Components/NavLink.vue';
import ResponsiveNavLink from '@/Components/ResponsiveNavLink.vue';

defineProps({
    title: String,
});

const showingNavigationDropdown = ref(false);

const switchToTeam = (team) => {
    router.put(route('current-team.update'), {
        team_id: team.id,
    }, {
        preserveState: false,
    });
};

const logout = () => {
    router.post(route('logout'));
};
</script>

<template>
 <aside class="bg-white w-[260px] shadow-md px-2">
    <ul>
        <li v-for="item in 9" :key="item" class="bg-gray-400 rounded px-2 py-1 my-1">Menu {{ item }}</li>

        <li class="bg-gray-400 rounded px-2 py-1 my-1">
            Menu Dropdown 
            <ul>
                <li>Sub Menu</li>
                <li>Sub Menu</li>
                <li>Sub Menu</li>
                <li>Sub Menu</li>
                <li>Sub Menu</li>
            </ul>
        </li>
    </ul>
 </aside>
</template>
