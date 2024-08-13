<template>
  <p class="text-2xl px-4 py-4 pb-2 bg-lime">Yayındaki İlanlarım</p>
  <hr />
  <div class="container mx-auto pt-4">
    <table class="min-w-full bg-white border border-gray-300">
      <thead class="bg-gray-200 h-4">
        <tr>
          <th class="w-3/12 border-r border-red-500"> </th>
          <th class="w-5/12 border-r border-red-500 text-center">İlan Başlığı</th>
          <th class="w-2/12 border-r border-red-500 text-center">m² (Brüt)</th>
          <th class="w-1/12 border-r border-red-500 text-center">Oda Sayısı</th>
          <th class="w-2/12 border-r border-red-500 text-center">Fiyat</th>
          <th class="w-2/12 border-r border-red-500 text-center">İlan Tarihi</th>
          <th class="w-2/12 border-r border-red-500 text-center">Konum</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td class="border-r border-red-500 min-w-full">
            <img src="/public/a.jpg" alt="İlan Resmi" class="bg-red-500">
          </td>
          <td class="border-r border-red-500 p-2">
            BEYLİKDÜZÜ VESADAN METROBÜS DURAĞINA KOMŞU 2+1 SATILIK ARAKAT!
          </td>
          <td class="border-r border-red-500 text-center p-2">200</td>
          <td class="border-r border-red-500 text-center p-2">3+1</td>
          <td class="border-r border-red-500 text-center p-2 text-red-600 font-bold">999.000.000 TL</td>
          <td class="border-r border-red-500 text-center p-2">06 Haziran 2024</td>
          <td class="border-r border-red-500 text-center p-2">Lefkoşa Göçmenköy</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script setup>

</script>