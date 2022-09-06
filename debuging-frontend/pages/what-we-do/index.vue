<template>
    <div class="main">

        <section class="container what-we-do-landing">
            <Landing :title="landing.title" :description="landing.description">
                <LandingIcon />
            </Landing>
        </section>

        <section class="container information-box-wrapper">
            <InformationBox :description="information.description" />
        </section>

        <section class="container services-section-wrapper">
            <ServicesHeader />
            <div class="services-section-container-wrapper">
                <CardItem v-for="card in cards" :key="card.title">
                    <services :icon="card.icon" :title="card.title" :content="card.content" />
                </CardItem>
            </div>
        </section>

        <section class="container advantage-section-wrapper">
            <Advantage v-for="advantage in advantages" :key="advantage.index" :title="advantage.title" :description="advantage.description" :image="advantage.image"/>
            <div class="cta">
                <Cta />
            </div>
        </section>

        <section class="container carousel-items">
            <div class="carousel-development-languages">
                <CarouselTitles :title="titleLanguage.title" />
                <Carousel wrapperClasses="development-languages" :optionsArray="optionsArray">
                    <CarouselSlide v-for="language in languages" :key="language.id">
                        <DevelopmentLanguages :icon="language.icon" :title="language.title" />
                    </CarouselSlide>
                </Carousel>
            </div>

            <div class="carousel-frontend-tech">
                <CarouselTitles :title="titleFrontend.title" />
                <Carousel wrapperClasses="frontend-carousel" :optionsArray="optionsArray">
                    <CarouselSlide v-for="frontend in frontends" :key="frontend.id">
                        <DevelopmentLanguages :icon="frontend.icon" :title="frontend.title" />
                    </CarouselSlide>
                </Carousel>
            </div>
    
            <!--<div class="carousel-backend-tech">
                <CarouselTitles :title="titleBackend.title" />
                <Carousel wrapperClasses="backend-carousel" :optionsArray="optionsArray">
                    <CarouselSlide v-for="backend in backends" :key="backend.id">
                        <DevelopmentLanguages :icon="backend.icon" :title="backend.title" />
                    </CarouselSlide>
                </Carousel>
            </div> -->
    
           <div class="carousel-database-tech">
                <CarouselTitles :title="titleDatabase.title" />
                <Carousel wrapperClasses="database-carousel" :optionsArray="optionsArray">
                    <CarouselSlide v-for="database in databases" :key="database.id">
                        <DevelopmentLanguages :icon="database.icon" :title="database.title" />
                    </CarouselSlide>
                </Carousel>
            </div>
    
            <div class="carousel-devops-tech">
                <CarouselTitles :title="titleDevops.title" />
                <Carousel wrapperClasses="devops-carousel" :optionsArray="optionsArray">
                    <CarouselSlide v-for="devops in devopses" :key="devops.id">
                        <DevelopmentLanguages :icon="devops.icon" :title="devops.title" />
                    </CarouselSlide>
                </Carousel>
            </div>
        </section>

    </div>
</template>

