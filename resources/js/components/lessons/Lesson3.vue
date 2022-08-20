<template>
<div class="container">
    <div class="row justify-content-center">
        <div class="col-md-8">
            <div class="card">
                <div class="card-body">
                    <div class="d-flex justify-content-start mb-3">
                        <div class="mr-auto">
                            <span class="span-header">Lesson 3</span>
                        </div>
                        <div class="align-self-center">
                            <button type="button" class="btn btn-dark" @click="onBack">戻る</button>
                        </div>
                    </div>

                    <div class="quesion-header">電卓を作成してください。</div>
                    <div class="result-aria">
                        <p class="formula">式：{{ formula }}</p>
                        <p class="result">結果：{{ result }}</p>
                        <div class="reset-button" @click="reset">リセット</div>
                    </div>
                    <div class="number-aria">
                        <div class="number-button" @click="zero">0</div>
                        <div class="number-button" @click="one">1</div>
                        <div class="number-button" @click="two">2</div>
                        <div class="number-button" @click="three">3</div>
                        <div class="number-button" @click="four">4</div>
                        <div class="number-button" @click="five">5</div>
                        <div class="number-button" @click="six">6</div>
                        <div class="number-button" @click="seven">7</div>
                        <div class="number-button" @click="eight">8</div>
                        <div class="number-button" @click="nine">9</div>
                    </div>
                    <div class="cul-aria">
                        <div class="cul-button" @click="plus">+</div>
                        <div class="cul-button" @click="minus">-</div>
                        <div class="cul-button" @click="multi">×</div>
                        <div class="cul-button" @click="division">÷</div>
                        <!-- <div class="cul-button" @click="equal">=</div> -->
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>
</template>

<script>
export default {
    props: {
        //
    },
    data () {
        return {
            result: 0,
            formula: "",
            tmpFormula: "",
            symbol: [],
        }
    },
    mounted () {
        //
    },
    watch: {
        //
    },
    computed: {
        //
    },
    methods: {
        onBack() {
            this.$router.push({ name: 'home' })
        },
        zero() {
            this.formula += "0"
            this.tmpFormula += "0"
        },
        one() {
            this.formula += "1"
            this.tmpFormula += "1"
        },
        two() {
            this.formula += "2"
            this.tmpFormula += "2"
        },
        three() {
            this.formula += "3"
            this.tmpFormula += "3"
        },
        four() {
            this.formula += "4"
            this.tmpFormula += "4"
        },
        five() {
            this.formula += "5"
            this.tmpFormula += "5"
        },
        six() {
            this.formula += "6"
            this.tmpFormula += "6"
        },
        seven() {
            this.formula += "7"
            this.tmpFormula += "7"
        },
        eight() {
            this.formula += "8"
            this.tmpFormula += "8"
        },
        nine() {
            this.formula += "9"
            this.tmpFormula += "9"
        },
        plus() {
            this.formula += " + "
            this.result += parseInt(this.tmpFormula, 10)
            this.tmpFormula = ""
        },
        minus() {
            this.formula += " - "
            this.result -= parseInt(this.tmpFormula, 10)
            this.tmpFormula = ""
        },
        multi() {
            this.formula += " × "
            this.result *= parseInt(this.tmpFormula, 10)
            this.tmpFormula = ""
        },
        division() {
            this.formula += " ÷ "
            this.result /= parseInt(this.tmpFormula, 10)
            this.tmpFormula = ""
        },
        reset() {
            this.result = 0
            this.formula = ""
            this.tmpFormula = ""
        },


    },
}
</script>

<style lang="scss" scoped>
@import "resources/sass/variables";
.result-aria {
    padding: 40px 20px;
    .reset-button {
        width: 60px;
        height: 30px;
        text-align: center;
        line-height: 30px;
        cursor: pointer;
        background-color: aliceblue;
        border-radius: 5px;
        border: 1px solid lightblue;
    }
}

.number-aria {
    display: flex;
    justify-content: space-between;
    padding: 40px 20px 0;
    .number-button {
        width: 30px;
        height: 30px;
        text-align: center;
        line-height: 30px;
        cursor: pointer;
        background-color: aliceblue;
        border-radius: 5px;
        border: 1px solid lightblue;
    }
}

.cul-aria {
    display: flex;
    justify-content: space-around;
    padding: 20px 20px 10px;
    .cul-button {
        width: 60px;
        height: 30px;
        text-align: center;
        line-height: 30px;
        cursor: pointer;
        background-color: #d6f6eb;
        border-radius: 5px;
        border: 1px solid lightblue;
    }
}
</style>
