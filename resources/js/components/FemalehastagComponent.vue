<template>
    <div class="female-hashtag">
        <h1 class="text-center">#Vue.js</h1>
        <div class="count" id="female-count">
            <ul>
                <li></li>
                <li></li>
                <li></li>
                <li></li>
                <li></li>
                <li></li>
                <li></li>
                <div class="clear"></div>
            </ul>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                vue: ""
            }
        },
        created() {
            this.getCount();
            setInterval(this.getCount, 1000);
        },
        methods: {
            getCount() {
                let base_url = document.getElementById('base_url').value;
                let uri = base_url+'api/count_hastag2';
                this.axios.get(uri).then(response => {
                    this.vue = response.data.vue;
                    this.counter();
                })
            },
            counter() {
                let tags = document.querySelectorAll('#female-count > ul > li');
                let items = [];
                tags.forEach(function(item, i){
                    items[i] = tags[i];
                })
                items = items.reverse();
                let reversedArr = (this.vue+'').split('').reverse();
                items.forEach(function(item, i){
                    setTimeout(function(){
                        let className = 'd' + reversedArr[i] || 0;
                        item.className = className;
                    }, i * 350);
                })
            }
        }
    }
</script>

<style scoped>
.count > ul > li:before {
  content: ' 0 1 2 3 4 5 6 7 8 9 ';
  display: block;
  word-break: break-all;
  word-break: break-word;
  transition: 0.7s cubic-bezier(0.12, 0.78, 0.52, 1.2);
  line-height: 45px;
  font-weight: bold;
  text-shadow: 0 1px 0 #ccc,
               0 2px 0 #c9c9c9,
               0 3px 0 #bbb,
               0 0px 0 #b9b9b9,
               0 0px 0 #aaa,
               0 6px 1px rgba(0,0,0,.1),
               0 0 5px rgba(0,0,0,.1),
               0 1px 3px rgba(0,0,0,.3),
               0 3px 5px rgba(0,0,0,.2),
               0 5px 10px rgba(0,0,0,.25),
               0 10px 10px rgba(0,0,0,.2),
               0 20px 20px rgba(0,0,0,.15);
}
.count > ul > li.d1:before {
  margin-top: -45px;
}
.count > ul > li.d2:before {
  margin-top: -90px;
}
.count > ul > li.d3:before {
  margin-top: -135px;
}
.count > ul > li.d4:before {
  margin-top: -180px;
}
.count > ul > li.d5:before {
  margin-top: -225px;
}
.count > ul > li.d6:before {
  margin-top: -270px;
}
.count > ul > li.d7:before {
  margin-top: -315px;
}
.count > ul > li.d8:before {
  margin-top: -360px;
}
.count > ul > li.d9:before {
  margin-top: -405px;
}
</style>