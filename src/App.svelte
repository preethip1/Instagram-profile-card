<script>
  import Greeting from "./Greeting.svelte";
  import Profile from "./Profile.svelte";
  import Bio from "./Bio.svelte";
  import Count from "./Count.svelte";
  import axios from "axios";
  import { onMount } from "svelte";

  console.log("line 9");
  let users = [];
  //axios.defaults.headers.post["Content-Type"] =
  //"application/x-www-form-urlencoded";
  let x = axios.get("http://localhost:8000/insta");
  console.log(x);
  x.then((res, error) => {
    if (!error) {
      console.log(res.data.users);
      users = res.data.users;
    }
  });
  //onMount(() => {
  //console.log("component mounted");
  //});
</script>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

<main>

  <Greeting />
  <!--<Profile {...users[0]} /> -->
  {#each users as user}
    <Profile {...user} />
  {/each}
</main>
