<template>
    <Head title="Beranda" />
    <AppLayout>
        <section class="bg-body-tertiary">
            <div class="container-fluid col-12 px-4 py-5">
                <div
                    class="row flex-lg-row-reverse align-items-center g-5 py-5"
                >
                    <div class="col-10 col-sm-8 col-lg-6">
                        <img
                            src="/assets/img/heroes.png"
                            class="d-block mx-lg-auto img-fluid"
                            alt="Bootstrap Themes"
                            width="700"
                            height="500"
                            loading="lazy"
                        />
                    </div>
                    <div class="col-lg-6">
                        <h1
                            class="display-5 fw-bold text-body-emphasis lh-1 mb-3"
                        >
                            Belajar dengan mengikuti kursus premium
                        </h1>
                        <p class="lead">
                            Kuasai ilmu mendalam seperti Laravel, MySQL,
                            JavaScript, VueJS dan lainnya untuk menjadi
                            programmer yang handal
                        </p>
                        <div
                            class="d-grid gap-2 d-md-flex justify-content-md-start"
                        >
                            <a
                                href="#"
                                class="btn btn-primary btn-lg px-4 me-md-2"
                            >
                                Temukan Kursus
                            </a>
                            <a
                                href="#"
                                class="btn btn-outline-secondary btn-lg px-4"
                            >
                                Baca Artikel
                            </a>
                        </div>
                    </div>
                </div>
            </div>
            <div class="album py-5 bg-body-tertiary">
                <div class="container">
                    <h2 class="mb-5">
                        <i class="bi bi-journal-richtext"></i>Kursus Terbaru
                    </h2>
                    <div class="row row-cols-1 row-cols-sm-2 row-cols-md-3 g-3">
                        <div
                            class="col"
                            v-for="(course, index) in courses"
                            :key="index"
                        >
                            <div class="card shadow-md">
                                <img
                                    :src="'images/courses/' + course.thumbnail"
                                    class="card-img-top"
                                    :alt="course.name"
                                />
                                <div class="card-body">
                                    <h5 class="card-title">
                                        {{ course.name }}
                                    </h5>
                                    <div
                                        class="card-text"
                                        v-html="course.description"
                                    ></div>
                                    <div
                                        class="d-flex justify-content-between align-items-center"
                                    >
                                        <div class="btn-group">
                                            <a
                                                :href="'/buy/' + course.id"
                                                type="button"
                                                class="btn btn-sm btn-outline-primary"
                                            >
                                                Beli Sekarang
                                            </a>
                                        </div>
                                        <p class="text-black">
                                            {{ formatRupiah(course.price) }}
                                        </p>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <section class="">
                <div class="container my-5">
                    <div class="p-5 text-center bg-body-tertiary rounded-3">
                        <svg
                            class="bi mt-4 mb-3"
                            style="color: var(--bs-indigo)"
                            width="100"
                            height="100"
                        >
                            <use xlink:href="#bootstrap"></use>
                        </svg>
                        <h1 class="text-body-emphasis">
                            Pelajari materi paling <i>update</i>
                        </h1>
                        <p class="col-lg-8 mx-auto fs-5 text-muted">
                            Kuasai ilmu mendalam seperti Laravel, MySQL,
                            JavaScript, VueJS dan lain-lain untuk menjadi
                            programmer yang handal
                        </p>
                        <div class="d-inline-flex gap-2 mb-5">
                            <button
                                class="d-inline-flex align-items-center btn btn-primary btn-lg px-4 rounded-pill"
                                type="button"
                            >
                                Belajar sekarang
                            </button>
                        </div>
                    </div>
                </div>
            </section>
        </section>
    </AppLayout>
</template>

<script>
import AppLayout from "../Layouts/AppLayout.vue";
import { Head, Link } from "@inertiajs/vue3";

export default {
    layout: AppLayout,
    components: {
        Head,
        Link,
    },
    props: {
        courses: Object,
    },
};
</script>
