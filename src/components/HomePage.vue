<template>
  <div class="">

    <Navbar />
    <!-- Hero Section -->
    <v-container class="pa-0" fluid>
      <!-- Hero Section with Background Image -->
      <v-sheet height="100vh" class="d-flex align-center" :style="heroStyles">

        <v-row justify="center" align="center" class="ma-0 w-100 text-center">
          <v-col cols="12" md="8" class="text-white px-4">
            <h2 class="text-h4 text-md-h2 font-weight-bold mb-4">
              Trusted electricians providing electrical services to Wellington
            </h2>
            <p class="text-body-1 text-md-h5 mb-6">
              At 24 Seven Electrical we can help with all your electrical needs including Renovations and Rewiring,
              lighting, heating, cooling and ventilation, security and access, home automation, & General Electrical
              maintenance.
            </p>
            <v-btn color="white" variant="outlined" class="text-white" @click="onContactClick">
              Contact Us
            </v-btn>
          </v-col>
        </v-row>
      </v-sheet>
    </v-container>

    <!-- Services Section -->
    <v-container fluid class="py-8 pb-16" style="background: hsl(217.14deg 43.75% 18.82%);">

      <v-row justify="center" align="center" class="ma-0 w-100 text-center">
        <v-col cols="12" md="8" class="text-white px-4">
          <h1 class="text-h4 text-md-h2 font-weight-bold mb-4">
            Our Services
          </h1>
          <p class="text-body-1 text-md-h5 mb-6">
            From new builds to renovations, feature lighting
            installations to
            sustainable energy
            solutions, we've got
            Wellington covered when it comes to all things electrical.
          </p>
          <p class="text-body-1 text-md-h5 mb-6">
            As your trusted electrician in Wellington, we pride
            ourselves on delivering
            excellence in
            every project we
            undertake. We understand the unique requirements of each customer and are always ready to listen and
            collaborate
            to bring your electrical vision to life.
          </p>

        </v-col>
      </v-row>
      <v-row class="pt-8">
        <v-col v-for="service in services" :key="service.title" cols="12" sm="6" md="3">
          <v-card outlined class="text-center pa-4">
            <v-icon size="48" color="primary">{{ service.icon }}</v-icon>
            <h4 class="my-4">{{ service.title }}</h4>
            <p>{{ service.description }}</p>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
    <v-container fluid class="py-10 bg-grey-lighten-4">
      <v-row justify="center" align="center" class="text-center">
        <v-col cols="6" sm="4" md="2" v-for="(image, index) in images" :key="index">
          <v-img :src="image" alt="Logo" contain max-width="200" class="mx-auto"></v-img>
        </v-col>
      </v-row>
    </v-container>

    <Reviews />
    <!-- Contact Section -->

    <v-container fluid class="py-8 px-16 gradient-background">

      <v-card title="Get in Touch" subtitle="Let’s chat about how we can help with your latest project."
        variant="outlined" class="form-card">
        <v-card-text>
          <v-row>
            <v-col cols="12" md="6">
              <v-text-field label="first Name" v-model="form.name" variant="outlined"></v-text-field>
            </v-col>
            <v-col cols="12" md="6">
              <v-text-field label="Last Name" v-model="form.name" variant="outlined"></v-text-field>
            </v-col>
            <v-col cols="12" md="6">
              <v-text-field label="Your Address" v-model="form.name" variant="outlined"></v-text-field>
            </v-col>
            <v-col cols="12" md="6">
              <v-text-field label="Your Email" v-model="form.email" variant="outlined"></v-text-field>
            </v-col>
            <v-col cols="12">
              <v-textarea label="Your Message" v-model="form.message" variant="outlined"></v-textarea>
            </v-col>
          </v-row>
        </v-card-text>
        <v-card-actions>
          <v-btn class="text-none ms-4 text-white" color="blue-darken-4" rounded="0" variant="flat"
            type="submit">Send</v-btn>
        </v-card-actions>
      </v-card>
    </v-container>

    <!-- Footer -->
    <v-footer color="primary" dark class="py-4">
      <v-container>
        <v-row justify="space-between">
          <v-col cols="auto">
            <p>&copy; 2024 24 Seven Electrical</p>
          </v-col>
          <v-col cols="auto">
            <v-btn icon>
              <v-icon>mdi-facebook</v-icon>
            </v-btn>
            <v-btn icon>
              <v-icon>mdi-linkedin</v-icon>
            </v-btn>
          </v-col>
        </v-row>
      </v-container>
    </v-footer>
  </div>
