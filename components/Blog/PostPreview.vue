<template>
  <nuxt-link :to="slug">
    <article class="post-preview">
      <div class="post-preview-thumbnail" :style="{backgroundImage: `url(${thumbnailImage})`}"></div>
      <div class="post-preview-content">
        <h2>{{ title }}</h2>
        <p>{{ content }}</p>
      </div>
    </article>
  </nuxt-link>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true,
    },
    content: {
      type: String,
      requried: true,
    },
    thumbnailImage: {
      type: String,
      required: true,
    },
    slug: {
      type: String,
      required: true,
    },
  },
};
</script>

<style scoped>
a {
  text-decoration: none;
  color: black;
}

.post-preview {
  width: 90%;
  height: 20rem;
  margin: 1rem;
  border-radius: 3px;
  box-shadow: 1px 1px 5px 1px rgba(0, 0, 0, 0.5);
}

.post-preview-thumbnail {
  background-position: center;
  background-size: cover;
  width: 100%;
  height: 10rem;
}

.post-preview-content {
  text-align: center;
  padding: 1rem;
}

@media (min-width: 900px) {
  .post-preview {
    width: 25rem;
    margin: 1rem;
  }
}
</style>
