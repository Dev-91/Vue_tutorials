<template>
    <div>
        <h1>Welcome to {{title}}!</h1>
        <input type="text" v-model="input1" />
        <button type="button" @click="getData">Get</button>
        <button type="button" @click="setData">Set</button>
        <h2>{{input1}}</h2>

        <select v-model="region" @change="changeRegion">
            <option :key="i" :value="d.v" v-for="(d, i) in options">
                {{d.t}}
            </option>
        </select>

        <table v-show="tableShow">
            <tr :key="i" v-for="(d, i) in options">
                <td>{{d.v}}</td>
                <td>{{d.t}}</td>
            </tr>
        </table>
    </div>
</template>
<script>
export default {
    data() {
        return {
            title: "Dev91",
            title2: "Jeju",
            input1: "abc",
            options: [
                {v: "S", t: "seoul"},
                {v: "J", t: "jeju"},
                {v: "B", t: "busan"}
            ],
            region: "J",
            tableShow: true,
        }
    },
    watch: {  // 특정 데이터를 모니터링해야하는 경우 사용!
        title() {
            console.log(this.title)
        },
        input1() { // 변수와 동일한 명칭의 메소드 명칭으로 생성!
            console.log(this.input1)
        },
    },
    methods: {
        getData() {
            alert(this.input1)
        },
        setData() {
            this.input1 = "1234"
        },
        changeRegion() {
            alert(this.region)
        }
    },

    // Life cycle callback methods start
    beforeCreate() {
        console.log("beforeCreate");
    },
    created() {
        console.log("created");
    },
    beforeMount() {
        console.log("beforeMount");
    },
    mounted() {
        console.log("mounted");
    },
    beforeUpdate() {
        console.log("beforeUpdate");
    },
    updated() {
        console.log("updated");
    },
    beforeDestroy() {
        console.log("beforeDestroy");
    },
    destroyed() {
        console.log("destroyed");
    },
    // Life cycle callback methods finish
}
</script>