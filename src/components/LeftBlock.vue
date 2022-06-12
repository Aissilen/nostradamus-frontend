<template>
    <div class="left-block">
        <div class="left-block-wrapper">
            <div class="answer-container">
                <div class="answer-container__header">
                    <span class="answer-container__header-text">Профиль клиента</span>
                </div>
                <ul class="answer-container__list">
                    <li class="answer-container__list-item">
                        <Multiselect
                            class="answer-container__list-item__input w-100 multiselect-blue"
                            v-model="values.sex"
                            mode="tags"
                            placeholder="Пол"
                            :options="options.sex"
                        />
                    </li>
                    <li class="answer-container__list-item">
                        <Multiselect
                            class="answer-container__list-item__input w-100 multiselect-blue"
                            v-model="values.age"
                            mode="tags"
                            placeholder="Возраст"
                            :options="options.age"
                        />
                    </li>
                    <li class="answer-container__list-item">
                        <Multiselect
                            class="answer-container__list-item__input w-100 multiselect-blue"
                            v-model="values.interest"
                            mode="tags"
                            placeholder="Интересы"
                            :options="options.interest"
                        />
                    </li>
                    <li class="answer-container__list-item">
                        <Multiselect
                            class="answer-container__list-item__input w-100 multiselect-blue"
                            v-model="values.cash"
                            mode="tags"
                            placeholder="Уровень дохода"
                            :options="options.cash"
                        />
                    </li>
                </ul>
            </div>
            <div class="button-container">
                <button
                    type="button"
                    class="btn btn-success w-100 start-search-button"
                    @click="apllyFilters()"
                >
                    НАЧАТЬ
                </button>
            </div>
        </div>
    </div>
</template>

<script>
import Multiselect from '@vueform/multiselect'

export default {
  name: 'LeftBlock',
  components: {
    Multiselect,
  },
  methods: {
    apllyFilters () {
        console.log(this.values);
    }
  },
  data() {
    return {
      values: {
          sex: null,
          age: null,
          interest: null,
          cash: null,
      },
      options: {
        sex: [
          'Мужской',
          'Женский',
        ],
        age: [
          'до 18',
          '18-24',
          '25-34',
          '35-44',
          '45-54',
          ' 55+ ',
        ],
        interest: [
          'Финансы и инвестиции',
          'Кафе, доставки',
          'Автолюбители',
        ],
        cash: [
          '0-20k',
          '21-50k',
          '51-100k',
          '101-200k',
          '200k+'
        ]
      }
    }
  }
}
</script>

<style src="@vueform/multiselect/themes/default.css"></style>

<style scoped>
.multiselect-blue {
  --ms-tag-bg: #014c98;
  --ms-tag-color: #fff;
  --ms-tag-opacity: 0.7;
}
.left-block-wrapper {
    background-color: #fff;
    padding: 5px 20px 20px 20px;
    border-radius: 10px;
}
.answer-container__list {
    margin: 0;
    padding: 0;
}
.answer-container__header{
    display: flex;
    align-items: center;
    justify-content: center;
    height: 40px;
}
.answer-container__list-item{
    list-style-type: none;
    display: flex;
    align-items: center;
    justify-content: flex-start;
    /* height: 40px; */
    margin-top: 10px;
    border-radius: 10px;
    background-color: #F5F5F5;
}
.answer-container__list-item__input{
    /* height: 40px; */
    border-radius: 10px;
    background-color: #F5F5F5;
    /* padding-left: 15px; */
}
.start-search-button{
    margin-top: 10px;
}
</style>