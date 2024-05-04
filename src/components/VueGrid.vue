<template>
    <div id="VueGrid">
        <button id="toggleBtn" v-on:click="toggleView">Toggle View</button>
        <div id="tweets">
            <div id="grid_container" v-if="toggleListGrid == 'grid'">
                <div class="tweet_container" v-for="(tweet, index) in tweets" :key="index">
                    <p class="tweet_name">{{ tweet[`name`] }}</p>
                    <p class="tweet_username">{{ tweet[`username`] }}</p>
                    <p class="tweet_content">{{ tweet[`content`] }}</p>
                </div>
            </div>
            <div id="list_container" v-if="toggleListGrid == 'list'">
                <div class="tweet_container" v-for="(tweet, index) in tweets" :key="index">
                    <p class="tweet_name">{{ tweet[`name`] }}</p>
                    <p class="tweet_username">{{ tweet[`username`] }}</p>
                    <p class="tweet_content">{{ tweet[`content`] }}</p>
                </div>
            </div>
        </div>
    </div>
</template>



<script>

export default {

    name: 'VueGrid',

    props: {
        msg: String

    },

    data: function () {
        return {
            toggleListGrid: `list`,
            tweets: [
                {
                    name: 'frank',
                    username: '@frank21',
                    content: 'Quisque ut erat suscipit, fringilla sem ultrices, aliquet risus. Cras vestibulum pulvinar elementum. Duis ut lectus eget arcu euismod facilisis at non odio'
                },
                {
                    name: 'john',
                    username: '@joncena',
                    content: 'Phasellus posuere, sem id commodo ornare, massa est cursus libero, consequat lacinia diam libero at lorem. Phasellus a elit sed magna cursus condimentum'
                },
                {
                    name: 'emily',
                    username: '@emiiliie',
                    content: 'Vestibulum condimentum tellus in dui pharetra sodales. Nullam cursus nec turpis eget mollis. Morbi sollicitudin, neque nec condimentum maximus'
                },
                {
                    name: 'joe',
                    username: '@joe76',
                    content: 'sed laoreet purus. Cras at diam et nunc rhoncus pretium tincidunt non est. Maecenas pellentesque finibus nisl quis laoreet. In neque ex, scelerisque vel tellus id'
                },
                {
                    name: 'ann',
                    username: '@abnn1',
                    content: 'Quisque ut erat suscipit, fringilla sem ultrices, aliquet risus. Cras vestibulum pulvinar elementum. Duis ut lectus eget arcu euismod facilisis at non odio'
                },
                {
                    name: 'holly',
                    username: '@holy',
                    content: 'Phasellus posuere, sem id commodo ornare, massa est cursus libero, consequat lacinia diam libero at lorem. Phasellus a elit sed magna cursus condimentum'
                },
                {
                    name: 'mark',
                    username: '@markk',
                    content: 'Vestibulum condimentum tellus in dui pharetra sodales. Nullam cursus nec turpis eget mollis. Morbi sollicitudin, neque nec condimentum maximus'
                },
                {
                    name: 'kevin',
                    username: '@kev55',
                    content: 'sed laoreet purus. Cras at diam et nunc rhoncus pretium tincidunt non est. Maecenas pellentesque finibus nisl quis laoreet. In neque ex, scelerisque vel tellus id'
                },
            ]
        }
    },

    methods: {
        toggleView: function () {
            if(this.toggleListGrid == 'grid'){
                this.toggleListGrid = 'list'
            }else if (this.toggleListGrid == 'list'){
                this.toggleListGrid = 'grid'
            }
        }
    }
}

</script>



<!-- Add "scoped" attribute to limit CSS to this component only -->

<style scoped>
#toggleBtn {
    text-align: end;
}
.tweet_name{
    font-weight: bold;
}
.tweet_username{
    font-style: italic;
    color: gray;
}

.tweet_content{
    margin-bottom: 50px;
}

#list_container{
    display: grid;
}

#list_container .tweet_container{
    display: block;
    width: 400px;
}

#grid_container{
    display: grid;
    grid-template-columns: auto auto auto auto;
}

#grid_container .tweet_container{
    display: inline-block;
    width: 300px;
}
</style>