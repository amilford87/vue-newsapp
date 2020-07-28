<template>

<div class="container">
    <h4>{{newsdetail.title}}</h4>
    <div class="row">
        <div class="col-md-12">
            <span>By: {{newsdetail.author}}</span>
        </div>
        <div class="col-md-12">
            <span>Published: {{newsdetail.publishedAt}}</span>
        </div>
    </div>
    <div class="row">
        <div class="col-md-12">
            <div class="row">
                <img class="img-container" src="" alt="" v-bind:src="newsdetail.urlToImage"/>
            </div>
            {{newsdetail.content}}
            <br>
                <br>
                    <span>Read More: </span> <a href="newsdetail.url">{{newsdetail.url}}</a>
                        <br>
                            <br>
                            <button class="btn-sm btn-primary">Mark As Read</button>

        </div>
    </div>
</div>
</template>

<script>
export default {
    name: '',
    props: {
        newsdetail: Object
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .img-container {
        margin: 20px;
        margin-left: 50px;
        width: 30em;
        line-height: 115px;
        text-align: center;
        vertical-align: middle;
    }

    .niceformat {
        color: blue;
        font-size: medium;
        font-weight: bold;
    }
</style>