<script>
export default {
    name:"PromotionSection",
    components:{
        Landing: () => import("@/components/modules/landing-section-item.vue"),
        LandingIcon: () => import("@/components/icons/what-we-do/landingIcon.vue"),
        InformationBox: () => import("@/components/misc/informationBox.vue"),
        CardItem: () => import("@/components/modules/card-item.vue"),
        ServicesHeader: () => import("@/components/sections/what-we-do/services-section/servicesHeader.vue"),
        Services: () => import("~/components/sections/what-we-do/services-section/servicesContainer.vue"),
        Advantage: () => import("@/components/sections/what-we-do/advantage/advantage.vue"),
        Cta: () => import("@/components/misc/cta.vue"),
        Carousel: () => import("@/components/modules/carousel/Carousel.vue"),
        CarouselSlide: () => import("@/components/modules/carousel/CarouselSlide.vue"),
        CarouselTitles: () => import("@/components/sections/what-we-do/languages-carousel/carouselTitle.vue"),
        DevelopmentLanguages: () => import("@/components/sections/what-we-do/languages-carousel/developmentLanguages.vue"),
    },
    data() {
        return {
            landing:{
                title:'One stop studio for all your web needs',
                description:'Veniam quis velit magna cillum eu Lorem laboris. Veniam quis velit magna cillum eu Lorem laboris.',
            },
            information:{
                description:'When approaching any project, we empathise the owners, try to get the best understanding of project needs, then incorporate our expertise to create the best user experience in a useful, meaningful way.'
            },
            cards:[
                {
                    icon: '<svg width="50" height="50" viewBox="0 0 70 70" fill="none" xmlns="http://www.w3.org/2000/svg"><g clip-path="url(#clip0_359_14305)"><path d="M62.4968 67.8125H7.80933C4.80151 67.8125 2.34058 65.3516 2.34058 62.3438V7.65625C2.34058 4.64844 4.80151 2.1875 7.80933 2.1875H62.4968C65.5046 2.1875 67.9656 4.64844 67.9656 7.65625V62.3438C67.9656 65.3516 65.5046 67.8125 62.4968 67.8125Z" fill="white"/><path d="M24.2156 67.8125C24.2156 68.7183 23.4807 69.4531 22.575 69.4531C21.6692 69.4531 20.9343 68.7183 20.9343 67.8125C20.9343 66.9067 21.6692 66.1719 22.575 66.1719C23.4807 66.1719 24.2156 66.9067 24.2156 67.8125Z" fill="#3EBDB9"/><path d="M13.2781 69.4531H7.80933C3.87225 69.4531 0.699951 66.2808 0.699951 62.3438V22.4219C0.699951 21.4926 1.41132 20.7812 2.34058 20.7812C3.26984 20.7812 3.9812 21.4926 3.9812 22.4219V62.3438C3.9812 64.4757 5.67737 66.1719 7.80933 66.1719H13.2781C14.2073 66.1719 14.9187 66.8832 14.9187 67.8125C14.9187 68.7418 14.2073 69.4531 13.2781 69.4531Z" fill="#444B54"/><path d="M67.9656 42.1094C67.0363 42.1094 66.325 41.398 66.325 40.4688V7.65625C66.325 5.52429 64.6288 3.82812 62.4968 3.82812H7.80933C5.67737 3.82812 3.9812 5.52429 3.9812 7.65625V13.6719H60.8562C61.7855 13.6719 62.4968 14.3832 62.4968 15.3125C62.4968 16.2418 61.7855 16.9531 60.8562 16.9531H2.34058C1.41132 16.9531 0.699951 16.2418 0.699951 15.3125V7.65625C0.699951 3.71918 3.87225 0.546875 7.80933 0.546875H62.4968C66.4339 0.546875 69.6062 3.71918 69.6062 7.65625V40.4688C69.6062 41.398 68.8948 42.1094 67.9656 42.1094Z" fill="#444B54"/><path d="M10.5437 8.75C10.5437 9.65576 9.80884 10.3906 8.90308 10.3906C7.99731 10.3906 7.26245 9.65576 7.26245 8.75C7.26245 7.84424 7.99731 7.10938 8.90308 7.10938C9.80884 7.10938 10.5437 7.84424 10.5437 8.75Z" fill="#444B54"/><path d="M16.0125 8.75C16.0125 9.65576 15.2776 10.3906 14.3718 10.3906C13.4661 10.3906 12.7312 9.65576 12.7312 8.75C12.7312 7.84424 13.4661 7.10938 14.3718 7.10938C15.2776 7.10938 16.0125 7.84424 16.0125 8.75Z" fill="#444B54"/><path d="M21.4812 8.75C21.4812 9.65576 20.7463 10.3906 19.8406 10.3906C18.9348 10.3906 18.2 9.65576 18.2 8.75C18.2 7.84424 18.9348 7.10938 19.8406 7.10938C20.7463 7.10938 21.4812 7.84424 21.4812 8.75Z" fill="#444B54"/><path d="M65.2312 48.6719H58.3953C57.9573 48.6719 57.6839 48.454 57.575 48.2895C57.466 48.1805 57.246 47.8516 57.3015 47.4692L58.1774 38.9926C58.3397 37.2964 57.7928 35.5469 56.6457 34.2886C55.4964 33.0304 53.8558 32.2656 52.1062 32.2656C50.3566 32.2656 48.716 32.977 47.5667 34.2886C46.4196 35.5469 45.8727 37.2964 46.035 38.9926L46.9109 47.4692C46.9664 47.9071 46.7464 48.1805 46.6375 48.2895C46.5285 48.3984 46.2551 48.6719 45.8171 48.6719H38.9812C36.5758 48.6719 34.6062 50.6415 34.6062 53.0469V62.3438C34.6062 64.4757 32.91 66.1719 30.7781 66.1719C29.8488 66.1719 29.1375 66.8832 29.1375 67.8125C29.1375 68.7418 29.8488 69.4531 30.7781 69.4531H62.4968C66.4339 69.4531 69.6062 66.2808 69.6062 62.3438V53.0469C69.6062 50.6415 67.6366 48.6719 65.2312 48.6719ZM38.9812 51.9531H45.8171C47.0754 51.9531 48.2225 51.4062 49.0428 50.5304C49.8632 49.6011 50.3011 48.3984 50.1366 47.1402L49.2629 38.6636C49.2073 37.8433 49.4274 37.0786 49.9742 36.4761C50.5211 35.8759 51.2303 35.5469 52.0507 35.5469C52.871 35.5469 53.5823 35.8759 54.1292 36.4761C54.6761 37.0786 54.9495 37.8433 54.8406 38.6636L53.9647 47.1402C53.8558 48.3429 54.2382 49.6011 55.0585 50.5304C55.8788 51.4618 57.0836 51.9531 58.2863 51.9531H65.2312C65.8336 51.9531 66.325 52.4445 66.325 53.0469V56.875H37.8875V53.0469C37.8875 52.4445 38.3788 51.9531 38.9812 51.9531Z" fill="#3EBDB9"/></g><defs><clipPath id="clip0_359_14305"><rect width="70" height="70" fill="white"/></clipPath></defs></svg>',
                    title: 'UI/UX',
                    content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod.',  
                },
                {
                    icon: '<svg width="50" height="50" viewBox="0 0 70 70" fill="none" xmlns="http://www.w3.org/2000/svg"><g clip-path="url(#clip0_359_16683)"><path d="M62.3438 67.8125H7.65625C4.64844 67.8125 2.1875 65.3516 2.1875 62.3438V7.65625C2.1875 4.64844 4.64844 2.1875 7.65625 2.1875H62.3438C65.3516 2.1875 67.8125 4.64844 67.8125 7.65625V62.3438C67.8125 65.3516 65.3516 67.8125 62.3438 67.8125Z" fill="white"/><path d="M51.9531 64.8047C48.9453 64.8047 46.4844 62.3438 46.4844 59.3359C46.4844 56.3281 48.9453 53.8672 51.9531 53.8672C54.9609 53.8672 57.4219 56.3281 57.4219 59.3359C57.4219 62.3438 54.9609 64.8047 51.9531 64.8047ZM51.9531 57.1484C50.7504 57.1484 49.7656 58.1332 49.7656 59.3359C49.7656 60.5386 50.7504 61.5234 51.9531 61.5234C53.1558 61.5234 54.1406 60.5386 54.1406 59.3359C54.1406 58.1332 53.1558 57.1484 51.9531 57.1484Z" fill="#3EBDB9"/><path d="M26.7969 29.8047C25.8676 29.8047 25.1562 30.5161 25.1562 31.4453V49.9301L20.5634 54.523C19.7964 54.1406 18.9227 53.9227 18.0469 53.9227C15.0391 53.9227 12.5781 56.3837 12.5781 59.3915C12.5781 62.3993 15.0391 64.8602 18.0469 64.8602C21.0547 64.8602 23.5156 62.3993 23.5156 59.3915C23.5156 58.4601 23.2977 57.6398 22.9132 56.875L27.9996 51.7886C28.3286 51.4618 28.493 51.0773 28.493 50.6415V31.5009C28.4375 30.5161 27.7261 29.8047 26.7969 29.8047ZM18.0469 61.5234C16.8442 61.5234 15.8594 60.5386 15.8594 59.3359C15.8594 58.1332 16.8442 57.1484 18.0469 57.1484C19.2496 57.1484 20.2344 58.1332 20.2344 59.3359C20.2344 60.5386 19.2496 61.5234 18.0469 61.5234Z" fill="#3EBDB9"/><path d="M44.8438 49.9301V36.9141C44.8438 35.9848 44.1324 35.2734 43.2031 35.2734C42.2739 35.2734 41.5625 35.9848 41.5625 36.9141V50.5859C41.5625 51.0239 41.727 51.4618 42.0538 51.7352L48.0695 57.7509C48.3984 58.0777 48.8364 58.2422 49.2188 58.2422C49.6011 58.2422 50.0391 58.0777 50.368 57.7509C51.0239 57.0929 51.0239 56.0547 50.368 55.4523L44.8438 49.9301Z" fill="#3EBDB9"/><path d="M36.6406 59.0625V25.9766C36.6406 25.0473 35.9293 24.3359 35 24.3359C34.0707 24.3359 33.3594 25.0473 33.3594 25.9766V59.0625C31.1163 59.7739 29.5312 61.8524 29.5312 64.2578C29.5312 67.2656 31.9922 69.7266 35 69.7266C38.0078 69.7266 40.4688 67.2656 40.4688 64.2578C40.4688 61.7969 38.8837 59.7183 36.6406 59.0625ZM35 66.4453C33.7973 66.4453 32.8125 65.4605 32.8125 64.2578C32.8125 63.0551 33.7973 62.0703 35 62.0703C36.2027 62.0703 37.1875 63.0551 37.1875 64.2578C37.1875 65.4605 36.2027 66.4453 35 66.4453Z" fill="#3EBDB9"/><path d="M59.6094 39.6484C58.6802 39.6484 57.8598 39.8663 57.0929 40.2508L52.0087 35.1645C51.3508 34.5087 50.3125 34.5087 49.7101 35.1645C49.0543 35.8203 49.0543 36.8585 49.7101 37.4609L54.7965 42.5473C54.4141 43.3121 54.1962 44.1879 54.1962 45.0616C54.1962 48.0694 56.6572 50.5304 59.665 50.5304C62.6728 50.5304 65.1337 48.0694 65.1337 45.0616C65.1337 42.0538 62.6172 39.6484 59.6094 39.6484ZM59.6094 47.3047C58.4067 47.3047 57.4219 46.3199 57.4219 45.1172C57.4219 43.9145 58.4067 42.9297 59.6094 42.9297C60.8121 42.9297 61.7969 43.9145 61.7969 45.1172C61.7969 46.3199 60.8121 47.3047 59.6094 47.3047Z" fill="#3EBDB9"/><path d="M15.8593 45.1172C15.8593 44.188 15.6414 43.3677 15.2568 42.6008L20.3432 37.5165C20.999 36.8586 20.999 35.8204 20.3432 35.2179C19.6874 34.5621 18.6492 34.5621 18.0468 35.2179L12.9604 40.3043C12.1956 39.9219 11.3198 39.704 10.446 39.704C7.43823 39.704 4.97729 42.165 4.97729 45.1728C4.97729 48.1806 7.43823 50.6415 10.446 50.6415C13.4539 50.6415 15.8593 48.125 15.8593 45.1172ZM10.3905 47.3047C9.18781 47.3047 8.203 46.3199 8.203 45.1172C8.203 43.9145 9.18781 42.9297 10.3905 42.9297C11.5932 42.9297 12.578 43.9145 12.578 45.1172C12.578 46.3199 11.5932 47.3047 10.3905 47.3047Z" fill="#3EBDB9"/><path d="M2.1875 36.6406C1.25824 36.6406 0.546875 35.9293 0.546875 35V22.4219C0.546875 21.4926 1.25824 20.7812 2.1875 20.7812C3.11676 20.7812 3.82812 21.4926 3.82812 22.4219V35C3.82812 35.9293 3.11676 36.6406 2.1875 36.6406Z" fill="#444B54"/><path d="M67.8125 36.6406C66.8832 36.6406 66.1719 35.9293 66.1719 35V7.65625C66.1719 5.52429 64.4757 3.82812 62.3438 3.82812H7.65625C5.52429 3.82812 3.82812 5.52429 3.82812 7.65625V13.6719H60.7031C61.6324 13.6719 62.3438 14.3832 62.3438 15.3125C62.3438 16.2418 61.6324 16.9531 60.7031 16.9531H2.1875C1.25824 16.9531 0.546875 16.2418 0.546875 15.3125V7.65625C0.546875 3.71918 3.71918 0.546875 7.65625 0.546875H62.3438C66.2808 0.546875 69.4531 3.71918 69.4531 7.65625V35C69.4531 35.9293 68.7418 36.6406 67.8125 36.6406Z" fill="#444B54"/><path d="M10.3906 8.75C10.3906 9.65576 9.65576 10.3906 8.75 10.3906C7.84424 10.3906 7.10938 9.65576 7.10938 8.75C7.10938 7.84424 7.84424 7.10938 8.75 7.10938C9.65576 7.10938 10.3906 7.84424 10.3906 8.75Z" fill="#444B54"/><path d="M15.8594 8.75C15.8594 9.65576 15.1245 10.3906 14.2188 10.3906C13.313 10.3906 12.5781 9.65576 12.5781 8.75C12.5781 7.84424 13.313 7.10938 14.2188 7.10938C15.1245 7.10938 15.8594 7.84424 15.8594 8.75Z" fill="#444B54"/><path d="M21.3281 8.75C21.3281 9.65576 20.5933 10.3906 19.6875 10.3906C18.7817 10.3906 18.0469 9.65576 18.0469 8.75C18.0469 7.84424 18.7817 7.10938 19.6875 7.10938C20.5933 7.10938 21.3281 7.84424 21.3281 8.75Z" fill="#444B54"/></g><defs><clipPath id="clip0_359_16683"><rect width="70" height="70" fill="white"/></clipPath></defs></svg>' ,                   
                    title: 'Backend Development',
                    content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod.',  
                },
                {
                    icon: '<svg width="50" height="50" viewBox="0 0 70 70" fill="none" xmlns="http://www.w3.org/2000/svg"><g clip-path="url(#clip0_365_1855)"><path d="M62.3438 67.8125H7.65625C4.64844 67.8125 2.1875 65.3516 2.1875 62.3438V7.65625C2.1875 4.64844 4.64844 2.1875 7.65625 2.1875H62.3438C65.3516 2.1875 67.8125 4.64844 67.8125 7.65625V62.3438C67.8125 65.3516 65.3516 67.8125 62.3438 67.8125Z" fill="white"/><path d="M26.1945 47.4692C26.8525 48.0695 26.9059 49.1098 26.3056 49.7656C25.9766 50.148 25.5387 50.3125 25.1008 50.3125C24.7184 50.3125 24.336 50.2036 24.007 49.8746L17.3911 43.859C17.0621 43.5321 16.8442 43.0942 16.8442 42.6563C16.8442 42.2183 17.0621 41.727 17.3911 41.4536L24.007 35.3824C24.665 34.7821 25.7032 34.8355 26.3056 35.4913C26.9059 36.1493 26.8525 37.1875 26.1945 37.7899L20.9458 42.6563L26.1945 47.4692ZM41.0712 31.1163L32.0478 55.3989C31.7744 56.1102 31.063 56.546 30.3516 56.4371C30.1871 56.4371 30.0782 56.3837 29.9137 56.3281C29.04 55.9992 28.6555 55.0699 28.9289 54.1962L37.9523 29.9136C38.2813 29.0399 39.2106 28.6554 40.0864 28.9288C40.9601 29.3134 41.3981 30.2426 41.0712 31.1163ZM52.609 43.859L45.9931 49.9301C45.6641 50.2036 45.2817 50.3681 44.8994 50.3681C44.4614 50.3681 44.0235 50.2036 43.6945 49.8212C43.0942 49.1632 43.1476 48.125 43.8056 47.5226L49.0543 42.7118L43.8056 37.8989C43.1476 37.2965 43.0942 36.2583 43.6945 35.6024C44.2969 34.9445 45.3351 34.8911 45.9931 35.4913L52.609 41.5625C52.938 41.8915 53.1559 42.3273 53.1559 42.7652C53.1559 43.2031 52.938 43.5855 52.609 43.859Z" fill="#3EBDB9"/><path d="M62.3438 69.4531H7.65625C3.71918 69.4531 0.546875 66.2808 0.546875 62.3438V22.4219C0.546875 21.4926 1.25824 20.7812 2.1875 20.7812C3.11676 20.7812 3.82812 21.4926 3.82812 22.4219V62.3438C3.82812 64.4757 5.52429 66.1719 7.65625 66.1719H62.3438C64.4757 66.1719 66.1719 64.4757 66.1719 62.3438V7.65625C66.1719 5.52429 64.4757 3.82812 62.3438 3.82812H7.65625C5.52429 3.82812 3.82812 5.52429 3.82812 7.65625V13.6719H60.7031C61.6324 13.6719 62.3438 14.3832 62.3438 15.3125C62.3438 16.2418 61.6324 16.9531 60.7031 16.9531H2.1875C1.25824 16.9531 0.546875 16.2418 0.546875 15.3125V7.65625C0.546875 3.71918 3.71918 0.546875 7.65625 0.546875H62.3438C66.2808 0.546875 69.4531 3.71918 69.4531 7.65625V62.3438C69.4531 66.2808 66.2808 69.4531 62.3438 69.4531Z" fill="#444B54"/><path d="M10.3906 8.75C10.3906 9.65576 9.65576 10.3906 8.75 10.3906C7.84424 10.3906 7.10938 9.65576 7.10938 8.75C7.10938 7.84424 7.84424 7.10938 8.75 7.10938C9.65576 7.10938 10.3906 7.84424 10.3906 8.75Z" fill="#444B54"/><path d="M15.8594 8.75C15.8594 9.65576 15.1245 10.3906 14.2188 10.3906C13.313 10.3906 12.5781 9.65576 12.5781 8.75C12.5781 7.84424 13.313 7.10938 14.2188 7.10938C15.1245 7.10938 15.8594 7.84424 15.8594 8.75Z" fill="#444B54"/><path d="M21.3281 8.75C21.3281 9.65576 20.5933 10.3906 19.6875 10.3906C18.7817 10.3906 18.0469 9.65576 18.0469 8.75C18.0469 7.84424 18.7817 7.10938 19.6875 7.10938C20.5933 7.10938 21.3281 7.84424 21.3281 8.75Z" fill="#444B54"/></g><defs><clipPath id="clip0_365_1855"><rect width="70" height="70" fill="white"/></clipPath></defs></svg>',
                    title: 'Frontend Development',
                    content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod.',
                },
                {
                    icon: '<svg width="55" height="40" viewBox="0 0 77 60" fill="none" xmlns="http://www.w3.org/2000/svg"><g clip-path="url(#clip0_359_14285)"><path d="M8.42188 53.9906V2.30786H68.5781C71.8867 2.30786 74.5938 5.01219 74.5938 8.31748V14.3271L50.5312 57.5963H33.6875V53.9906H8.42188Z" fill="white"/><path d="M68.5781 0.504883H8.42188C7.39969 0.504883 6.61719 1.2866 6.61719 2.30777V52.1876H4.21094C2.22531 52.1876 0.601562 53.8097 0.601562 55.7933C0.601562 57.777 2.22531 59.3991 4.21094 59.3991H39.7031C40.7253 59.3991 41.5078 58.6174 41.5078 57.5962C41.5078 56.5751 40.7253 55.7933 39.7031 55.7933H35.4922V53.9905C35.4922 52.9693 34.7097 52.1876 33.6875 52.1876H10.2266V4.11065H68.5781C69.6003 4.11065 70.3828 3.32893 70.3828 2.30777C70.3828 1.2866 69.6003 0.504883 68.5781 0.504883Z" fill="#3EBDB9"/><path d="M68.5781 57.5962H50.5312C47.2227 57.5962 44.5156 54.8919 44.5156 51.5866V15.5289C44.5156 12.2236 47.2227 9.51929 50.5312 9.51929H68.5781C71.8867 9.51929 74.5938 12.2236 74.5938 15.5289V51.5866C74.5938 54.8919 71.8867 57.5962 68.5781 57.5962Z" fill="white"/><path d="M68.5781 59.399H50.5312C46.2005 59.399 42.7109 55.913 42.7109 51.5865V15.5288C42.7109 11.2024 46.2005 7.71631 50.5312 7.71631H68.5781C72.9089 7.71631 76.3984 11.2024 76.3984 15.5288V51.5865C76.3984 55.913 72.9089 59.399 68.5781 59.399ZM50.5312 11.3221C48.1861 11.3221 46.3203 13.186 46.3203 15.5288V51.5865C46.3203 53.9293 48.1861 55.7932 50.5312 55.7932H68.5781C70.9233 55.7932 72.7891 53.9293 72.7891 51.5865V15.5288C72.7891 13.186 70.9233 11.3221 68.5781 11.3221H50.5312Z" fill="#444B54"/></g><defs><clipPath id="clip0_359_14285"><rect width="77" height="60" fill="white"/></clipPath></defs></svg>',
                    title: 'Progressive Web App',
                    content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod.',
                },
            ],

            advantages:[
                {
                    title: 'Admin Panel',
                    description: 'Magna consectetur exercitation anim proident laborum nostrud nisi cillum excepteur pariatur. Deserunt elit et esse consectetur proident adipisicing do eu ullamco consequat. Voluptate nisi consectetur do aute consectetur occaecat do voluptate culpa fugiat labore sint sunt sint do. Nulla sit nulla quis quis exercitation ex ut aliquip sint Lorem sit. Officia magna aliquip veniam excepteur consectetur irure labore ullamco enim.',
                    image: 'Adminpanel'    
                },
                {
                    title: 'Security',
                    description: 'Magna consectetur exercitation anim proident laborum nostrud nisi cillum excepteur pariatur. Deserunt elit et esse consectetur proident adipisicing do eu ullamco consequat. Voluptate nisi consectetur do aute consectetur occaecat do voluptate culpa fugiat labore sint sunt sint do. Nulla sit nulla quis quis exercitation ex ut aliquip sint Lorem sit. Officia magna aliquip veniam excepteur consectetur irure labore ullamco enim.',
                    image: 'Security'
                },
                {
                    title: 'Performance',
                    description: 'Magna consectetur exercitation anim proident laborum nostrud nisi cillum excepteur pariatur. Deserunt elit et esse consectetur proident adipisicing do eu ullamco consequat. Voluptate nisi consectetur do aute consectetur occaecat do voluptate culpa fugiat labore sint sunt sint do. Nulla sit nulla quis quis exercitation ex ut aliquip sint Lorem sit. Officia magna aliquip veniam excepteur consectetur irure labore ullamco enim.',
                    image: 'Performance'
                },
                {
                    title: 'Seo',
                    description: 'Magna consectetur exercitation anim proident laborum nostrud nisi cillum excepteur pariatur. Deserunt elit et esse consectetur proident adipisicing do eu ullamco consequat. Voluptate nisi consectetur do aute consectetur occaecat do voluptate culpa fugiat labore sint sunt sint do. Nulla sit nulla quis quis exercitation ex ut aliquip sint Lorem sit. Officia magna aliquip veniam excepteur consectetur irure labore ullamco enim.',
                    image: 'Seo'
                },
                {
                    title: 'Scalable',
                    description: 'Magna consectetur exercitation anim proident laborum nostrud nisi cillum excepteur pariatur. Deserunt elit et esse consectetur proident adipisicing do eu ullamco consequat. Voluptate nisi consectetur do aute consectetur occaecat do voluptate culpa fugiat labore sint sunt sint do. Nulla sit nulla quis quis exercitation ex ut aliquip sint Lorem sit. Officia magna aliquip veniam excepteur consectetur irure labore ullamco enim.',
                    image: 'Scalable'
                },
                {
                    title: 'Ui/UX',
                    description: 'Magna consectetur exercitation anim proident laborum nostrud nisi cillum excepteur pariatur. Deserunt elit et esse consectetur proident adipisicing do eu ullamco consequat. Voluptate nisi consectetur do aute consectetur occaecat do voluptate culpa fugiat labore sint sunt sint do. Nulla sit nulla quis quis exercitation ex ut aliquip sint Lorem sit. Officia magna aliquip veniam excepteur consectetur irure labore ullamco enim.',
                    image: 'UiUX'
                },
                {
                    title: 'Support',
                    description: 'Magna consectetur exercitation anim proident laborum nostrud nisi cillum excepteur pariatur. Deserunt elit et esse consectetur proident adipisicing do eu ullamco consequat. Voluptate nisi consectetur do aute consectetur occaecat do voluptate culpa fugiat labore sint sunt sint do. Nulla sit nulla quis quis exercitation ex ut aliquip sint Lorem sit. Officia magna aliquip veniam excepteur consectetur irure labore ullamco enim.',
                    image: 'Support'
                },
            ],

            titleLanguage:{
                title: 'development',
            },
            titleFrontend:{
                title: 'frontend development',
            },
            titleBackend:{
                title: 'backend development',
            },
            titleDatabase:{
                title: 'database',
            },
            titleDevops:{
                title: 'Devops',
            },
            optionsArray: [
                {
                    breakpoint: -1,
                    itemsPerSlide: 6,
                    itemsMargin: 15,
                    loop: true,
                    itemsPerStep: 4,
                    arrows: true,
                    dots: true,
                },
                {
                    breakpoint: 1440,
                    itemsPerSlide: 4,
                    itemsMargin: 10,
                    loop: true,
                    itemsPerStep: 2,
                    arrows: true,
                    dots: true,
                },
                {
                    breakpoint: 992,
                    itemsPerSlide: 3,
                    itemsMargin: 30,
                    loop: true,
                    itemsPerStep: 1,
                    arrows: true,
                    dots: true,
                },
                {
                    breakpoint: 768,
                    itemsPerSlide: 2,
                    itemsMargin: 15,
                    loop: true,
                    itemsPerStep: 1,
                    arrows: true,
                    dots: true,
                },
                {
                    breakpoint: 576,
                    itemsPerSlide: 2,
                    itemsMargin: 0,
                    loop: true,
                    itemsPerStep: 1,
                    arrows: false,
                    dots: true,
                }
            ],
            languages:[
                {
                    icon : 'javaScript', 
                    title: 'javaScript'
                },
                {
                    icon : 'typeScript', 
                    title: 'typeScript'
                },
                {
                    icon : 'PHP', 
                    title: 'PHP'
                },
                {
                    icon : 'Python', 
                    title: 'Python'
                },
            ],
            frontends:[
                {
                    icon : 'VUE', 
                    title: 'VUE'
                },
                {
                    icon : 'VUEX', 
                    title: 'VUEX'
                },
                {
                    icon : 'Nuxt', 
                    title: 'Nuxt'
                },
                {
                    icon : 'React', 
                    title: 'React'
                },
                {
                    icon : 'Next', 
                    title: 'Next'
                },
                {
                    icon : 'React-Native', 
                    title: 'React Native'
                },
                {
                    icon : 'Angular', 
                    title: 'Angular'
                },
                {
                    icon : 'Flutter', 
                    title: 'Flutter'
                },
            ],
            backends:[
                {
                    icon : 'Nodejs', 
                    title: 'Nodejs'
                },
                {
                    icon : 'Node-Express', 
                    title: 'Node + Express'
                },
                {
                    icon : 'Node-Koa', 
                    title: 'Node + Koa'
                },
                {
                    icon : 'Node-Nest', 
                    title: 'Node + Nest'
                },
                {
                    icon : 'PHP', 
                    title: 'PHP'
                },
                {
                    icon : 'PHP-Laravel', 
                    title: 'PHP + Laravel'
                },
            ],
            databases:[
                {
                    icon : 'Redis', 
                    title: 'Redis'
                },
                {
                    icon : 'MongoDB', 
                    title: 'MongoDB'
                },
                {
                    icon : 'MySQL', 
                    title: 'MySQL'
                },
                {
                    icon : 'MariaDB', 
                    title: 'MariaDB'
                },
                {
                    icon : 'PostgreSQL', 
                    title: 'PostgreSQL'
                },
            ],
            devopses:[
                {
                    icon : 'NginX', 
                    title: 'NginX'
                },
                {
                    icon : 'Apache', 
                    title: 'Apache'
                },
                {
                    icon : 'Kafka', 
                    title: 'Kafka'
                },
                {
                    icon : 'RabbitMQ', 
                    title: 'RabbitMQ'
                },
                {
                    icon : 'Docker', 
                    title: 'Docker'
                },
            ],
        }
    },
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/global.scss';

.services-section-container-wrapper{
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    


    @include mq(lg){
        flex-direction: row;
        flex-wrap: wrap;
    }

    &>div{
        margin-bottom: 50px;
        padding: 30px;

        @include mq(lg){
            padding: 50px;
            flex-basis: 47.5%;
        }    
    }
}

.information-box-wrapper{
    margin-top: 120px;
    margin-bottom: 70px;
    
    @include mq(lg){
        margin-top: 200px;
        margin-bottom: 150px;
    }
}

.advantage-section-wrapper{
    margin-top: 100px;

    @include mq(lg){
        margin-top: 150px;

        // &>div:nth-child(even){
        //     flex-direction: row-reverse;
        // }
    }
}

.cta{
    margin-top: 150px;
    margin-bottom: 150px;
}

// .carousel-items{
//     div{
//         margin-bottom: 70px;

//         @include mq(lg) {
//             margin-bottom: 100px;
//         }
//     }
// }

.carousel-items{
    margin-bottom: 200px;
}

</style>