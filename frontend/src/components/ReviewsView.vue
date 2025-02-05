<template>

    <v-data-table
        :headers="headers"
        :items="reviews"
        :items-per-page="5"
        class="elevation-1"
    ></v-data-table>

</template>

<script>
    const axios = require('axios').default;

    export default {
        name: 'ReviewsView',
        props: {
            value: Object,
            editMode: Boolean,
            isNew: Boolean
        },
        data: () => ({
            headers: [
                { text: "id", value: "id" },
                { text: "itemId", value: "itemId" },
                { text: "rating", value: "rating" },
                { text: "text", value: "text" },
                { text: "userId", value: "userId" },
                { text: "userImg", value: "userImg" },
                { text: "itemId", value: "itemId" },
                { text: "rating", value: "rating" },
                { text: "text", value: "text" },
                { text: "userId", value: "userId" },
                { text: "userImg", value: "userImg" },
            ],
            reviews : [],
        }),
          async created() {
            var temp = await axios.get(axios.fixUrl('/reviews'))

            temp.data._embedded.reviews.map(obj => obj.id=obj._links.self.href.split("/")[obj._links.self.href.split("/").length - 1])

            this.reviews = temp.data._embedded.reviews;
        },
        methods: {
        }
    }
</script>

