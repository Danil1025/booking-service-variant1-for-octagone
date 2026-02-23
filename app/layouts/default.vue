<script setup lang="ts">
import LogoIcon from '~/components/icons/LogoIcon.vue';
import TextLogo from '~/components/icons/TextLogo.vue';
</script>

<template>
    <div class="">
        <div class="preheader">
            <div class="preheader__content">
                <div class="preheader__logo">
                    <div class="full-logo">
                        <LogoIcon />
                        <TextLogo />
                    </div>
                    <p class="preheader__logo-text">
                        Сервис бронирования ресурсов
                    </p>
                </div>
                <div class="preheader__auth-btns">
                    <NuxtLink to="/" class="preheader__auth-btn">
                        Вход
                    </NuxtLink>
                    <NuxtLink to="/" class="preheader__auth-btn">
                        Регистрация
                    </NuxtLink>
                </div>
                <p class="preheader__slogan">
                    Рыбатекст используется дизайнерами, проектировщиками и фронтендерами, когда нужно быстро заполнить
                    макеты или прототипы содержимым. Это тестовый контент, который не должен нести никакого смысла, лишь
                    показать наличие самого текста или продемонстрировать типографику в деле.
                </p>
            </div>
            <!-- <header class="preheader__bottom-header">
                
            </header> -->
            <Header class="preheader__bottom-header"/>
        </div>
        <!-- <Header/> -->
        <main>
            <slot></slot>
        </main>
    </div>
</template>

<style scoped>
.preheader {
    background-image: url("/images/background.png");
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;
    height: 110dvh;
    width: 100%;

    position: relative;
}

.preheader__content {
    padding-top: 25dvh;
}

.preheader__bottom-header {
    /* Прижимаем к низу */
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;

    
}

.preheader__logo {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 63px;
}

.full-logo {
    display: flex;
    align-items: center;
    gap: 31px;
}

.preheader__logo-text {
    max-width: 796px;
    font-weight: 400;
    font-size: 64px;
    line-height: 87px;
    color: #FFFFFF;
}

.preheader__auth-btns {
    margin-top: 61px;
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 32px;
}

.preheader__auth-btn {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    padding: 10px 60px;
    background: #FFFFFF;
    border-radius: 47px;
    font-weight: 600;
    font-size: 32px;
    line-height: 44px;
    color: #000000;
    transition-duration: 0.2s;
}

.preheader__auth-btn:hover {
    box-shadow: 0px 0px 20px rgba(255, 255, 255, 0.5);
}

.preheader__slogan {
    text-align: center;
    margin: 0 auto;
    margin-top: 124px;
    max-width: 921px;
    font-weight: 600;
    font-size: 24px;
    line-height: 33px;
    color: #FFFFFF;
}
</style>