<script setup lang="ts">
import { ref, computed } from 'vue'

const currentDate = ref(new Date())
const selectedDate = ref<Date | null>(null)

const months = [
    'Январь', 'Февраль', 'Март', 'Апрель', 'Май', 'Июнь',
    'Июль', 'Август', 'Сентябрь', 'Октябрь', 'Ноябрь', 'Декабрь'
]

const weekDays = ['Пн', 'Вт', 'Ср', 'Чт', 'Пт', 'Сб', 'Вс']

const calendarDays = computed(() => {
    const year = currentDate.value.getFullYear()
    const month = currentDate.value.getMonth()

    const firstDay = new Date(year, month, 1)
    const lastDay = new Date(year, month + 1, 0)

    const startDayOfWeek = firstDay.getDay() || 7 // Пн=1, Вс=7
    const daysInMonth = lastDay.getDate()

    const days: { date: number; isCurrentMonth: boolean; isWeekend: boolean }[] = []

    const prevMonthLastDay = new Date(year, month, 0).getDate()
    for (let i = startDayOfWeek - 1; i > 0; i--) {
        days.push({
            date: prevMonthLastDay - i + 1,
            isCurrentMonth: false,
            isWeekend: false
        })
    }

    for (let day = 1; day <= daysInMonth; day++) {
        const date = new Date(year, month, day)
        const dayOfWeek = date.getDay()
        const isWeekend = dayOfWeek === 0 || dayOfWeek === 6

        days.push({
            date: day,
            isCurrentMonth: true,
            isWeekend
        })
    }

    const remainingDays = 42 - days.length
    for (let day = 1; day <= remainingDays; day++) {
        days.push({
            date: day,
            isCurrentMonth: false,
            isWeekend: false
        })
    }

    return days
})

const currentMonthName = computed(() => {
    return months[currentDate.value.getMonth()]
})

const currentYear = computed(() => {
    return currentDate.value.getFullYear()
})

const goToPreviousMonth = () => {
    currentDate.value = new Date(currentDate.value.getFullYear(), currentDate.value.getMonth() - 1, 1)
}

const goToNextMonth = () => {
    currentDate.value = new Date(currentDate.value.getFullYear(), currentDate.value.getMonth() + 1, 1)
}

const selectDate = (day: typeof calendarDays.value[0]) => {
    if (day.isCurrentMonth) {
        selectedDate.value = new Date(currentDate.value.getFullYear(), currentDate.value.getMonth(), day.date)
    }
}

const isDateSelected = (day: typeof calendarDays.value[0]) => {
    if (!selectedDate.value || !day.isCurrentMonth) return false

    return (
        selectedDate.value.getDate() === day.date &&
        selectedDate.value.getMonth() === currentDate.value.getMonth() &&
        selectedDate.value.getFullYear() === currentDate.value.getFullYear()
    )
}
</script>

<template>
    <div class="calendar">
        <div class="calendar-header">
            <h2 class="calendar-title">{{ currentMonthName }} {{ currentYear }}</h2>
            <div class="calendar-nav">
                <button @click="goToPreviousMonth" class="calendar-nav-btn">
                    ‹
                </button>
                <button @click="goToNextMonth" class="calendar-nav-btn">
                    ›
                </button>
            </div>
        </div>

        <div class="calendar-weekdays">
            <div v-for="day in weekDays" :key="day" class="calendar-weekday">
                {{ day }}
            </div>
        </div>

        <div class="calendar-days">
            <div v-for="(day, index) in calendarDays" :key="index" @click="selectDate(day)" :class="[
                'calendar-day',
                { 'calendar-day--current': day.isCurrentMonth },
                { 'calendar-day--selected': isDateSelected(day) },
                { 'calendar-day--weekend': day.isWeekend && day.isCurrentMonth }
            ]">
                {{ day.date }}
            </div>
        </div>
    </div>
</template>

<style scoped>
.calendar {
    background: #F2F2F2;
    padding: 35px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
    width: 100%;
    border-radius: 9px;
}

.calendar-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
}

.calendar-title {
    font-style: normal;
    font-weight: 700;
    font-size: 20px;
    line-height: 24px;
    letter-spacing: 0.38px;
    color: #000000;
}

.calendar-nav {
    display: flex;
    gap: 8px;
}

.calendar-nav-btn {
    width: 35px;
    height: 35px;
    border: none;
    border: 1px solid #004636;
    background: #fcfcfc;
    border-radius: 8px;
    cursor: pointer;
    font-size: 30px;
    color: #686868;
    transition: all 0.2s;
    display: flex;
    align-items: center;
    justify-content: center;
}

.calendar-nav-btn:hover {
    background: #e8e8e8;
    color: #1a1a1a;
}

.calendar-weekdays {
    display: grid;
    grid-template-columns: repeat(7, 1fr);
    gap: 2px;
    margin-bottom: 4px;
}

.calendar-weekday {
    text-align: center;
    padding: 8px 0;

    font-family: 'Nunito Sans';
    font-style: normal;
    font-weight: 600;
    font-size: 12px;
    line-height: 16px;
    color: #004636;
}

.calendar-days {
    display: grid;
    grid-template-columns: repeat(7, 1fr);
    gap: 4px;
}

.calendar-day {
    aspect-ratio: 1;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 15px;
    cursor: default;
    color: #ccc;
    transition: all 0.2s;

    font-family: 'Nunito Sans';
    font-style: normal;
    font-weight: 600;
    font-size: 16px;
    line-height: 21px;
    letter-spacing: -0.32px;
}

.calendar-day--current {
    color: #1a1a1a;
    cursor: pointer;
}

.calendar-day--current:hover {
    background: #81a49f;
}

.calendar-day--selected {
    background: #43716B;
    color: #fff !important;

}

.calendar-day--weekend {
    color: #FF0000;
}

.calendar-day--weekend.calendar-day--selected {
    background: #43716B;
    color: #fff !important;
}
</style>