</template>

<script>
import Reviews from './Reviews.vue';
import Navbar from './Navbar.vue';

export default {
  components: { Reviews, Navbar },
  data() {
    return {
      drawer: false, // Controls the navigation drawer
      services: [
        { title: 'Electrical', icon: 'mdi-flash', description: 'All types of electrical work.' },
        { title: 'Heating & Cooling', icon: 'mdi-air-conditioner', description: 'Reliable HVAC solutions.' },
        { title: 'Wind & Power', icon: 'mdi-wind-turbine', description: 'Sustainable energy solutions.' },
        { title: 'Security & Access', icon: 'mdi-security', description: 'Secure your premises.' },
      ],
      form: { name: '', email: '', message: '' },
      heroStyles: {
        backgroundImage: "url('https://images.squarespace-cdn.com/content/v1/60b30597da4de55c53684bb7/596ba952-92b2-4820-8adc-bea02f052306/Asset+2.png?format=1000w')", // Replace with your image URL
        backgroundSize: "cover",
        backgroundPosition: "center",
        backgroundRepeat: "no-repeat",
        boxShadow: "0 3px 13px rgba(0, 0, 0, 0.5)",
      },
      images: [
        "https://images.squarespace-cdn.com/content/v1/60b30597da4de55c53684bb7/128ec99c-43b8-4a76-902f-577f09c3a14f/EWRB+LOGO.png?format=300w", // Replace with actual paths
        "https://images.squarespace-cdn.com/content/v1/60b30597da4de55c53684bb7/7d5025db-24a1-4672-8a9d-9e87487a48db/Master+Electricians.png?format=300w",
        "https://images.squarespace-cdn.com/content/v1/60b30597da4de55c53684bb7/7bfa4a62-91d0-451c-aa33-26948fb81128/Mastercraft+Electrical.png?format=300w",
        "https://images.squarespace-cdn.com/content/v1/60b30597da4de55c53684bb7/3b2f163b-c1e3-4af8-8a70-fa35d9a7801e/SiteSafe-logo.png?format=300w",
        "https://images.squarespace-cdn.com/content/v1/60b30597da4de55c53684bb7/8d195621-5892-4297-85a2-535210bc68d5/GWO-logo.png?format=300w",
      ],
      reviews: [
        {
          rating: 5,
          text: "Your guy went the extra mile to make sure that the job was perfect. It is a great impression for the company.",
        },
        {
          rating: 5,
          text: "Your guy has done a great job. He was solution focused, he even put in some bracing...",
        },
        {
          rating: 5,
          text: "Matt & his team were a great pleasure to work with. They have amazing attention to detail...",
        },
        {
          rating: 5,
          text: "Awesome service. Fast and reasonably priced. Will definitely be using again.",
        },
      ],
    };
  },
  methods: {
    toggleMenu() {
      this.drawer = !this.drawer;
    },
    navigateTo(section) {
      alert(`Navigating to ${section} section!`);
      this.drawer = false;
    },
    submitForm() {
      alert('Form submitted successfully!');
    },
  },
};
</script>

<style scoped>
.gradient-background {
  background: linear-gradient(135deg, #001f3f, #003366);
  color: white;
  min-height: 100vh;
}

.form-card {
  background-color: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.2);
  color: white;
}

.corner-image {
  position: absolute;
  bottom: 20px;
  right: 20px;
  z-index: -1;
  /* Ensures the image is behind the content */
  opacity: 0.3;
  /* Makes the image slightly transparent */
}

.v-sheet {
  position: relative;
}

.v-sheet::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  /* Adjust the opacity for the overlay */
  z-index: 1;
}

.v-row {
  position: relative;
  z-index: 2;
}

.text-center {
  text-align: center;
}

.bg-primary {
  background-color: #001f3f !important;
  /* Adjust your color as needed */
}

.white--text {
  color: white !important;
}
</style>
