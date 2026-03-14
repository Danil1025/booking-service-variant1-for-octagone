<template>
    <div class="people">
        <div class="controls">
            <div class="filters">
                <div class="search-filter filter">
                    <input type="text" class="search-input" placeholder="Поиск">
                    <svg width="18" height="18" viewBox="0 0 18 18" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path
                            d="M8.25 14.25C11.5637 14.25 14.25 11.5637 14.25 8.25C14.25 4.93629 11.5637 2.25 8.25 2.25C4.93629 2.25 2.25 4.93629 2.25 8.25C2.25 11.5637 4.93629 14.25 8.25 14.25Z"
                            stroke="black" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" />
                        <path d="M15.75 15.75L12.4875 12.4875" stroke="black" stroke-width="2" stroke-linecap="round"
                            stroke-linejoin="round" />
                    </svg>
                </div>

                <div class="select-filter filter">
                    <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path d="M2.66675 4H13.3334M2.66675 8H9.33341M2.66675 12H5.33341" stroke="black"
                            stroke-width="2" stroke-linecap="round" stroke-linejoin="round" />
                    </svg>
                    <select name="text-filter" id="text-filter" class="text-filter">
                        <option selected value="По алфавиту">По алфавиту</option>
                        <option value="По популярности">По популярности</option>
                    </select>
                </div>

            </div>
            <p class="add-people filter">Добавить <svg width="16" height="16" viewBox="0 0 16 16" fill="none"
                    xmlns="http://www.w3.org/2000/svg">
                    <path d="M3 8L13 8" stroke="black" stroke-linecap="round" />
                    <path d="M8 3L8 13" stroke="black" stroke-linecap="round" />
                </svg>
            </p>
        </div>
        <div class="people-cards">
            <div class="people-card">
                <div class="people-image">
                    <img src="/images/people1.png" alt="" class="people-img">
                    <p class="people-profession">Фотограф</p>
                </div>
                <div class="people-text">
                    <p class="people-name">Иван Иванов</p>
                    <p class="people-desc">Высококачественная видеосъёмка и аэросъёмка: доступные цены, профессиональное
                        оборудование и опытные специалисты</p>
                    <div class="people-btns">
                        <Button class="people-btn">Пригласить</Button>
                        <Button class="people-btn" variant="white">Подробнее</Button>
                    </div>
                </div>
            </div>
            <div class="people-card">
                <div class="people-image">
                    <img src="/images/people2.png" alt="" class="people-img">
                    <p class="people-profession">Фотограф</p>
                </div>
                <div class="people-text">
                    <p class="people-name">Анастасия Ремогузина</p>
                    <p class="people-desc">Высококачественная видеосъёмка и аэросъёмка: доступные цены, профессиональное
                        оборудование и опытные специалисты</p>
                    <div class="people-btns">
                        <Button class="people-btn">Пригласить</Button>
                        <Button class="people-btn" variant="white">Подробнее</Button>
                    </div>
                </div>
            </div>
            <div class="people-card">
                <div class="people-image">
                    <img src="/images/people1.png" alt="" class="people-img">
                    <p class="people-profession">Фотограф</p>
                </div>
                <div class="people-text">
                    <p class="people-name">Иван Иванов</p>
                    <p class="people-desc">Высококачественная видеосъёмка и аэросъёмка: доступные цены, профессиональное
                        оборудование и опытные специалисты</p>
                    <div class="people-btns">
                        <Button class="people-btn">Пригласить</Button>
                        <Button class="people-btn" variant="white">Подробнее</Button>
                    </div>
                </div>
            </div>
            <div class="people-card">
                <div class="people-image">
                    <img src="/images/people2.png" alt="" class="people-img">
                    <p class="people-profession">Фотограф</p>
                </div>
                <div class="people-text">
                    <p class="people-name">Анастасия Ремогузина</p>
                    <p class="people-desc">Высококачественная видеосъёмка и аэросъёмка: доступные цены, профессиональное
                        оборудование и опытные специалисты</p>
                    <div class="people-btns">
                        <Button class="people-btn">Пригласить</Button>
                        <Button class="people-btn" variant="white">Подробнее</Button>
                    </div>
                </div>
            </div>
            <div class="people-card">
                <div class="people-image">
                    <img src="/images/people1.png" alt="" class="people-img">
                    <p class="people-profession">Фотограф</p>
                </div>
                <div class="people-text">
                    <p class="people-name">Иван Иванов</p>
                    <p class="people-desc">Высококачественная видеосъёмка и аэросъёмка: доступные цены, профессиональное
                        оборудование и опытные специалисты</p>
                    <div class="people-btns">
                        <Button class="people-btn">Пригласить</Button>
                        <Button class="people-btn" variant="white">Подробнее</Button>
                    </div>
                </div>
            </div>
            <div class="people-card">
                <div class="people-image">
                    <img src="/images/people2.png" alt="" class="people-img">
                    <p class="people-profession">Фотограф</p>
                </div>
                <div class="people-text">
                    <p class="people-name">Анастасия Ремогузина</p>
                    <p class="people-desc">Высококачественная видеосъёмка и аэросъёмка: доступные цены, профессиональное
                        оборудование и опытные специалисты</p>
                    <div class="people-btns">
                        <Button class="people-btn">Пригласить</Button>
                        <Button class="people-btn" variant="white">Подробнее</Button>
                    </div>
                </div>
            </div>
            <div class="people-card">
                <div class="people-image">
                    <img src="/images/people1.png" alt="" class="people-img">
                    <p class="people-profession">Фотограф</p>
                </div>
                <div class="people-text">
                    <p class="people-name">Иван Иванов</p>
                    <p class="people-desc">Высококачественная видеосъёмка и аэросъёмка: доступные цены, профессиональное
                        оборудование и опытные специалисты</p>
                    <div class="people-btns">
                        <Button class="people-btn">Пригласить</Button>
                        <Button class="people-btn" variant="white">Подробнее</Button>
                    </div>
                </div>
            </div>
            <div class="people-card">
                <div class="people-image">
                    <img src="/images/people2.png" alt="" class="people-img">
                    <p class="people-profession">Фотограф</p>
                </div>
                <div class="people-text">
                    <p class="people-name">Анастасия Ремогузина</p>
                    <p class="people-desc">Высококачественная видеосъёмка и аэросъёмка: доступные цены, профессиональное
                        оборудование и опытные специалисты</p>
                    <div class="people-btns">
                        <Button class="people-btn">Пригласить</Button>
                        <Button class="people-btn" variant="white">Подробнее</Button>
                    </div>
                </div>
            </div>

        </div>
    </div>
