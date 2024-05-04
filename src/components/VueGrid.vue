<template>
    <div id="VueGrid">
        <h1 id="title">Not Twitter</h1>
        <button id="toggleBtn" v-on:click="toggleView">Toggle View</button>
        <div id="tweets">
            <div id="grid_container" v-if="toggleListGrid == 'grid'">
                <div class="tweet_container" v-for="(tweet, index) in tweets" :key="index">
                    <p class="tweet_name">{{ tweet[`name`] }}</p>
                    <p class="tweet_username">{{ tweet[`username`] }}</p>
                    <p class="tweet_content">{{ tweet[`content`] }}</p>
                    <p class="tweet_date">{{ tweet[`date`] }}</p>
                </div>
            </div>
            <div id="list_container" v-if="toggleListGrid == 'list'">
                <div class="tweet_container" v-for="(tweet, index) in tweets" :key="index">
                    <p class="tweet_name">{{ tweet[`name`] }}</p>
                    <p class="tweet_username">{{ tweet[`username`] }}</p>
                    <p class="tweet_content">{{ tweet[`content`] }}</p>
                    <p class="tweet_date">{{ tweet[`date`] }}</p>
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
                    content: 'Quisque ut erat suscipit, fringilla sem ultrices, aliquet risus. Cras vestibulum pulvinar elementum. Duis ut lectus eget arcu euismod facilisis at non odio',
                    date: '2024/03/20'
                },
                {
                    name: 'john',
                    username: '@joncena',
                    content: 'Phasellus posuere, sem id commodo ornare, massa est cursus libero, consequat lacinia diam libero at lorem. Phasellus a elit sed magna cursus condimentum',
                    date: '2024/03/29'
                },
                {
                    name: 'emily',
                    username: '@emiiliie',
                    content: 'Vestibulum condimentum tellus in dui pharetra sodales. Nullam cursus nec turpis eget mollis. Morbi sollicitudin, neque nec condimentum maximus',
                    date: '2024/03/27'
                },
                {
                    name: 'joe',
                    username: '@joe76',
                    content: 'sed laoreet purus. Cras at diam et nunc rhoncus pretium tincidunt non est. Maecenas pellentesque finibus nisl quis laoreet. In neque ex, scelerisque vel tellus id',
                    date: '2024/03/26'
                },
                {
                    name: 'ann',
                    username: '@abnn1',
                    content: 'Quisque ut erat suscipit, fringilla sem ultrices, aliquet risus. Cras vestibulum pulvinar elementum. Duis ut lectus eget arcu euismod facilisis at non odio',
                    date: '2024/03/25'
                },
                {
                    name: 'holly',
                    username: '@holy',
                    content: 'Phasellus posuere, sem id commodo ornare, massa est cursus libero, consequat lacinia diam libero at lorem. Phasellus a elit sed magna cursus condimentum',
                    date: '2024/03/21'
                },
                {
                    name: 'mark',
                    username: '@markk',
                    content: 'Vestibulum condimentum tellus in dui pharetra sodales. Nullam cursus nec turpis eget mollis. Morbi sollicitudin, neque nec condimentum maximus',
                    date: '2024/03/23'
                },
                {
                    name: 'kevin',
                    username: '@kev55',
                    content: 'sed laoreet purus. Cras at diam et nunc rhoncus pretium tincidunt non est. Maecenas pellentesque finibus nisl quis laoreet. In neque ex, scelerisque vel tellus id',
                    date: '2024/03/22'
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
#title{
    margin-left: 60px;
}
#toggleBtn {
    margin-left: 80px;
}
#tweets{
    padding: 50px;
}
.tweet_name{
    font-weight: bold;
}
.tweet_username{
    font-style: italic;
    color: gray;
}

.tweet_content{
    margin-bottom: 20px;
}

.tweet_date{
    margin-bottom: 20px;
    text-align: end;
    font-style: italic;
    font-weight: lighter;
    color: darkgray;
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