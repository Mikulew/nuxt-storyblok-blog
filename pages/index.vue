<template>
  <section id="posts">
    <PostPreview
      v-for="post in posts"
      :key="post.id"
      :title="post.title"
      :content="post.previewText"
      :thumbnailImage="post.thumbnailUrl"
      :slug="post.slug"
    />
  </section>
</template>

<script>
import PostPreview from "@/components/Blog/PostPreview";

export default {
  data() {
    return {
      posts: [
        {
          id: 1,
          title: "A new beginning",
          previewText: "This will be awesome, don't miss it!",
          thumbnailUrl: "https://via.placeholder.com/150",
          slug: "a-new-beginning",
        },
        {
          id: 2,
          title: "Vue.js developer returns",
          previewText: "From Vue.js to React.js and back!",
          thumbnailUrl: "https://via.placeholder.com/150",
          slug: "vue-js-developer-returns",
        },
      ],
    };
  },
  components: {
    PostPreview,
  },
};
</script>

<style>
#posts {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  padding: 2rem 0 0 0;
}

@media (min-width: 900px) {
  #posts {
    flex-direction: row;
  }
}
</style>