</template>

<style scoped>
.people {
    display: flex;
    flex-direction: column;
    gap: 30px;

    width: 1200px;
}

.controls {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
}

.filters {
    display: flex;
    gap: 20px;
    align-items: center;
}

.filter {
    width: 233px;
    padding: 12px 16px;
    background-color: #F2F2F2;
    border-radius: 10px;


    font-weight: 400;
    font-size: 14px;
    line-height: 19px;
    letter-spacing: -0.01em;

    cursor: pointer;
}

.search-filter {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.search-input {
    border: none;
    outline: none;
    background-color: transparent;
    width: 100%;
    padding-right: 16px;
}

.search-filter::placeholder {
    color: #A0A0A0;
}

.select-filter {
    display: flex;
}

.text-filter {
    text-align: center;
    border: none;
    outline: none;
    width: 100%;
    background-color: transparent;
}

.add-people {
    width: 165px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.people-cards {
    display: flex;
    flex-wrap: wrap;
    gap: 30px;
}

.people-card {
    background-color: #F2F2F2;
    display: flex;
    align-items: center;
    border-radius: 10px;
    height: 166px;
}

.people-image {
    display: flex;
    flex-direction: column;
    align-items: center;
    position: relative;

    width: 166px;
    height: 166px;
}

.people-img {
    width: 166px;
    height: 166px;
    border-top-left-radius: 10px;
    border-bottom-left-radius: 10px;
}

.people-profession {
    position: absolute;
    bottom: 0;

    display: flex;
    justify-content: center;
    align-items: center;

    width: 146px;
    height: 24px;
    margin-bottom: 10px;

    background: rgba(242, 242, 242, 0.7);
    box-shadow: 0px 0px 10px rgba(81, 114, 163, 0.2);
    border-radius: 28px;


    font-weight: 600;
    font-size: 10px;
    line-height: 14px;



}

.people-text {

    padding: 10px 20px;
    max-width: 418px;
}

.people-name {
    font-weight: 600;
    font-size: 24px;
    line-height: 33px;
    margin-bottom: 10px;

}

.people-desc {
    font-weight: 400;
    font-size: 14px;
    line-height: 19px;

    height: 38px;
    overflow: hidden;
    margin-bottom: 26px;

}

.people-btns {
    display: flex;
    justify-content: space-between;
}

.people-btn {
    width: 184px;
}
</style>