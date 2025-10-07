<template>
    <section class="main-wrapper">
        <div class="container">
            <div class="main-wrapp">
                <h1>Збудовані обʼєкти</h1>
                <div class="cards-wrapp">
                    <div class="card-filter">
                        <div
                            v-for="category in categories"
                            :key="category"
                            class="card-filter-item"
                            @click="selectCategory(category)"
                            :class="{ active: selectedCategory === category }"
                        >
                            {{ category }}
                        </div>
                    </div>
                    <div class="cards">
                        <Card 
                            v-for="article in visibleArticles" 
                            :key="article.id" 
                            :article="article" 
                        />
                    </div>
                    <div class="more" @click="loadMore" v-if="visibleCount < filteredArticles.length">Завантажити ще</div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>

    import { ref, computed } from 'vue';
    import Card from '../elements/Card.vue';
    import { articles } from '@/utils/articles.js'; 

    const selectedCategory = ref('Усі');

    const categories = ['Усі', 'Житловий', 'Громадський', 'Спортивний', 'Меценатство'];

    const visibleCount = ref(3);

    const filteredArticles = computed(() => {
        if (selectedCategory.value === 'Усі') {
            return articles;
        }
        return articles.filter(article => article.category === selectedCategory.value);
    });

    const visibleArticles = computed(() => filteredArticles.value.slice(0, visibleCount.value));

    const selectCategory = (category) => {
        selectedCategory.value = category;
        visibleCount.value = 3;
    };

    const loadMore = () => {
        if (visibleCount.value < filteredArticles.value.length) {
            visibleCount.value += 3;
        }
    };
</script>

<style lang="scss">
    .main-wrapper{
        margin-top: 100px;
        margin-bottom: 210px;
        .main-wrapp{
            display: flex;
            flex-direction: column;
            h1{
                font-weight: 500;
                font-size: clamp(28px, 4vw, 48px);
                line-height: 90%;
                margin-bottom: clamp(24px, 4vw, 40px);
            }
            .cards-wrapp{
                .card-filter{
                    display: flex;
                    gap: clamp(10px, 4vw, 60px);
                    margin-bottom: clamp(40px, 8vw, 100px);
                    font-weight: 600;
                    font-size: clamp(16px, 2vw, 24px);
                    line-height: 120%;
                    .card-filter-item{
                        cursor: pointer;
                        &.active{
                            border-bottom: 2px solid #000;
                        }
                    }
                }
                .cards{
                    display: flex;
                    justify-content: space-between;
                    flex-wrap: wrap;
                    gap: 70px 20px;
                    align-items: flex-start;
                    margin-bottom: 128px;
                }
                .more{
                    font-weight: 500;
                    font-size: 14px;
                    line-height: 140%;
                    text-transform: uppercase;
                    border-bottom: 2px solid #000;
                    width: 153px;
                    position: relative;
                    margin: 0 auto;
                    cursor: pointer;
                    &::before{
                        content: "";
                        position: absolute;
                        width: 7.5px;
                        height: 12px;
                        right: 4px;
                        bottom: 4px;
                        background-image: url('/src/assets/img/arrow-down.svg');
                        background-size: cover;
                        background-repeat: no-repeat;
                        background-position: center;
                    }
                }
            }
        }
    }

    @media (max-width: 585px) {
        h1{
            display: flex;
            justify-content: center;
        }
        .main-wrapper .main-wrapp .cards-wrapp .card-filter {
            flex-wrap: wrap;
            justify-content: center;
            gap: clamp(8px, 2vw, 20px);
        }
    }
</style>