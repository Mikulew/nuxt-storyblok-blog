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
  asyncData(context) {
    return context.app.$storyapi
      .get("cdn/stories", { version: "draft", starts_with: "blog/" })
      .then(res => {
        return {
          posts: res.data.stories.map(bp => {
            return {
              slug: bp.slug,
              title: bp.content.title,
              previewText: bp.content.summary,
              thumbnailUrl: bp.content.thumbnail
            };
          })
        };
      });
  },
  components: {
    PostPreview
  }
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
