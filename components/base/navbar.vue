<script setup>
const route = useRoute()

const links = [
  [{
    label: 'Login',
    icon: 'i-heroicons-home',
    to: '/login'
  }, {
    label: 'Horizontal Navigation',
    icon: 'i-heroicons-chart-bar',
    to: `${route.path.startsWith('/dev') ? '/dev' : ''}/components/horizontal-navigation`
  }, {
    label: 'Command Palette',
    icon: 'i-heroicons-command-line',
    to: '/components/command-palette'
  }], [{
    label: 'Examples',
    icon: 'i-heroicons-light-bulb'
  }, {
    label: 'Help',
    icon: 'i-heroicons-question-mark-circle'
  }]
]
</script>

<template>
  <UContainer>
    <UHorizontalNavigation :links="links" class="border-b border-gray-200 dark:border-gray-800" />
  </UContainer>
</template>
