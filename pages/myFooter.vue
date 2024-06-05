<script setup lang="ts">
import { ref } from 'vue';

const active = ref('araba');

const setActive = (menu: string) => {
  active.value = menu;
};
const links = [{
  label: 'Biz',
  children: [{
    label: 'Hakkımızda',
    to: 'hakkimizda',
    target: '_self'
  }, {
    label: 'İletişim',
    to: 'iletisim',
    target: '_self'
  }, {
    label: 'Sıkça Sorulan Sorular',
    to: 'sikca_sorulan_sorular',
    target: '_self'
  }, {
    label: 'Site Haritası',
    to: 'site_haritasi',
    target: '_self'
  }]
}, {
  label: 'Bireysel Üyelik',
  children: [{
    label: 'Bireysel Üyelik Sözleşmesi',
    to: 'bireysel_uyelik_sozlesmesi',
    target: '_self'
  }, {
    label: 'İlan Kuralları',
    to: 'ilan_kurallari',
    target: '_self'
  }, {
    label: 'Gizlilik Politikası',
    to: 'gizlilik_politikasi',
    target: '_self'
  }, {
    label: 'Yardım',
    to: 'gizlilik_politikasi',
    target: '_self'
  }]
}, {
  label: 'Kurumsal Üyelik',
  children: [{
    label: 'Kurumsal Üyelik Sözleşmesi',
    to: 'kurumsal_uyelik_sozlesmesi',
    target: '_self'
  }, {
    label: 'Galeri Üyelik Kuralları',
    to: 'iletisim',
    target: '_self'
  }, {
    label: 'Rent a Car Üyelik Kuralları',
    to: 'iletisim',
    target: '_self'
  }, {
    label: 'Gizlilik Politikası',
    to: 'iletisim',
    target: '_self'
  }, {
    label: 'Yardım',
    to: 'iletisim',
    target: '_self'
  }]
}, {
  label: 'Bizi Takip Edin',
  children: [{
    label: 'Instagram: @adapazarim',
    to: 'iletisim',
    target: '_self'
  }, {
    label: 'Facebook: @adapazarim',
    to: 'iletisim',
    target: '_self'
  }, {
    label: 'Twitter: @adapazarim',
    to: 'iletisim',
    target: '_self'
  }, {
    label: 'Youtube: @adapazarim',
    to: 'hakkimizda',
    target: '_self'
  }]
}]
</script>

<template>
  <UFooterColumns :links="links" class="footer_ui"></UFooterColumns>

  <p class="footer_aciklama">Copyright © 2024 adapazarim.com | Yasirin Şirketi Ltd.Şti<br />
    Bu internet sitesinin kullanıcıları Kullanım Koşulları ve Gizlilik Politikası ile
    Bireysel
    Üyelik Sözleşmesi veya Kurumsal Üyelik Sözleşmesi 'ni kabul etmiş sayılırlar
    Adapazarim.com'da kullanıcılar tarafından oluşturulan bütün içerikler, bilgi ve yorumların yayınlanması ve
    doğruluğu
    ile ilgili tüm yasal yükümlülükler içeriği oluşturan kullanıcıya aittir. İlanlara ait içeriklerin yorum ve
    bilgilerin yanlışlık, eksiklik veya yasalarla düzenlenmiş kurallara aykırılığından dolayı kktcarabam.com asla
    sorumlu tutulamaz. İlanlarla ilgili sorularınızı ilan sahipleriyle iletişime geçip sorabilirsiniz.</p>
  <p class="footer_copyright">Copyright Droix & Gravis © {{ new Date().getFullYear() }}</p>

</template>

<style>
.footer_ui {
  background-color: #332D2D;
  padding: 2rem 20rem;
  display: flex;
  flex-direction: column;
  color: white;
}

.footer_ui a {
  color: rgb(209 213 219 / var(--tw-text-opacity));
  font-size: 1rem;
}

.footer_ui a:hover {
  color: white;
}

.footer_ui h3 {
  color: white;
  font-size: 1rem;
}

.footer_aciklama {
  padding: 0rem 1rem 1rem 2rem;
  background-color: #332D2D;
  color: white;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 0.8rem;

}

.footer_copyright {
  background-color: #292424;
  text-align: center;
  color: white;
}
</style>