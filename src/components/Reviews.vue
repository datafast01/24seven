<template>
    <v-container class="slider-section bg-white" fluid>
        <!-- Section Title -->
        <h2 class="text-center mb-6">Client Feedback</h2>

        <!-- Slider Container -->
        <v-row justify="center bg-white">
            <v-col cols="12" md="10" sm="12">
                <v-sheet class="slider-container bg-white" rounded>
                    <div class="slider-content">
                        <!-- Review Cards -->
                        <v-card v-for="(review, index) in reviews" :key="index" class="review-card bg-white"
                            variant="outlined" elevation="2">
                            <div class="flex-profile mb-4">
                                <v-avatar size="55">
                                    <v-img :src="review.profileImage" alt="Profile Image" />
                                </v-avatar>

                                <div class="heading-image">
                                    <div class="heading">
                                        <h3 class="name-cus">{{ review.name }}</h3>
                                    </div>
                                    <v-rating :model-value="4.5" color="amber" density="compact" size="small"
                                        half-increments readonly></v-rating>
                                </div>
                            </div>

                            <p class="prop">
                                {{ review.comment }}
                            </p>
                        </v-card>
                    </div>
                </v-sheet>

                <!-- Navigation Buttons -->

            </v-col>
        </v-row>
    </v-container>
</template>

<script>
export default {
    data() {
        return {
            currentIndex: 0,
            cardWidth: 300, // Adjust card width + margin
            reviews: [
                {
                    name: "Justin Raj",
                    profileImage:
                        "https://cdn.pixabay.com/photo/2020/07/01/12/58/icon-5359553_1280.png",
                    ratingImage:
                        "https://static.vecteezy.com/system/resources/thumbnails/009/663/927/small/5-star-rating-review-star-transparent-free-png.png",
                    comment:
                        "Dorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc vulputate libero et velit interdum.",
                },
                {
                    name: "Antony",
                    profileImage:
                        "https://cdn.pixabay.com/photo/2020/07/01/12/58/icon-5359553_1280.png",
                    ratingImage:
                        "https://static.vecteezy.com/system/resources/thumbnails/009/663/927/small/5-star-rating-review-star-transparent-free-png.png",
                    comment:
                        "Curabitur tempus urna at turpis condimentum lobortis. Dorem ipsum dolor sit amet.",
                },
                {
                    name: "Surendar",
                    profileImage:
                        "https://cdn.pixabay.com/photo/2020/07/01/12/58/icon-5359553_1280.png",
                    ratingImage:
                        "https://static.vecteezy.com/system/resources/thumbnails/009/663/927/small/5-star-rating-review-star-transparent-free-png.png",
                    comment:
                        "Class aptent taciti sociosqu ad litora torquent per conubia nostra.",
                },
                {
                    name: "Surendar",
                    profileImage:
                        "https://cdn.pixabay.com/photo/2020/07/01/12/58/icon-5359553_1280.png",
                    ratingImage:
                        "https://static.vecteezy.com/system/resources/thumbnails/009/663/927/small/5-star-rating-review-star-transparent-free-png.png",
                    comment:
                        "Class aptent taciti sociosqu ad litora torquent per conubia nostra.",
                },
                // Add more reviews here
            ],
        };
    },


};
</script>

<style scoped>
.slider-section {
    font-family: Arial, sans-serif;
    background-color: #f8f9fa;
    padding: 40px 0;
}

.slider-container {
    overflow: hidden;
    border-radius: 8px;
    position: relative;
    height: 350px;
}

.slider-content {
    display: flex;
    transition: transform 0.5s ease-in-out;
}

.review-card {
    width: 280px;
    min-width: 280px;
    height: 320px;
    margin-right: 20px;
    padding: 20px;
    box-sizing: border-box;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}

.heading .name-cus {
    font-size: 16px;
    font-weight: 500;
    margin-bottom: 5px;
}

.prop {
    font-size: 14px;
    color: #666;
    line-height: 1.6;
}

.flex-profile {
    display: flex;
    gap: 15px;
    align-items: center;
}

.prev,
.next {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    z-index: 1;
    font-size: 24px;
}

.prev {
    left: 10px;
}

.next {
    right: 10px;
}
</style>
