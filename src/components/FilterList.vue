<template>

    <div>
        <div class="filter-header">
            <img src="../assets/images/left-arrow.svg" alt="" width="20" @click="goBack" >
            <p class="font-18">Фильтр</p>
        </div>
        <div class="filter-body">
            <collapse :selected="false">
                <div slot="collapse-header">
                    ТОВАРЫ
                </div>
                <div slot="collapse-body">
                    <div class="radio-wrapper" v-for="item in buttons2" >
                        <div v-on:click="provide2(item)" v-bind:class="{clicked2: contains(check, item)}" class="tab-unchecked"></div><div><p class="collapse-text-type font-14">{{item.name}}</p></div>
                    </div>
                </div>
            </collapse>
            <div class="line-grey-out"><div class="line-grey"></div></div>
            <collapse :selected="false">
                <div slot="collapse-header">
                    ЦЕНА
                </div>
                <div slot="collapse-body">
                    frf
                </div>
            </collapse>
            <div class="line-grey-out"><div class="line-grey"></div></div>
            <collapse :selected="false">
                <div slot="collapse-header">
                    ЦВЕТ
                </div>
                <div slot="collapse-body">
                    <div class="filter-color">
                        <div>
                            <md-checkbox class="color-font font-14" v-model="array" value="black">Черный</md-checkbox>
                            <md-checkbox class="color-font font-14" v-model="array" value="white">Белый</md-checkbox>
                            <md-checkbox class="color-font font-14" v-model="array" value="grey">Серый</md-checkbox>
                        </div>
                        <div>
                            <md-checkbox class="color-font font-14" v-model="array" value="gold">Золотой</md-checkbox>
                            <md-checkbox class="color-font font-14" v-model="array" value="pink">Розовый</md-checkbox>
                            <md-checkbox class="color-font font-14" v-model="array" value="green">Зеленый</md-checkbox>
                        </div>
                    </div>
                </div>
            </collapse>
            <div class="line-grey-out"><div class="line-grey"></div></div>
            <collapse :selected="false">
                <div slot="collapse-header">
                    РАЗМЕР ЭКРАНА
                </div>
                <div slot="collapse-body">
                    <div class="all-sizes">
                        <div v-for="item in buttons" v-on:click="provide(item)" v-bind:class="{clicked: contains(sizes, item)}" class="one-size">{{ item.name }}</div>
                    </div>
                </div>
            </collapse>
            <div class="line-grey-out"><div class="line-grey"></div></div>
            <collapse :selected="false">
                <div slot="collapse-header">
                    ОТЗЫВЫ ПОКУПАТЕЛЕЙ
                </div>
                <div slot="collapse-body">
                    <div>
                        <div class="feedback">
                            <div><md-radio v-model="radio" value="all"></md-radio></div>
                            <p>Любой рейтинг</p>
                        </div>
                        <div class="feedback">
                            <div><md-radio v-model="radio" value="one"></md-radio></div>
                            <div class="for-star">
                                <img src="../assets/images/star.svg" alt="">
                                <img src="../assets/images/star.svg" alt="">
                                <img src="../assets/images/star.svg" alt="">
                                <img src="../assets/images/star.svg" alt="">
                                <img src="../assets/images/stargrey.svg" alt="">
                                <p> и более</p>
                            </div>
                        </div>
                        <div class="feedback">
                            <div><md-radio v-model="radio" value="two"></md-radio></div>
                            <div class="for-star">
                                <img src="../assets/images/star.svg" alt="">
                                <img src="../assets/images/star.svg" alt="">
                                <img src="../assets/images/star.svg" alt="">
                                <img src="../assets/images/stargrey.svg" alt="">
                                <img src="../assets/images/stargrey.svg" alt="">
                                <p> и более</p>
                            </div>
                        </div>
                        <div class="feedback">
                            <div><md-radio v-model="radio" value="three"></md-radio></div>
                            <div class="for-star">
                                <img src="../assets/images/star.svg" alt="">
                                <img src="../assets/images/star.svg" alt="">
                                <img src="../assets/images/stargrey.svg" alt="">
                                <img src="../assets/images/stargrey.svg" alt="">
                                <img src="../assets/images/stargrey.svg" alt="">
                                <p> и более</p>
                            </div>
                        </div>

                    </div>
                </div>
            </collapse>
            <div class="line-grey-out"><div class="line-grey"></div></div>
            <collapse :selected="false">
                <div slot="collapse-header">
                    ВСТРОЕННАЯ ПАМЯТЬ
                </div>
                <div slot="collapse-body">
                    frf
                </div>
            </collapse>
            <div class="line-grey-out"><div class="line-grey"></div></div>
            <collapse :selected="false">
                <div slot="collapse-header">
                    ЗАДНЯЯ КАМЕРА
                </div>
                <div slot="collapse-body">
                    frf
                </div>
            </collapse>
            <div class="line-grey-out"><div class="line-grey"></div></div>
            <collapse :selected="false">
                <div slot="collapse-header">
                    ПЕРЕДНЯЯ КАМЕРА
                </div>
                <div slot="collapse-body">
                    frf
                </div>
            </collapse>
            <div class="line-grey-out"><div class="line-grey"></div></div>
            <collapse :selected="false">
                <div slot="collapse-header">
                    РАЗРЕШЕНИЕ ЭКРАНА
                </div>
                <div slot="collapse-body">
                    frf
                </div>
            </collapse>
            <div class="line-grey-out"><div class="line-grey"></div></div>
        </div>
    </div>
