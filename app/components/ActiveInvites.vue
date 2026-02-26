<template>
    <div class="active-invites">
        <h3 class="active-invites__h3">Активные приглашения</h3>

        <div class="active-invites__cards">
            <div class="active-invites__card">
                <p class="active-invites__card-p">Съёмки в первомайском</p>
                <div class="active-invites__card-info">
                    <p class="active-invites__card-info-element">10.00 - 12.00</p>
                    <p class="active-invites__card-info-element">Иванов И. В.</p>
                    <p class="active-invites__card-info-element">Фотограф</p>
                </div>
                <div class="active-invites__card-btns">
                    <Button>Подробнее</Button>
                    <Button variant="white">Отклонить</Button>
                </div>
            </div>
            <div class="active-invites__card">
                <p class="active-invites__card-p">Съёмки в первомайском</p>
                <div class="active-invites__card-info">
                    <p class="active-invites__card-info-element">10.00 - 12.00</p>
                    <p class="active-invites__card-info-element">Иванов И. В.</p>
                    <p class="active-invites__card-info-element">Фотограф</p>
                </div>
                <div class="active-invites__card-btns">
                    <Button>Подробнее</Button>
                    <Button variant="white">Отклонить</Button>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
.active-invites__h3 {
    font-weight: 600;
    font-size: 20px;
    line-height: 27px;

    margin-bottom: 16px;
}

.active-invites__cards {
    display: flex;
    flex-direction: column;
    gap: 16px;
}

.active-invites__card {
    padding: 30px;
    width: 100%;

    display: flex;
    flex-direction: column;
    align-items: start;
    gap: 16px;

    background: #F2F2F2;
    border-radius: 10px;
}

.active-invites__card-p {
    font-weight: 600;
    font-size: 20px;
    line-height: 27px;
}

.active-invites__card-info {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
}

.active-invites__card-info-element {
    padding: 5px 16px;
    background: #86AEAA;
    border-radius: 5px;

    font-weight: 700;
    font-size: 14px;
    line-height: 19px;
    color: #FFFFFF;

    cursor: default;
}

.active-invites__card-btns {
    display: flex;
    gap: 10px;
}
</style>