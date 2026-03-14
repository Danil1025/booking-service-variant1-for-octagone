<template>
    <div class="">
        <PreHeader>
            <Header class="preheader__bottom-header" />
        </PreHeader>
        <main>
            <div class="main-container">
                <div class="main">
                    <slot>
                        
                    </slot>

                    <div class="sidebar">
                        <Calendar />

                        <ActiveInvites />
                    </div>
                </div>
            </div>
        </main>
    </div>
</template>

<style scoped>
.preheader__bottom-header {
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
}

.main-container {
    max-width: 1720px;
    margin: 0 auto;
}

.main {
    padding-block: 50px;

    display: flex;
    justify-content: space-between;
    width: 100%;
}

.sidebar {
    display: flex;
    flex-direction: column;
    gap: 20px;

    width: 460px;
}
</style>