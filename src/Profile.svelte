<script>
  import Name from "./Name.svelte";
  import Username from "./Username.svelte";
  import Count from "./Count.svelte";
  import Bio from "./Bio.svelte";
  export let username;
  export let name;
  export let bio;
  export let followers;
  export let following;
  export let posts;
  export let src;
</script>

<style>
  .outer {
    display: flex;
    flex-direction: column;
    margin: 2%;
    padding: 2%;
  }
  .un {
    display: flex;
    flex-grow: 1;
    align-items: flex-start;
    justify-content: flex-start;
    font-size: 25px;
    margin: auto;
	padding: 1%;
  }
  .cc {
    flex-grow: 3;
    display: flex;
    flex-direction: row;
    margin: 5%;
    padding: 5%;
  }
  .im {
    flex-grow: 1;
    border-radius: 50%;
  }
  .cf {
    flex-grow: 3;
  }
  .bio {
	  margin: 5%;
	  flex-grow: 3;
	  padding: 5%;
  }
  .n {
    display: flex;
    flex-grow: 1;
    margin: auto;
  }
  img {
    border-radius: 50%;
  }
</style>

<div class=" outer">
  <div class="un">
    <Username class="un" {username} />
  </div>
  <div class="n">
    <Name {name} />
  </div>

  <div class="cc">
    <div class="im">
      <img {src} alt={'A picture of Jacqueline'} />
    </div>
    <div class = "">
      <div class="cf">
        <Count {followers} {following} {posts} />
      </div>
      <div class="bio">
        <Bio {bio} />
      </div>
    </div>
  </div>
</div>
