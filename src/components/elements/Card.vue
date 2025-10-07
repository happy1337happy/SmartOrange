<template>
    <div class="card-wrapp">
        <div class="card-top">
            <div class="date">
                {{ article.date }}
            </div>
            <div class="category">
                {{ article.category }}
            </div>
        </div>
        <div class="img-wrapp" v-if="article.photo">
            <img :src="`/src/assets/img/${article.photo}`" :alt="article.title">
        </div>
        <h2 class="title">{{ article.title }}</h2>
        <div class="address" v-if="article.address">
            {{ article.address }}
        </div>
        <div class="types-wrapp" v-if="article.types && article.types.length > 0">
            Види робіт:
            <div class="types">
                <div class="type-item" v-for="type in article.types" :key="type">
                    {{ type }}
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import { defineProps } from 'vue'

const props = defineProps({
    article: {
        type: Object,
        required: true
    }
})
</script>

<style lang="scss">
    .card-wrapp{
        display: flex;
        flex-direction: column;
        width: 100%;
        max-width: 440px;
        height: auto;
        position: relative;
        border-top: 1.8px solid rgba(168, 168, 168, 0.3);
        border-right: 1.8px solid rgba(168, 168, 168, 0.3);
        border-left: 1.8px solid rgba(168, 168, 168, 0.3);
        border-bottom: 0;
        padding: 20px 12px;
        &::before{
            content: "";
            position: absolute;
            bottom: -28px;
            left: 0;
            width: 100%;
            max-width: 440px;
            height: 28px;
            background-image: url('/src/assets/img/card-down.png');
            background-size: cover;
            background-repeat: no-repeat;
            background-position: center;
        }
        &::after{
            content: "";
            position: absolute;
            top: -30px;
            left: 50%;
            transform: translateX(-50%);
            width: 50px;
            height: 50px;
            background-image: url('/src/assets/img/pin.svg');
            background-size: cover;
            background-repeat: no-repeat;
            background-position: center;
        }
        .card-top{
            display: flex;
            justify-content: space-between;
            margin-bottom: 28px;
            font-weight: 500;
            .date{
                font-size: 20px;
                line-height: 120%;
            }
            .category{
                font-size: 14px;
                line-height: 140%;
                text-transform: uppercase;
                padding: 4px 8px;
                border: 1px solid rgba(168, 168, 168, 1);
                border-radius: 1000px;
            }
        }
        .img-wrapp{
            width: 100%;
            height: 100%;
            max-width: 416px;
            margin-bottom: 12px;
            img{
                width: 100%;
                object-fit: cover;
            }
        }
        .title{
            font-weight: 600;
            font-size: clamp(20px, 5vw, 24px);
            line-height: 120%;
            margin-bottom: 28px;
        }
        .address{
            font-weight: 500;
            font-size: clamp(16px, 4vw, 20px);
            line-height: 120%;
            font-family: Inter Tight;
            margin-bottom: 28px;
        }
        .types-wrapp{
            font-weight: 500;
            font-size: clamp(12px, 3vw, 14px);
            line-height: 140%;
            text-transform: uppercase;
            display: flex;
            flex-direction: column;
            .types{
                display: flex;
                flex-direction: row;
                flex-wrap: wrap;
                gap: 2px;
                color: $grey;
                margin-top: 9px;
                .type-item{
                    padding: 4px 8px;
                    border: 1px solid rgba(168, 168, 168, .2);
                    border-radius: 1000px;
                }
            }
        }
    }
    @media (max-width: 480px){
        .card-wrapp::before {
            bottom: -20px;
        }
        .card-wrapp::after {
            width: 40px;
            height: 40px;
            top: -25px;
        }
    }
    @media (max-width: 376px){
        .card-wrapp::before {
            bottom: -10px;
        }
        .card-wrapp::after {
            width: 30px;
            height: 30px;
            top: -15px;
        }
    }
</style>