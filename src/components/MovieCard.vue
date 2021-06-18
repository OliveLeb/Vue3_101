<template>
    <div class="card card full-image">
        <div class="wrapper" :style="{backgroundImage:`url(${image})`}">
            <div class="header">
            <div class="date">
                <span class="day">{{splitDate[0]}}</span>
                <span class="month">{{splitDate[1]}}</span>
                <span class="year">{{splitDate[2]}}</span>
            </div>
            <ul class="menu-content">
                <li>
                <a href="#" :class="['fa', statusBookmark ? 'fa-bookmark' : 'fa-bookmark-o']" @click.prevent="toggleStatus('statusBookmark')"></a>
                </li>
                <li>
                <a href="#" :class="['fa',statusLike ? 'fa-heart' : 'fa-heart-o']" @click.prevent="toggleStatus('statusLike')">
                    <span>{{myNbLikes}}</span>
                </a>
                </li>
                <li>
                <a href="#" class="fa fa-comment-o" >
                    <span>{{comment}}</span>
                </a>
                </li>
            </ul>
            </div>
            <div class="data">
            <div class="content">
                <span class="category">{{category}}</span>
                <h1 class="title">
                <a href="#">{{title}}</a>
                </h1>
                <p class="text">
                {{resume}}
                </p>
                <a :href="trailer" class="button" target="_blank" rel="noopener noreferrer">
                Trailer
                </a>
            </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name : 'MovieCard', 
    props : {
        id: {
            type: String,
            required: true,
        },
        title: {
            type: String,
            required: true,
        },
        date : String,
        category : String,
        resume : String,
        like : {
            type : Boolean,
            default: false,
        },
        nbLike : {
            type: Number,
            default: 0
        },
        comment : {
            type: Number,
            default: 0
        },
        bookmark : {
            type : Boolean,
            default : false
        },
        trailer : String,
        image : {
            type: String,
            required: true,
        }
    },
    data() {
        return {
            statusLike : this.like,
            myNbLikes : this.nbLike,
            statusBookmark : this.bookmark
        }
    },
    methods: {
        toggleStatus(status) {
            if(status === 'statusLike') {
                this.statusLike = ! this.statusLike;
                return;
            }
            if(status === 'statusBookmark') return this.statusBookmark = ! this.statusBookmark;
        }
    },
    watch: {
        statusLike(value) {
            this.myNbLikes += value ? 1 : -1;
        }
    },
    computed: {
        splitDate() {
            return this.date.split(' ');
        }
    }
}
</script>

<style scoped>

.card {
  float: left;
  padding: 1.7rem;
  width: 50%;
}
.card .menu-content {
  margin: 0;
  padding: 0;
  list-style-type: none;
}
.card .menu-content::before,
.card .menu-content::after {
  content: '';
  display: table;
}
.card .menu-content::after {
  clear: both;
}
.card .menu-content li {
  display: inline-block;
}
.card .menu-content a {
  color: #fff;
}
.card .menu-content span {
  position: absolute;
  left: 50%;
  top: 0;
  font-size: 10px;
  font-weight: 700;
  font-family: 'Open Sans';
  -webkit-transform: translate(-50%, 0);
  transform: translate(-50%, 0);
}
.card .wrapper {
  background-color: #fff;
  min-height: 540px;
  position: relative;
  overflow: hidden;
  box-shadow: 0 19px 38px rgba(0, 0, 0, 0.3), 0 15px 12px rgba(0, 0, 0, 0.2);
}
.card .wrapper:hover .data {
  -webkit-transform: translateY(0);
  transform: translateY(0);
}
.card .data {
  position: absolute;
  bottom: 0;
  width: 100%;
  -webkit-transform: translateY(calc(70px + 1em));
  transform: translateY(calc(70px + 1em));
  transition: -webkit-transform 0.3s;
  transition: transform 0.3s;
  transition: transform 0.3s, -webkit-transform 0.3s;
}
.card .data .content {
  padding: 1em;
  position: relative;
  z-index: 1;
}
.card .category {
  font-size: 12px;
}
.card .title {
  margin-top: 10px;
}
.card .text {
  height: 70px;
  margin: 0;
}
.card input[type='checkbox'] {
  display: none;
}
.card input[type='checkbox']:checked + .menu-content {
  -webkit-transform: translateY(-60px);
  transform: translateY(-60px);
}

.full-image .wrapper {
  background-size: cover;
}

.full-image .wrapper:hover .menu-content span {
  -webkit-transform: translate(-50%, -10px);
  transform: translate(-50%, -10px);
  opacity: 1;
}
.full-image .header {
  color: #fff;
  padding: 1em;
}
.full-image .header::before,
.full-image .header::after {
  content: '';
  display: table;
}
.full-image .header::after {
  clear: both;
}
.full-image .header .date {
  float: left;
  font-size: 12px;
}
.full-image .menu-content {
  float: right;
}
.full-image .menu-content li {
  margin: 0 5px;
  position: relative;
}
.full-image .menu-content span {
  transition: all 0.3s;
  opacity: 0;
}
.full-image .data {
  color: #fff;
  -webkit-transform: translateY(calc(70px + 4em));
  transform: translateY(calc(70px + 4em));
}
.full-image .title a {
  color: #fff;
}
.full-image .date span {
  margin-right: 5px;
}
.full-image .button {
  display: block;
  width: 100px;
  margin: 2em auto 1em;
  text-align: center;
  font-size: 12px;
  color: #fff;
  line-height: 1;
  position: relative;
  font-weight: 700;
}
.full-image .button::after {
  content: '\2192';
  opacity: 0;
  position: absolute;
  right: 0;
  top: 50%;
  -webkit-transform: translate(0, -50%);
  transform: translate(0, -50%);
  transition: all 0.3s;
}
.full-image .button:hover::after {
  -webkit-transform: translate(5px, -50%);
  transform: translate(5px, -50%);
  opacity: 1;
}
</style>