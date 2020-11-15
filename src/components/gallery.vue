<template>
    <div class="gallery-container">
        <div class="images-box">
            <div class="img-1"
                @click="img1Clicked">
            </div>
            <div class="img-2"
                @click="img2Clicked">
            </div>
            <div class="img-3"
                @click="img3Clicked">
            </div>
            <div class="img-4"
                @click="img4Clicked" 
                @mouseenter="img4MouseEnter" 
                @mouseleave="img4MouseLeave">
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return{
            img1: document.getElementsByClassName('img-1'),
            img2: document.getElementsByClassName('img-2'),
            img3: document.getElementsByClassName('img-3'),
            img4: document.getElementsByClassName('img-4')
        }
    },
    methods: {
        img4MouseEnter(){
            this.img4[0].style.zIndex = 11;
        },
        img4MouseLeave(){
            if(this.img4[0].classList.length != 2){
                setTimeout(() => {
                    this.img4[0].style.zIndex = 1;
                } , 1200);
            }
        },

        img1Clicked(){
            this.img1[0].classList.toggle('img1-cover');
        },
        img2Clicked(){
            this.img2[0].classList.toggle('img2-cover');
        },
        img3Clicked(){
            this.img3[0].classList.toggle('img3-cover');
        },
        img4Clicked(){
            this.img4[0].classList.toggle('img4-cover');
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
        // image 1 styles
        .img-1{
            width: inherit;
            height: inherit;
            clip-path: polygon(25% 0%, 75% 0%, 100% 50%, 100% 50%, 100% 50%, 100% 50%);
            position: absolute;
            @include image('../assets/img-1.jpg');
            transition: 1200ms ease;
            z-index: 10; 
            cursor: pointer;

            &:hover{
                clip-path: polygon(25% 0%, 75% 0%, 100% 50%, 75% 100%, 75% 100%, 75% 100%);
            }
        }
        .img1-cover{
            transition: all 1200ms;
            clip-path: polygon(25% 0%, 75% 0%, 100% 50%, 75% 100%, 25% 100%, 0% 50%) !important;
            z-index: 100;
        }
        // image 2 styles
        .img-2{
            width: inherit;
            height: inherit;
            clip-path: polygon(25% 0%, 100% 50%, 75% 100%, 75% 100%, 75% 100%, 75% 100%);
            position: absolute;
            @include image('../assets/img-5.jpg');
            transition: 1200ms ease;
            z-index: 9;
            cursor: pointer;

            &:hover{
                clip-path: polygon(25% 0%, 100% 50%, 100% 50%, 75% 100%, 25% 100%, 25% 100%);
            }
        }
        .img2-cover{
            transition: all 1200ms;
            clip-path: polygon(25% 0%, 75% 0%, 100% 50%, 75% 100%, 25% 100%, 0% 50%) !important;
            z-index: 100;
        }
        // image 3 styles
        .img-3{
            width: inherit;
            height: inherit;
            clip-path: polygon(25% 0%, 75% 100%, 75% 100%, 75% 100%, 25% 100%, 25% 100%);
            position: absolute;
            @include image('../assets/img-6.jpg');
            transition: 1200ms ease;
            z-index: 8;
            cursor: pointer;

            &:hover{
                clip-path: polygon(25% 0%, 75% 100%, 75% 100%, 75% 100%, 25% 100%, 0% 50%);
            }
        }
        .img3-cover{
            transition: all 1200ms;
            clip-path: polygon(25% 0%, 75% 0%, 100% 50%, 75% 100%, 25% 100%, 0% 50%) !important;
            z-index: 100;
        }
        // image 4  styles
        .img-4{
            width: inherit;
            height: inherit;
            clip-path: polygon(25% 0%, 25% 100%, 25% 100%, 25% 100%, 25% 100%, 0% 50%);
            position: absolute;
            @include image('../assets/img-8.jpg');
            transition: 1200ms ease;
            cursor: pointer;

            &:hover{
                clip-path: polygon(25% 0%, 75% 100%, 75% 100%, 75% 100%, 25% 100%, 0% 50%);
            }
        }
        .img4-cover{
            transition: all 1200ms;
            clip-path: polygon(25% 0%, 75% 0%, 100% 50%, 75% 100%, 25% 100%, 0% 50%) !important;
            z-index: 100;
        }

        @media only screen and (max-width: 650px){
            width: 25rem;
            height: 25rem;
        }
        @media only screen and (max-width: 450px){
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