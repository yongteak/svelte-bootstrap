<script lang="ts">
    import { onMount } from 'svelte';
    import type { Post } from '$lib/type';
    import { fetchPosts } from '$lib/api';
  
    let posts: Post[] = [];
  
    onMount(async () => {
      posts = await fetchPosts();
    });
  </script>
  
  <div class="space-y-4">
    {#each posts as post (post.id)}
      <div class="flex items-center space-x-3">
        <div class="text-gray-600">{post.points}</div>
        <button class="text-gray-500 hover:text-gray-700">
          <!-- 여기에 upvote 아이콘을 넣을 수 있습니다. -->
          ▲
        </button>
        <div>
          <a href={post.url} class="text-blue-600 hover:underline">{post.title}</a>
          <div class="text-sm text-gray-500">
            {post.points} points by {post.author} | <a href={post.commentsUrl} class="hover:underline">comments</a>
          </div>
        </div>
      </div>
    {/each}
  </div>