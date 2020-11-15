<template>
    <div class="gallery-container">
        <div class="images-box">
            <div class="img-1"></div>
            <div class="img-2"></div>
            <div class="img-3"></div>
            <div class="img-4" 
                @mouseenter="img4MouseEnter" 
                @mouseleave="img4MouseLeave"
                ref="img4">
            </div>
        </div>
    </div>
</template>

<script>
export default {
    methods: {
        img4MouseEnter(){
            console.log(document.getElementsByClassName('img-4')[0].style);
            document.getElementsByClassName('img-4')[0].style.zIndex = 11;
        },
        img4MouseLeave(){
            setTimeout(() => {
                document.getElementsByClassName('img-4')[0].style.zIndex = 1;
            } , 1200)
        }
    }
}
</script>

<style lang="scss" scoped>
@import '../scss/mixins';

.gallery-container{
    @include flex;

    .images-box{
        width: 35rem;
        height: 35rem;
        clip-path: polygon(25% 0%, 75% 0%, 100% 50%, 75% 100%, 25% 100%, 0% 50%);
        background: #101010;
        position: relative;
        .img-1{
            width: inherit;
            height: inherit;
            clip-path: polygon(25% 0%, 75% 0%, 100% 50% , 100% 50%);
            position: absolute;
            @include image('../assets/img-1.jpg');
            transition: clip-path 1200ms ease;
            z-index: 10; 
            cursor: pointer;

            &:hover{
                clip-path: polygon(25% 0%, 75% 0%, 100% 50%, 75% 100%);
            }
        }
        .img-2{
            width: inherit;
            height: inherit;
            clip-path: polygon(25% 0%, 100% 50%, 75% 100%, 75% 100%, 75% 100%);
            position: absolute;
            @include image('../assets/img-5.jpg');
            transition: clip-path 1200ms ease;
            z-index: 9;
            cursor: pointer;

            &:hover{
                clip-path: polygon(25% 0%, 100% 50%, 100% 50%, 75% 100%, 25% 100%);
            }
        }
        .img-3{
            width: inherit;
            height: inherit;
            clip-path: polygon(25% 0%, 75% 100%, 25% 100%, 25% 100%);
            position: absolute;
            @include image('../assets/img-6.jpg');
            transition: clip-path 1200ms ease;
            z-index: 8;
            cursor: pointer;

            &:hover{
                clip-path: polygon(25% 0%, 75% 100%, 25% 100%, 0% 50%);
            }
        }
        .img-4{
            width: inherit;
            height: inherit;
            clip-path: polygon(25% 0%, 25% 100%, 25% 100%, 0% 50%);
            position: absolute;
            @include image('../assets/img-8.jpg');
            transition: clip-path 1200ms ease;
            cursor: pointer;

            &:hover{
                clip-path: polygon(25% 0%, 75% 100%, 25% 100%, 0% 50%);
            }
        }

        @media only screen and (max-width: 650px){
            width: 20rem;
            height: 20rem;
        }
        @media only screen and (max-width: 350px){
            width: 15rem;
            height: 15rem;
        }
    }
}
</style>