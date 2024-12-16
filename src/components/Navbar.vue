<template>
    <div>
        <v-app-bar color="primary" dark app>
            <!-- Logo -->
            <v-app-bar-title>
                <img src="https://images.squarespace-cdn.com/content/v1/60b30597da4de55c53684bb7/1622970003915-9LPWQ99QB6MT7JK6UTDQ/logo.png?format=1500w"
                    style="
  
    max-height: 75px;" /></v-app-bar-title>

            <!-- Desktop Links -->
            <v-spacer></v-spacer>
            <v-btn text class="hidden-sm-and-down">About</v-btn>
            <v-btn text class="hidden-sm-and-down">What we do</v-btn>
            <v-btn text class="hidden-sm-and-down">Contact</v-btn>

            <!-- Hamburger Menu for Mobile/Tablet -->
            <v-app-bar-nav-icon @click="toggleMenu" class="hidden-md-and-up"></v-app-bar-nav-icon>
        </v-app-bar>

        <!-- Navigation Drawer -->
        <v-navigation-drawer v-model="drawer" temporary right>
            <v-list>
                <v-list-item @click="navigateTo('About')">About</v-list-item>
                <v-list-item @click="navigateTo('What we do')">What we do</v-list-item>
                <v-list-item @click="navigateTo('Contact')">Contact</v-list-item>
            </v-list>
        </v-navigation-drawer>
    </div>

</template>

<script>
export default {

}
</script>

<style></style>