<template>
    <div>
        <v-card
            class="pa-3 mb-3"
            :class="{'done': list.status == 'done'}"
            v-for="(list, index) in todoList"
            :key="index"
        >
            <p>{{list.memo}}</p>
            <v-btn 
                v-if="list.status === 'created'"
                @click="$emit('statusControl', index, 'done')"
                fab text small
            >
                완료
            </v-btn>
            <v-btn
                v-else
                @click="$emit('statusControl', index, 'created')"
                fab text small
            >
                부활
            </v-btn>
            <v-btn
                v-if="list.status == 'created'"
                @click="listEdit(list.memo, index)"
                fab text small
            >
                수정
            </v-btn>
            <v-btn
                @click="$emit('listDelete', index)"
                fab text small
            >
                제거
            </v-btn>
        </v-card>
    </div>
</template>

<script>
import { eventBus } from '../main'

export default {
    props: ['todoList'],
    methods: {
        listEdit(memo, index) {
            eventBus.modifyList(memo, index)
        }
    }
}
</script>

<style scoped>
.done {
    background-color: rgba(197, 23, 23, 0.5);
}
.done p {
    text-decoration: line-through;
    color: rgba(0, 0, 0, 0.5);
}
</style>
