<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue';
import LogoIcon from '~/components/icons/LogoIcon.vue';
import Settings from '~/components/icons/Settings.vue';

const isProfileMenuOpen = ref(false);

const toggleProfileMenu = () => {
    isProfileMenuOpen.value = !isProfileMenuOpen.value;
};

const closeProfileMenu = () => {
    isProfileMenuOpen.value = false;
};


const handleClickOutside = (event: MouseEvent) => {
    const target = event.target as HTMLElement;
    if (!target.closest('.header')) {
        closeProfileMenu();
    }
};

onMounted(() => {
    document.addEventListener('click', handleClickOutside);
});

onUnmounted(() => {
    document.removeEventListener('click', handleClickOutside);
});
</script>

<template>
    <header class="header">
        <div class="preheader__bottom-header-container">
            <div class="preheader__bottom-header-content">
                <NuxtLink to="/" class="header__nav-icon-link">
                    <LogoIcon class="preheader__bottom-header-icon" />
                </NuxtLink>

                <ul class="preheader__bottom-header-ul">
                    <li class="preheader__bottom-header-ul-item">
                        <NuxtLink to="/equipment" class="preheader__bottom-header-ul-item-link">
                            Аппаратура
                        </NuxtLink>
                    </li>
                    <li class="preheader__bottom-header-ul-item">
                        <NuxtLink to="/people" class="preheader__bottom-header-ul-item-link">
                            Люди
                        </NuxtLink>
                    </li>
                    <li class="preheader__bottom-header-ul-item">
                        <NuxtLink to="/" class="preheader__bottom-header-ul-item-link">
                            Пространство
                        </NuxtLink>
                    </li>

                    <!-- Элемент Профиль с выпадающим меню -->
                    <li class="preheader__bottom-header-ul-item header__profile-item">
                        <button @click.stop="toggleProfileMenu"
                            class="preheader__bottom-header-ul-item-link header__profile-link" type="button"
                            aria-expanded="false">
                            Профиль
                            <img src="/images/profile-icon.png" alt="profile icon"
                                class="preheader__bottom-header-profile-icon">


                        </button>

                        <transition name="dropdown">
                            <div v-if="isProfileMenuOpen" class="header__profile-dropdown">
                                <ul class="header__profile-dropdown-list">
                                    <li>
                                        <div class="header__profile-info">
                                            <p class="header__profile-name">Иван Иванов</p>
                                            <NuxtLink to="/" class="header__profile-dropdown-item">
                                                <Settings class="header__settings-link" />
                                            </NuxtLink>
                                        </div>
                                    </li>
                                    <li>
                                        <p class="header__profile-email">example@yandex.ru</p>
                                    </li>
                                    <li>
                                        <Button>
                                            Выйти
                                        </Button>
                                    </li>
                                </ul>
                            </div>
                        </transition>
                    </li>
                </ul>
            </div>
        </div>
    </header>
</template>

<style scoped>
.header {
    width: 100%;
    padding-block: 19px;
    background: rgba(0, 0, 0, 0.5);
    position: relative;
}

.preheader__bottom-header-container {
    max-width: 1820px;
    margin: 0 auto;
}

.preheader__bottom-header-content {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.preheader__bottom-header-icon {
    width: 49px;
    height: 47px;
}

.preheader__bottom-header-ul {
    display: flex;
    align-items: center;
    gap: 134px;
    list-style: none;
    margin: 0;
    padding: 0;
}

.preheader__bottom-header-ul-item {
    position: relative;
}

.preheader__bottom-header-ul-item-link {
    font-weight: 600;
    font-size: 24px;
    line-height: 33px;
    color: #FFFFFF;
    background: none;
    border: none;
    cursor: pointer;
    display: flex;
    align-items: center;
    gap: 8px;
    transition: opacity 0.2s;
}

.router-link-exact-active {
    text-decoration: underline;
    text-underline-offset: 12px;
    text-decoration-thickness: 2px
}

.preheader__bottom-header-ul-item-link:hover {
    opacity: 0.7;
}

.header__profile-link {
    display: flex;
    align-items: center;
    gap: 35px;
}

.header__profile-dropdown {
    position: absolute;
    top: 100%;
    right: 0;
    margin-top: 10px;
    z-index: 1000;
    padding: 20px;
    background: #FFFFFF;
    box-shadow: 0px 0px 10px rgba(81, 114, 163, 0.2);
    border-radius: 10px;

}

.header__profile-dropdown-list {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 16px;
}

.header__profile-info {
    display: flex;
    align-items: center;
    gap: 16px;
}

.header__profile-name {
    font-weight: 600;
    font-size: 16px;
    line-height: 22px;

}

.header__settings-link {
    width: 14px;
    height: 14px;
    color: black;
}


.header__profile-email {
    font-style: normal;
    font-weight: 400;
    font-size: 14px;
    line-height: 19px;

}

.header__logout-btn {
    color: #FF4D4D;
}

.header__logout-btn:hover {
    background: rgba(255, 77, 77, 0.1);
}

.dropdown-enter-active,
.dropdown-leave-active {
    transition: opacity 0.2s ease, transform 0.2s ease;
}

.dropdown-enter-from,
.dropdown-leave-to {
    opacity: 0;
    transform: translateY(-10px);
}
</style>