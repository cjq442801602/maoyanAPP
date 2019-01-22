<template>
    <div>
        <header>
            <img :src="pic"/>
            <h2>猫眼电影</h2>
        </header>
    </div>
</template>
<script type="text/javascript">
    import '../styles/all.css'
    import pic from '../assets/jiantou.png'

    export default {
        data(){
            return{
                pic
            }
        }
    }
</script>
<style scoped>
    header{height: 51.5px;width: 100%;background: #e54847;}
    header>img{position:absolute;left:0;top:0;height:51.5px;}
    header>h2{font-size: 18px;color:#fff;text-align: center;line-height: 49px;}
</style>