<script>
// import HelloWorld from "./components/HelloWorld.vue";
// import TheWelcome from "./components/TheWelcome.vue";
export default {
    data() {
        return {
            currentInput: "",
            todoItems: [
                { id: 1, content: "Do this" },
                { id: 2, content: "Do that" },
            ],
        };
    },
    methods: {
        handleAddTodoItem() {
            const newTodoItem = {};
            newTodoItem.content = this.currentInput;
            this.todoItems.push(newTodoItem);
        },
        handleRemoveTodoItem(indexOfTodoItem) {
            this.todoItems.splice(indexOfTodoItem, 1);
        },
    },
};
</script>

<template>
    <header>Vue Todo</header>
    <main class="">
        <div class="p-4">
            <input v-model="currentInput" class="p-2 border bg-slate-200" />
            <button
                class="ml-2 p-1 text-sm border-green-500 border-2 rounded-xl text-green-700"
                @click="handleAddTodoItem"
            >
                Add item
            </button>
        </div>
        <ul class="bg-stone-600 rounded-md">
            <div
                v-for="(todoItem, index) in todoItems"
                :key="index"
                class="p-2"
            >
                <li class="inline">{{ todoItem.content }}</li>
                <button
                    class="ml-2 p-1 text-sm border-orange-500 rounded-xl text-orange-700"
                    @click="handleRemoveTodoItem(index)"
                >
                    Remove
                </button>
            </div>
        </ul>
    </main>
</template>

<style>
#app {
    height: 100vh;
    margin: 0 auto;
    padding: 2rem;
    color: white;
    background-color: hsl(194, 65%, 17%);
    font-weight: normal;
}

header {
    line-height: 1.5;
}

a,
.green {
    text-decoration: none;
    color: hsla(160, 100%, 37%, 1);
    transition: 0.4s;
}

#app {
    display: grid;
    grid-template-rows: 100px 1fr;
    padding: 0 2rem;
}
</style>
