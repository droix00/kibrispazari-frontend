<template>
    <!-- KAYNAK: https://github.com/lloydtao/django-nuxt-social-crud/blob/main/frontend/frontend/components/LoginForm.vue -->
    <div class="login_content">
        <div class="photo_left_layout">
            <img src="public/oturan_kadin_cizimi.png" />
        </div>
        <div class="login_right_layout">
            <div class="mx-auto flex w-full max-w-sm flex-col">
                <h1 class="mt-8 text-2xl font-semibold text-gray-700 lg:mt-0">
                    Yeni bir deneyim için hazır mısınız?
                </h1>
                <p class="mt-2 text-sm text-gray-400">Bize katılacak olmanıza seviniyoruz.</p>
                <p class="mt-5 text-sm font-semibold text-gray-500">Adı Soyadı *</p>
                <input class="mt-1 rounded border py-1 px-3 text-lg shadow" />
                <p class="mt-5 text-sm font-semibold text-gray-500">E-mail *</p>
                <input class="mt-1 rounded border py-1 px-3 text-lg shadow" />
                <p class="mt-5 text-sm font-semibold text-gray-500">Cep Telefonu *</p>
                <input class="mt-1 rounded border py-1 px-3 text-lg shadow" />
                <p class="mt-5 text-sm font-semibold text-gray-500">Şifre *</p>
                <input class="mt-1 rounded border py-1 px-3 text-lg shadow" type="password" />
                <div class="mt-5 flex items-center">
                    <input class="mr-2 align-middle text-sm text-sm" type="checkbox" />
                    <p class="text-sm font-semibold text-gray-500"><a href="" class="text-[#F8818C]">Üyelik Sözleşmesi'ni okudum</a>, anladım.</p>
                </div>
                <div class="mt-5 flex items-center">
                    <input class="mr-2 align-middle text-sm text-sm" type="checkbox" />
                    <p class="text-sm font-semibold text-gray-500"><a href="" class="text-[#F8818C]">KVKK'yı</a> kabul ediyorum.</p>
                </div>
                <div class="mt-5 flex items-center">
                    <input class="mr-2 align-middle text-sm text-sm" type="checkbox" />
                    <p class="text-sm font-semibold text-gray-500">Kampanyalardan haberdar olmak istiyorum.</p>
                </div>
                <button
                    class="mt-5 rounded border bg-indigo-400 py-2 px-5 text-sm text-sm font-semibold text-gray-50 shadow hover:bg-indigo-500">
                    Kayıt Ol
                </button>
                <button class="mt-3 rounded border bg-white py-2 px-5 shadow hover:bg-gray-100">
                    <div class="flex items-center justify-center space-x-2">
                        <GitHubLogo />
                        <span class="text-sm font-semibold text-gray-700">Google ile Kayıt Ol</span>
                    </div>
                </button>
                <div class="mt-8 flex items-center space-x-1">
                    <p class="text-sm font-semibold text-gray-500">Zaten bir hesabınız mı var?</p>
                    <a href="#" class="text-sm font-semibold text-indigo-400 hover:text-indigo-500"><router-link to="girisyap" class="header__nav-link">Giriş Yap</router-link></a>
                </div>
            </div>
        </div>
    </div>
    <myFooter />
</template>
<script>
import myFooter from '~/pages/myFooter.vue'; // Header bileşenini içeri aktar
export default {
    components: {
        myFooter // Footer bileşenini kullanılabilir hale getir
    }
}
</script>
<style>
.login_content {
    display: flex;
    margin: 1%;
}

.photo_left_layout {
    flex: 10;
    background-color: #F9FAFB;
    border-radius: 3% 0% 0% 3%;
    box-shadow: rgba(0, 0, 0, 0.25) -8px 14px 28px;
}

.photo_left_layout img {
    background-size: cover;
    height: 90%;
    float: right;
}

.login_right_layout {
    flex: 9;
    padding: 4% 0% 3% 0%;
    border-radius: 0% 3% 3% 0%;
    box-shadow: rgba(0, 0, 0, 0.25) 8px 14px 28px;
}
</style>