</template>

<script>
    import Vue from 'vue';
    import Collapse from 'vue-collapse'
    import VueMaterial from 'vue-material'
    import 'vue-material/dist/vue-material.min.css'
    import 'vue-material/dist/theme/default.css'

    Vue.use(VueMaterial)

    export default {
        name: "FilterList",
        data() {
            return{
                checkedProduct: true,
                radio: 'accent',
                array: [],
                boolean: false,
                string: null,
                novalue: null,
                disabled: true,
                obj1: {name: 'ob1'},
                obj2: {name: 'obj2'},
                obj: null,
                indeterminate: true,
                currentTab: 0,
                buttons: [
                    {name: '5.5'},
                    {name: '5.7'},
                    {name: '5.0'},
                    {name: '6.0'},
                    {name: '4.7'},
                    {name: '4.3'},
                ],
                buttons2: [
                    {name: 'Ноутбуки (23)'},
                    {name: 'Наушники (123)'},
                    {name: 'Смартфоны (24)'},
                    {name: 'Планшеты (134)'},
                    {name: 'Плейеры (5)'},
                    {name: 'Чехлы для ноутбуков (32)'},
                    {name: 'Чехлы для смартфонов (24)'},
                ],
                sizes: [],
                check: [],
                currentImg: 0,
            }
        },
        methods: {
            goBack(){
                // this.$router.push('/filter')
                this.$router.push({ path: '/' })
            },
            selectTab(selectedTab){
                this.currentTab = selectedTab
            },
            provide(item){
                if(this.sizes.indexOf(item) == -1)
                {
                    this.sizes.push(item);
                }
                else
                {
                    this.sizes.splice(this.sizes.indexOf(item), 1);
                }
            },
            provide2(item){
                if(this.check.indexOf(item) == -1)
                {
                    this.check.push(item);
                }
                else
                {
                    this.check.splice(this.check.indexOf(item), 1);
                }
            },
            contains(arr, item){
                return arr.indexOf(item) != -1;
            },
            selectImg(selectedImg){
                this.currentImg = selectedImg
            },
        },
        components:{
            Collapse
        }
    }
</script>




