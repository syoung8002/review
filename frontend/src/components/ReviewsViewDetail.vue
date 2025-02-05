<template>

    <v-card outlined>
        <v-card-title>
            Reviews # {{$route.params.id }}
        </v-card-title>

        <v-card-text>
            <div>
                <String label="ItemId" v-model="item.itemId" :editMode="editMode" @change="change" />
            </div>
            <div>
                <Number label="Rating" v-model="item.rating" :editMode="editMode" @change="change" />
            </div>
            <div>
                <String label="Text" v-model="item.text" :editMode="editMode" @change="change" />
            </div>
            <div>
                <String label="UserId" v-model="item.userId" :editMode="editMode" @change="change" />
            </div>
            <div>
                <String label="UserImg" v-model="item.userImg" :editMode="editMode" @change="change" />
            </div>
            <div>
                <String label="ItemId" v-model="item.itemId" :editMode="editMode" @change="change" />
            </div>
            <div>
                <Number label="Rating" v-model="item.rating" :editMode="editMode" @change="change" />
            </div>
            <div>
                <String label="Text" v-model="item.text" :editMode="editMode" @change="change" />
            </div>
            <div>
                <String label="UserId" v-model="item.userId" :editMode="editMode" @change="change" />
            </div>
            <div>
                <String label="UserImg" v-model="item.userImg" :editMode="editMode" @change="change" />
            </div>
        </v-card-text>
    </v-card>

</template>

<script>
  const axios = require('axios').default;

  export default {
    name: 'ReviewsViewDetail',
    props: {
      value: Object,
    },
    data: () => ({
        item : [],
    }),
    async created() {
      var params = this.$route.params;
      var temp = await axios.get(axios.fixUrl('/reviews/' + params.id))

      this.item = temp.data;

    },
    methods: {
    }
  }
</script>

