<template>
    <div>
        <div class="parent">
            <h1 v-if="loader">loading posts</h1>
            <h1 v-else-if="error">error fetching posts</h1>
            <div class="card" v-for="post in posts">
                <h1>{{ post.id }}</h1>
                <p>{{ post.title }}</p>
                <h5>{{ post.body }}</h5>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'ServicesView',

    // computed: {
    //     greeting() {
    //         alert("This is special from the mounted!");
    //     }
    // },

    methods: {
        sayHello() {
            alert("Hello!.");
        }
    },

    data() {
        return {
            pageTitle: "Services Page",
            loader: true,
            error: null,

            //services
            posts: [],
        };
    },
    //api calls
    // mounted() {
    //     fetch('https://fakestoreapi.com/products')
    //         .then((response) => response.json())
    //         .then((data) => {
    //             this.posts = data;
    //         });

    // }
    async mounted() {
        try{
          const response = await fetch('https://fakestoreapi.com/products')
            if(!response.ok){
                throw new Error("");
            }
          const data = await response.json()
          this.posts = data;
        } catch (error){
          //console.log(error);
          this.error = error;
        } finally {
            this.loader = false;
        }

    }
};
</script>

<style scoped>
.parent {
    display: flex;
    gap: 20px;
    flex-wrap: wrap;
}
.card {
    border: 1px solid #ccc;
    padding: 20px;
    border-radius: 8px;
    width: 300px;
    box-shadow: 2px 2px 12px rgba(0, 0, 0, 0.1);
    background-color:salmon;
}
</style>