<style lang="scss" scoped>
    @import '../assets/styles/main.scss';

    .filter-header{
        width: 100%;
        height: 4rem;
        line-height: 20px;
        text-align: center;
        color: $mainColor2;
        font-family: 'Roboto', sans-serif;
        background: #FFFFFF;
        box-shadow: 0px 4px 4px rgba(231, 231, 231, 0.25);
        display: flex;
        align-items: center;
        justify-content: center;
        img{
            position: absolute;
            left: 0;
            margin: 0px 10px 0px 10px;
        }
        h1{
            margin: 0;
        }
    }
    .filter-body{
        background-color: #fff;
        margin-top: 0.5rem;
    }
    .line-grey-out{
        padding: 0rem 1rem 0rem 1rem;
    }
    .line-grey{
        width: 100%;
        height: 1px;
        background: rgba(40, 47, 54, 0.15);
        margin-left: auto;
        margin-right: auto;
        margin-top: 1rem;
    }
    .md-checkbox {
        display: flex;
    }
    .md-radio {
        display: flex;
    }
    .filter-color{
        display: flex;
        justify-content: space-between;
    }
    .color-font{
        line-height: 20px;
        color: rgba(40, 47, 54, 0.8);
        font-family: 'Open Sans', sans-serif;
    }
    .for-star{
        height: 3rem;
        display: flex;
        align-items: center;
        p{
            padding-left: 10px;
        }
    }
    .feedback{
        height: 2rem;
        display: flex;
        align-items: center;
        p{
            margin: 0;
            font-size: 14px;
            line-height: 20px;
            color: $mainColor2;
            font-family: 'Open Sans', sans-serif;
        }
    }
    .all-sizes{
        display: flex;
        flex-wrap: wrap;
        padding-left: 0.3rem;
        padding-right: 0.3rem;
        justify-content: start;
        margin-top: 1rem;
    }
    .one-size{
        width: 49px;
        height: 30px;
        font-weight: 600;
        line-height: 20px;
        font-size: 14px;
        font-family: 'Open Sans', sans-serif;
        border: 1px solid rgba(40, 47, 54, 0.15);
        box-sizing: border-box;
        border-radius: 5px;
        margin: 0rem 0.2rem 0.2rem 0.2rem;
        display: flex;
        align-items: center;
        justify-content: center;
    }
    .clicked{
        border: 1px solid $mainColor1;
    }

    .checkbox{
        width: 20px;
        height: 20px;
        background: #FFFFFF;
        border: 1px solid rgba(40, 47, 54, 0.15);
        box-sizing: border-box;
        border-radius: 3px;
    }
    .active{
        background: $mainColor1;
    }
    .radio-wrapper{
        display: flex;
        p{
            margin: 0;
            padding: 0rem 0rem 1rem 1rem;
        }
    }
    .tab-unchecked{
        width: 20px;
        height: 20px;
        background: url(../assets/images/unchecked-checkbox.png) no-repeat center center;
        background-size: 20px;
        border: none;
    }
    .clicked2{
        width: 20px;
        height: 20px;
        /*color: red;*/
        color: red;
        background: url(../assets/images/checked-checkbox.png);
        background-size: cover;
    }
    .collapse-text-type{
        line-height: 20px;
        font-family: 'Open Sans', sans-serif;
        font-weight: normal;
    }

</style>

<style lang="scss">
    @import '../assets/styles/main.scss';

    .collapse-content{
        background-color: #fff!important;
    }
    .collapse .collapse-header{
        background-color: #fff;
        padding: 20px 20px 5px 40px !important;
    }
    .collapse .collapse-header::before {
        -webkit-transition: all .2s !important;
        transition: all .2s !important;
        content: url(../assets/images/arrow-down.svg) !important;
        position: absolute !important;
        font-size: 0.4em !important;
        top: calc(50% - 0.4em) !important;
        left: 90% !important;
        color: #c5c9d0 !important;
        -webkit-transform: rotate(0deg) !important;
        transform: rotate(0deg) !important;
    }
    .collapse.is-active .collapse-header::before {
        -webkit-transform: rotate(180deg) !important;
        transform: rotate(180deg) !important;
    }
    .collapse .collapse-content-box{
        border-bottom: none!important;
    }
    .md-checkbox.md-theme-default.md-checked .md-checkbox-container{
        background-color: $mainColor1 !important;
        border-color: $mainColor1 !important;
    }
    .md-radio.md-theme-default.md-checked .md-radio-container{
        border-color: var(--md-theme-default-accent, $mainColor1);
    }
    button{
        border: 0;
        background-color: transparent;
    }
    select {
        -webkit-appearance: none;
        -moz-appearance: none;
        appearance: none;
    }
</style>
