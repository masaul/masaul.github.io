<template>
    <div class="work view-page">
        <div class="text">
            <h1 class="title">
                <div class="outline-text">Projects</div>
                <span class="hov">M</span>
                <span class="hov">y</span>
                <span class="space"></span>
                <span class="hov">p</span>
                <span class="hov">r</span>
                <span class="hov">o</span>
                <span class="hov">j</span>
                <span class="hov">e</span>
                <span class="hov">c</span>
                <span class="hov">t</span>
                <span class="hov">s</span>
            </h1>
        </div>

        <div class="work-list">
            <div class="work" v-for="(work, index) in myProjects" :key="index">
                <div class="information">
                    <h2 class="work-number">0{{ index + 1 }}.</h2>
                    <h1 class="work-title">
                        {{ work.title }}
                    </h1>
                    <img
                        :src="require(`@/assets/${work.img}`)"
                        alt=""
                        class="mobile-img"
                    />
                    <p class="description">
                        {{ work.description }}
                    </p>
                    <div class="tools">
                        <p>
                            Code Tools:
                            <span>{{ work.codeTools.join(", ") }}</span>
                        </p>
                        <p class="design">
                            Design: <span>{{ work.design }}</span>
                        </p>
                    </div>
                    <div class="links">
                        <a
                            target="_blank"
                            class="btn"
                            :href="work.link"
                            :class="work.link === '' ? 'disabled' : ''"
                            >Visit</a
                        >
                        <a
                            target="_blank"
                            class="btn"
                            :href="work.source"
                            :class="work.source === '' ? 'disabled' : ''"
                            >Source Code</a
                        >
                    </div>
                </div>
                <div class="img">
                    <img :src="require(`@/assets/${work.img}`)" alt="" />
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            isExpand: false,
            icon: "fas fa-expand",
            isDetail: false,
            myProjects: [
                {
                    title: "Portofolio Simple",
                    description:
                        "Build a simple portfolio that describes myself",
                    source: "https://github.com/masaul/my-portofolio",
                    link: "https://masaul.github.io/my-portofolio/masaul.html",
                    img: "portme.png",
                    codeTools: [
                        "HTML",
                        "CSS",
                        "Javascript",
                        "Bootstrap 5",
                    ],
                    design: "Design by WPU",
                },
            ],
        };
    },
    mounted() {},
    methods: {},
};
</script>

<style scoped src="../styles/work.css"></style>
