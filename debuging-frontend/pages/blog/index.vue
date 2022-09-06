<template>
    <div class="main">
        <section class="container blog-landing">
            <BlogLanding :title="landing.title" :description="landing.description">
                <LandingIcon />
            </BlogLanding>
        </section>
        <section class="container blog-section-wrapper">
            <div class="blogs">
                <BlogItem
                    v-for="blog in blogsPreview"
                    :key="blog.id"
                    :blogData="blog"
                />
            </div>
            <div class="blog-card">
                <BlogCard />
            </div>
        </section>
    </div>
</template>

<script>
export default {
    data() {
        return {
            landing:{
                title: 'Blog',
                description: 'Elit anim nulla ut voluptate sit consectetur exercitation adipisicing consequat fugiat ipsum minim occaecat.',    
            },
            blogsPreview:[
                {
                    title: 'Color and psychological functioning: a review of theoretical sadklfj  asdlfk jasdflkjsadfasdlfk sad',
                    description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Animi quasi repellendus necessitatibus adipisci in. Deleniti illo similique eveniet repellendus, modi debitis id nobis necessitatibus iste reprehenderit voluptatem, recusandae maxime! Iusto!',
                    imageUrl: '/imgs/blog-test1.jpg',
                    writer: {
                        name: 'Shayan Azali',
                        imageUrl: '/imgs/testProfile.jpg',
                    },
                    publishedAt: 'aug 7',
                    timeToRead: '7',
                },
                {
                    title: 'Color and psychological functioning: a review of theoretical sadklfj  asdlfk jasdflkjsadfasdlfk sad',
                    description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Animi quasi repellendus necessitatibus adipisci in. Deleniti illo similique eveniet repellendus, modi debitis id nobis necessitatibus iste reprehenderit voluptatem, recusandae maxime! Iusto!',
                    imageUrl: '/imgs/blog-test2.jpg',
                    writer: {
                        name: 'Shayan Azali',
                        imageUrl: '/imgs/testProfile.jpg',
                    },
                    publishedAt: 'aug 7',
                    timeToRead: '7',
                },
                {
                    title: 'Color and psychological functioning: a review of theoretical sadklfj  asdlfk jasdflkjsadfasdlfk sad',
                    description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Animi quasi repellendus necessitatibus adipisci in. Deleniti illo similique eveniet repellendus, modi debitis id nobis necessitatibus iste reprehenderit voluptatem, recusandae maxime! Iusto!',
                    imageUrl: '/imgs/blog-test3.jpg',
                    writer: {
                        name: 'Shayan Azali',
                        imageUrl: '/imgs/testProfile.jpg',
                    },
                    publishedAt: 'aug 7',
                    timeToRead: '7',
                },
                {
                    title: 'Color and psychological functioning: a review of theoretical sadklfj  asdlfk jasdflkjsadfasdlfk sad',
                    description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Animi quasi repellendus necessitatibus adipisci in. Deleniti illo similique eveniet repellendus, modi debitis id nobis necessitatibus iste reprehenderit voluptatem, recusandae maxime! Iusto!',
                    imageUrl: '/imgs/blog-test1.jpg',
                    writer: {
                        name: 'Shayan Azali',
                        imageUrl: '/imgs/testProfile.jpg',
                    },
                    publishedAt: 'aug 7',
                    timeToRead: '7',
                },
                {
                    title: 'Color and psychological functioning: a review of theoretical sadklfj  asdlfk jasdflkjsadfasdlfk sad',
                    description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Animi quasi repellendus necessitatibus adipisci in. Deleniti illo similique eveniet repellendus, modi debitis id nobis necessitatibus iste reprehenderit voluptatem, recusandae maxime! Iusto!',
                    imageUrl: '/imgs/blog-test2.jpg',
                    writer: {
                        name: 'Shayan Azali',
                        imageUrl: '/imgs/testProfile.jpg',
                    },
                    publishedAt: 'aug 7',
                    timeToRead: '7',
                },
                {
                    title: 'Color and psychological functioning: a review of theoretical sadklfj  asdlfk jasdflkjsadfasdlfk sad',
                    description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Animi quasi repellendus necessitatibus adipisci in. Deleniti illo similique eveniet repellendus, modi debitis id nobis necessitatibus iste reprehenderit voluptatem, recusandae maxime! Iusto!',
                    imageUrl: '/imgs/blog-test3.jpg',
                    writer: {
                        name: 'Shayan Azali',
                        imageUrl: '/imgs/testProfile.jpg',
                    },
                    publishedAt: 'aug 7',
                    timeToRead: '7',
                },
                {
                    title: 'Color and psychological functioning: a review of theoretical sadklfj  asdlfk jasdflkjsadfasdlfk sad',
                    description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Animi quasi repellendus necessitatibus adipisci in. Deleniti illo similique eveniet repellendus, modi debitis id nobis necessitatibus iste reprehenderit voluptatem, recusandae maxime! Iusto!',
                    imageUrl: '/imgs/blog-test1.jpg',
                    writer: {
                        name: 'Shayan Azali',
                        imageUrl: '/imgs/testProfile.jpg',
                    },
                    publishedAt: 'aug 7',
                    timeToRead: '7',
                },
                {
                    title: 'Color and psychological functioning: a review of theoretical sadklfj  asdlfk jasdflkjsadfasdlfk sad',
                    description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Animi quasi repellendus necessitatibus adipisci in. Deleniti illo similique eveniet repellendus, modi debitis id nobis necessitatibus iste reprehenderit voluptatem, recusandae maxime! Iusto!',
                    imageUrl: '/imgs/blog-test2.jpg',
                    writer: {
                        name: 'Shayan Azali',
                        imageUrl: '/imgs/testProfile.jpg',
                    },
                    publishedAt: 'aug 7',
                    timeToRead: '7',
                },
                {
                    title: 'Color and psychological functioning: a review of theoretical sadklfj  asdlfk jasdflkjsadfasdlfk sad',
                    description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Animi quasi repellendus necessitatibus adipisci in. Deleniti illo similique eveniet repellendus, modi debitis id nobis necessitatibus iste reprehenderit voluptatem, recusandae maxime! Iusto!',
                    imageUrl: '/imgs/blog-test3.jpg',
                    writer: {
                        name: 'Shayan Azali',
                        imageUrl: '/imgs/testProfile.jpg',
                    },
                    publishedAt: 'aug 7',
                    timeToRead: '7',
                },
            ]
        }
    },
    components:{
        BlogLanding:() => import('@/components/modules/landing-section-item.vue') ,
        LandingIcon: () => import('@/components/icons/blog/landingIcon.vue'),
        BlogItem:() => import('@/components/modules/blog-item.vue'),
        BlogCard:() => import('@/components/sections/blog/blog-card/index.vue'),
    }
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/global.scss';

.blog-section-wrapper{
    margin-top: 200px;
    width: 100%;
    display: flex;
    flex-direction: column-reverse;
    align-items: flex-start;
    @include mq(lg){
        flex-direction: row;
        justify-content: space-between;
    }
}

.blogs{
    width: 100%;
    @include mq(lg){
        flex-basis: 60%;
    }
}

.blog-card{
    width: 100%;
    @include mq(lg){
        position: sticky;
        top: 0;
        padding: 0px 20px;
        flex-basis: 40%;
    }

    @include mq(xlg){
        padding: 0px 50px;
        flex-basis: 40%;
    }
}
</style>