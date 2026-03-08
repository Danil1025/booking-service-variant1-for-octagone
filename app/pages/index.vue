<template>
    <div class="space-cards">
        <div class="space-card">
            <div class="space-card-top">
                <div class="space-card-top__inf">
                    <p class="space-card-top__inf-p">Фото</p>
                    <p class="space-card-top__inf-p">Информация</p>
                </div>
                <p class="space-card-top__name">Коворкинг ИРНИТУ</p>
            </div>
            <div class="space-card-bottom">
                <div class="space-card-bottom__dates">
                    <p class="space-card-bottom__date">08.00 - 09.00</p>
                    <p class="space-card-bottom__date">09.00 - 10.00</p>
                    <p class="space-card-bottom__date green">10.00 - 11.00</p>
                    <p class="space-card-bottom__date green">11.00 - 12.00</p>
                    <p class="space-card-bottom__date">12.00 - 13.00</p>
                    <p class="space-card-bottom__date green">13.00 - 14.00</p>
                    <p class="space-card-bottom__date">14.00 - 15.00</p>
                    <p class="space-card-bottom__date">15.00 - 16.00</p>
                    <p class="space-card-bottom__date">16.00 - 17.00</p>
                    <p class="space-card-bottom__date">17.00 - 18.00</p>
                    <p class="space-card-bottom__date">18.00 - 19.00</p>
                    <p class="space-card-bottom__date">19.00 - 20.00</p>
                </div>
                <div class="space-card-bottom__buttons">
                    <Button>Забронировать</Button>
                    <Button variant="white">Подробнее</Button>
                </div>
            </div>
        </div>
        <div class="space-card">
            <div class="space-card-top twice">
                <div class="space-card-top__inf">
                    <p class="space-card-top__inf-p">Фото</p>
                    <p class="space-card-top__inf-p">Информация</p>
                </div>
                <p class="space-card-top__name">Переговорная ИРНИТУ</p>
            </div>
            <div class="space-card-bottom">
                <div class="space-card-bottom__dates">
                    <p class="space-card-bottom__date">08.00 - 09.00</p>
                    <p class="space-card-bottom__date">09.00 - 10.00</p>
                    <p class="space-card-bottom__date green">10.00 - 11.00</p>
                    <p class="space-card-bottom__date green">11.00 - 12.00</p>
                    <p class="space-card-bottom__date">12.00 - 13.00</p>
                    <p class="space-card-bottom__date green">13.00 - 14.00</p>
                    <p class="space-card-bottom__date">14.00 - 15.00</p>
                    <p class="space-card-bottom__date">15.00 - 16.00</p>
                    <p class="space-card-bottom__date">16.00 - 17.00</p>
                    <p class="space-card-bottom__date">17.00 - 18.00</p>
                    <p class="space-card-bottom__date">18.00 - 19.00</p>
                    <p class="space-card-bottom__date">19.00 - 20.00</p>
                </div>
                <div class="space-card-bottom__buttons">
                    <Button>Забронировать</Button>
                    <Button variant="white">Подробнее</Button>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
.space-cards {
    display: flex;
    flex-direction: column;
    gap: 45px;
}

.space-card {
    max-width: 1204px;
    overflow: hidden;
    border-radius: 10px;
}

.space-card-top {
    width: 1204px;
    background-image: url('/images/space-card1.png');
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;

    padding: 16px;
}

.twice {
    background-image: url('/images/space-card2.png');
}

.space-card-top__inf {
    display: flex;
    justify-content: start;
    justify-self: flex-start;
    align-items: center;
    gap: 25px;
}

.space-card-top__inf-p {
    padding: 8px 25px;
    background: #FFFFFF;
    border-radius: 6px;
    font-weight: 400;
    font-size: 14px;
    line-height: 19px;
}

.space-card-top__name {
    font-style: normal;
    font-weight: 600;
    font-size: 20px;
    line-height: 27px;

    padding: 8px 20px;
    background: #FFFFFF;
    border-radius: 5px;

    width: fit-content;

    margin-top: 155px;
}

.space-card-bottom {
    width: 100%;
    display: flex;
    gap: 30px;
    padding: 16px;
    background: #F2F2F2;
}

.space-card-bottom__dates {
    display: flex;
    flex-wrap: wrap;
    gap: 13.6px;
}

.space-card-bottom__date {
    width: 145px;
    height: 39px;
    display: flex;
    justify-content: center;
    align-items: center;
    background: #DCE7E6;
    border-radius: 6px;
    font-weight: 400;
    font-size: 14px;
    line-height: 19px;
}

.green {
    font-weight: 700;
    color: #FFFFFF;
    background: #86AEAA;
}

.space-card-bottom__buttons {
    display: flex;
    flex-direction: column;
    gap: 13.6px;
}
</style>