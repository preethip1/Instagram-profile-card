<script>
  export let followers = 0;
  export let following = 0;
  export let posts = 0;
  let addPost = () => {
    posts = posts + 1;
  };
  let deletePost = () => {
    posts = posts - 1;
  };

  let addFollowing = () => {
    following = following + 1;
  };
  let deleteFollowing = () => {
    following = following - 1;
  };

  let addFollowers = () => {
    followers = followers + 1;
  };
  let deleteFollowers = () => {
    followers = followers - 1;
  };
</script>

<style>
  .wrapper {
    display: flex;
    flex: column;
    margin: 2%;
  }
  .followers {
    margin: 2%;
  }
  .following {
    margin: 2%;
  }
  .posts {
    margin: 2%;
  }
  .postWrap {
    display: flex;
    flex-direction: column;
    flex-grow: 1;
  }
  .butt {
    display: flex;
    flex-direction: row-reverse;
    flex-grow: 1;
  }
</style>

<div class="wrapper">
  <div class="postWrap">
    <span class="followers">followers {followers}</span>
    <div class="butt">
      <button on:click={addFollowers} class="btn btn-success">+</button>
      {#if followers > 0}
        <button on:click={deleteFollowers} class="btn btn-danger">-</button>
      {:else}
        <button on:click={deleteFollowers} class="btn btn-danger" disabled>
          -
        </button>
      {/if}
    </div>
  </div>

  <div class="postWrap">
    <span class="following">following {following}</span>
    <div class="butt">
      <button on:click={addFollowing} class="btn btn-success">+</button>
      {#if following > 0}
        <button on:click={deleteFollowing} class="btn btn-danger">-</button>
      {:else}
        <button on:click={deleteFollowing} class="btn btn-danger" disabled>
          -
        </button>
      {/if}
    </div>
  </div>

  <div class="postWrap">
    <span class="posts">post-count {posts}</span>
    <div class="butt">
      <button on:click={addPost} class="btn btn-success">+</button>
      {#if posts > 0}
        <button on:click={deletePost} class="btn btn-danger">-</button>
      {:else}
        <button on:click={deletePost} class="btn btn-danger" disabled>-</button>
      {/if}
    </div>

  </div>
</div>
