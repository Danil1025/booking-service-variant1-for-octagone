<script setup lang="ts">
import { ref } from 'vue';

const isModalOpen = ref(false);

const selectedPlace = ref('Выберите мероприятие');

const checkPlaceholder = (event: Event) => {
    const select = event.target as HTMLSelectElement;
    select.classList.toggle('has-placeholder', select.value === 'Выберите мероприятие');
};

</script>

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
                    <Button @click="isModalOpen = true">Забронировать</Button>
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
                    <Button @click="isModalOpen = true">Забронировать</Button>
                    <Button variant="white">Подробнее</Button>
                </div>
            </div>
        </div>

        <Modal v-model="isModalOpen" title="Бронирование">
            <div class="booking-form">
                <div class="booking-area">
                    <p class="booking-label">Мероприятие:</p>
                    <select name="booking-place" class="booking-field" id="booking-place" v-model="selectedPlace"
                        @change="checkPlaceholder"
                        :class="{ 'disabled': selectedPlace === 'Выберите мероприятие' }">
                        <option class="disabled" value="Выберите мероприятие" selected disabled>Выберите
                            мероприятие</option>
                        <option value="Коворкинг ИРНИТУ">Коворкинг ИРНИТУ</option>
                        <option value="Переговорная ИРНИТУ">Переговорная ИРНИТУ</option>
                    </select>
                </div>

                <div class="booking-area">
                    <p class="booking-label">Выберите время мероприятия:</p>
                    <div class="booking-dates">
                        <p class="booking-date">08.00 - 09.00</p>
                        <p class="booking-date">09.00 - 10.00</p>
                        <p class="booking-date booking-green">10.00 - 11.00</p>
                        <p class="booking-date booking-green">11.00 - 12.00</p>
                        <p class="booking-date">12.00 - 13.00</p>
                        <p class="booking-date booking-green">13.00 - 14.00</p>
                        <p class="booking-date">14.00 - 15.00</p>
                        <p class="booking-date">15.00 - 16.00</p>
                        <p class="booking-date">16.00 - 17.00</p>
                        <p class="booking-date">17.00 - 18.00</p>
                        <p class="booking-date">18.00 - 19.00</p>
                        <p class="booking-date">19.00 - 20.00</p>
                    </div>
                </div>

                <div class="booking-area">
                    <p class="booking-label">Ответственные лица:</p>
                    <div class="responsible-people booking-field">
                        <p class="responsible-human">Иван Иванов</p>
                        <p class="responsible-human">Елена Иванова</p>
                        +
                    </div>
                </div>

                <div class="booking-area">
                    <p class="booking-label">Дополнительная информация</p>
                    <input placeholder="Выберите мероприятие" type="text" class="booking-field">
                </div>

                <div class="booking-actions">
                    <Button class="booking-button" @click="isModalOpen = false">Забронировать</Button>
                    <Button class="booking-cancel" variant="white" @click="isModalOpen = false">Отмена</Button>
                </div>
            </div>
        </Modal>

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

.booking-form {
    display: flex;
    flex-direction: column;
    gap: 16px;

}

.booking-area {
    display: flex;
    flex-direction: column;
    gap: 8px;
}

.booking-label {
    font-weight: 400;
    font-size: 12px;
    line-height: 16px;
}

.booking-field {
    width: 100%;
    border: none;
    padding-bottom: 8px;
    border-bottom: 1px solid #686868;
    outline: none;
}

option {
    font-weight: 500;
    font-size: 14px;
    line-height: 19px;
    color: black;
}

.disabled {
    font-weight: 400;
    color: #686868;
}

.booking-dates {
    display: flex;
    flex-wrap: wrap;

    gap: 14px;
}

.booking-date {
    width: 130px;
    height: 39px;
    display: flex;
    justify-content: center;
    align-items: center;

    background: #DCE7E6;
    border-radius: 6px;

    font-weight: 400;
    font-size: 14px;
    line-height: 19px;

    cursor: default;
}

.booking-green {
    background: #86AEAA;
    font-weight: 700;
    color: #FFFFFF;
}

.responsible-people {
    display: flex;
    gap: 10px;
    align-items: center;

    cursor: default;
}

.responsible-human {
    padding: 5px 16px;
    background: #86AEAA;
    border-radius: 5px;

    font-weight: 700;
    font-size: 12px;
    line-height: 16px;
    color: #FFFFFF;
}

.booking-actions {
    display: flex;
    justify-content: space-between;
}

.booking-button {
    width: 72%;
}

.booking-cancel {
    width: 25%;
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>