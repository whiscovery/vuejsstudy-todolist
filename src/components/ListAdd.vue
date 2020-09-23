<template>
    <div>
         <v-textarea
          outlined
          v-model="memo"
          label="투두리스트 입력"
          value=""
        ></v-textarea>
        <v-btn @click="listAdd">추가</v-btn>

    </div>
</template>

<script>
export default {
    data () {
        return {
            memo: null
        }
    },
    methods: {
        listAdd() {
            console.log("리스트추가")
            if(this.memo == null){
                alert("할일을 입력하세요")
            } else {
                this.$emit('listAdd', this.memo)
            }
            
        }
    }
}
</script>