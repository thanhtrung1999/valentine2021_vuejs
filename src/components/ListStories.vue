<template>
  <!-- eslint-disable vue/no-use-v-if-with-v-for,vue/no-confusing-v-for-v-if -->
  <div id="list-stories" :style="styleLastComponent()">
    <transition name="slide-fade">
      <StoryComponent
        v-for="(story, index) in listStories"
        :key="index"
        v-if="activeComponent === index"
        :story="story"
        :class="{ active: activeComponent === index }"
        class="story-component"
        :id="`story-component--${index}`"
      />
    </transition>
    <button class="btn-next" @click="nextComponent()"><i class="fas fa-angle-double-right"></i></button>
  </div>
</template>

<script>
import StoryComponent from "@/components/StoryComponent";
export default {
  name: "list-stories",
  props: {
    listStories: {
      type: Array,
      default() {
        return [];
      },
    },
  },
  data() {
    return {
      activeComponent: 0,
    };
  },
  created() {
    this.showComponentActived();
  },
  methods: {
    showComponentActived() {
      const setActiveComponent = setInterval(() => {
        ++this.activeComponent;
        if (this.activeComponent === this.listStories.length) {
          clearInterval(setActiveComponent);
          let listStoriesElement = document.getElementById("list-stories");
          listStoriesElement.classList.add("hidden");
        }
      }, 12000);
    },
    nextComponent() {
      this.activeComponent = this.activeComponent + 1;
      if (this.activeComponent === this.listStories.length) {
        this.activeComponent = 0;
      }
    },
    styleLastComponent() {
      let listStoriesElement = document.getElementById("list-stories");
      if (this.activeComponent === this.listStories.length - 1) {
        listStoriesElement.classList.add("--increase-height");
      }
    }
  },
  components: {
    StoryComponent,
  },
};
</script>

<style lang="scss" scoped>
// @for $i from 0 through 10 {
//   @if($i % 2 == 0) {
//     #story-component--#{$i} {
//       position: relative;
//     }
//   }
//   @else {
//     #story-component--#{$i} {
//       position: absolute;
//     }
//   }
// }
.--increase-height{
  height: 18rem!important;
}
.btn-next {
  position: absolute;
  z-index: 999;
  top: 0;
  right: 0;
  background-color: rgb(241, 28, 160);
  border: none;
  outline: none;
  font-size: 1.1rem;
  font-family: "Pacifico", cursive;
  border-top-right-radius: 1.5rem;
  padding-right: .7rem;
  color: #f1f1f1;
  transition: all .6s ease;
  cursor: pointer;
}
.slide-fade-enter-active {
  transition: all 3s ease-out;
  opacity: 1;
  animation: slideEnter 3s ease-out;
}
.slide-fade-leave-active {
  transition: all 2s ease-in-out;
  opacity: 0;
  animation: slideLeave 2s ease-in-out;
}
.slide-fade-leave {
  opacity: 1;
  transform: translateX(0);
}
@keyframes slideEnter {
  from {
    transform: translateX(-5rem);
  }
  to {
    transform: translateX(0);
  }
}
@keyframes slideLeave {
  from {
    transform: translateX(0);
  }
  to {
    transform: translateX(5rem);
  }
}
.hidden {
  animation: hiddenComponent 5s ease;
  transition: all 5s ease-in;
  opacity: 0;
}
@keyframes hiddenComponent {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
    visibility: hidden;
    transform: translate(50%);
  }
}
</style>