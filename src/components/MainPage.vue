<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },

  data: () => ({
    users: ["1M", "2D", "3D", "4F", "5D", "6D", "7F"],
    menuButtons: ["mdi-home", "mdi-magnify", "mdi-plus", "mdi-heart", "mdi-cog"],
  }),
};
</script>

<template>
  <div>
    <div class="users-story d-flex">
      <div class="add-story">
        <v-avatar color="primary" size="54" class="mr-4 add-story__inner"> CM</v-avatar>
        <v-btn
            fab
            x-small
            width="18"
            height="18"
            text
            dark
            smal
            class="primary add-story__button"
            color="white"
        >
          <v-icon x-small>
            mdi-plus
          </v-icon>
        </v-btn>
      </div>
      <v-avatar
        color="primary"
        size="54"
        class="mr-4"
        v-for="(item) in 10"
        :key="item"
      >
        <img src="https://picsum.photos/200" alt="">
      </v-avatar>
    </div>

    <div class="post-container pb-10">
      <v-card elevation="0" class="mb-4" v-for="item in 5" :key="item">
        <v-card-title>
          <v-avatar color="primary" size="36" class="mr-4">
            <img src="https://cdn.vuetifyjs.com/images/john.jpg" alt="John" />
          </v-avatar>
          <div>Crihan Mihai</div>
        </v-card-title>
        <v-card-text>
          <iframe
            width="100%"
            height="400px"
            src="https://www.youtube.com/embed/w9okGAKOyYk"
            title="YouTube video player"
            frameborder="0"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
            allowfullscreen
          ></iframe>
        </v-card-text>
        <v-card-actions>
          <v-btn fab text dark small color="pink">
            <v-icon dark> mdi-heart </v-icon>
          </v-btn>
          <v-btn fab text dark small color="pink">
            <v-icon dark> mdi-share </v-icon>
          </v-btn>
          <v-spacer></v-spacer>
          <v-btn fab text dark small color="black">
            <v-icon dark> mdi-plus </v-icon>
          </v-btn>
        </v-card-actions>
        <div class="px-4 pb-5">1032 Отметок нравится</div>
      </v-card>
    </div>

    <div class="bottom-menu d-flex justify-space-around align-center">
      <v-btn
        fab
        text
        dark
        small
        color="black"
        v-for="(item, index) in menuButtons"
        :key="index"
      >
        <v-icon dark>
          {{ item }}
        </v-icon>
      </v-btn>
    </div>
  </div>
</template>

<style scoped lang="scss">
* {
  ::-webkit-scrollbar {
    width: 0;
    height: 0;
  }
}

.add-story {
  position: relative;

  .v-avatar:after {
    display: none;
  }

  &__inner {}
  &__button {
    position: absolute;
    right: 12px;
    bottom: 0;

    &::v-deep .v-btn__content {
      border: 1px solid lightgray;
      border-radius: 100%;
    }
  }
}

.users-story {
  padding: 16px;
  overflow-x: scroll;
  border-bottom: 1px solid lightgray;

  .user {
    margin-right: 12px;
  }

  .v-avatar {
    position: relative;
    overflow: visible;

    &:after {
      position: absolute;
      top: -4px;
      left: -4px;
      width: 62px;
      height: 62px;
      content: " ";
      border: 2px solid pink;
      border-radius: 100%;
    }
  }
}

.bottom-menu {
  position: fixed;
  height: 48px;
  bottom: 0;
  left: 0;
  right: 0;
  z-index: 9;
  border-top: 1px solid lightgray;
  background: white;
  width: 100%;
}
</style>
