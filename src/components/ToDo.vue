<template>
    <div class="container">
        <div>
            <button @click="toggleCompletedList">Mostra completati</button>
            <input type="text" v-model="newachivement" />
            <button @click="addachivement">Crea</button>
        </div>
        <div>
            <ul>
                <div v-if="completed == true">
                    <h1>completed List</h1>
                    <li v-for="(achivement, index) in completedlist" :key="index" @click="removeClass(index)"
                        :class="{ completed: achivement.completed }">
                        {{ achivement.name }}
                        <!-- @click.stop è usata per prevenire la propagazione dell'evento di click a genitori o elementi superiori nella gerarchia DOM. -->
                        <button class="btn btn-danger ms-5" v-if="completedlist.length > 0"
                            @click.stop="deleteItem(index)">Deleat</button>
                    </li>
                </div>
                <div v-else>
                    <h1>List</h1>
                    <li v-for="(achivement, index) in list" :key="index" @click="addclass(index)">
                        {{ achivement.name }}
                    </li>

                </div>

            </ul>
        </div>
    </div>
</template>

<script>
export default {
    name: "To-Do",
    data() {
        return {
            newachivement: '',
            list: [],
            completedlist: [],
            completed: false,
        }
    },
    methods: {
        addachivement() {
            if (this.newachivement !== '' && this.newachivement !== ' ') {
                this.list.push({ name: this.newachivement, completed: false });
                this.newachivement = ''
            }
        },
        addclass(i) {
            let achivement = this.list[i]
            achivement.completed = true;
            this.completedlist.push(achivement);
            this.list = this.list.filter(item => item !== achivement);
        },
        removeClass(i) {
            let achivement = this.completedlist[i];
            achivement.completed = false;
            this.list.push(achivement);
            this.completedlist = this.completedlist.filter(item => item !== achivement);
        },
        toggleCompletedList() {
            this.completed = !this.completed;
        },
        deleteItem(index) {
            this.completedlist.splice(index, 1); 
        },
    }
}
</script>

<style lang="scss" scoped>
.completed {
    text-decoration: line-through;
    color: gray;
}
li:hover{
    cursor: pointer;
}
</style>