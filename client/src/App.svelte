<script>
  import { Router, Link, Route } from 'svelte-routing'
  import { onMount } from 'svelte'
  import PrivateRouteGuard from './components/PrivateRouteGuard.svelte';
  import Login from './components/Login.svelte'
  import Signup from './components/Signup.svelte'
  import Profile from './components/Profile.svelte'
  import About from './components/About.svelte'
  import FootballSummarizer from './components/FootballSummarizer.svelte'
  import ReversePrivateRouteGuard from './components/ReversePrivateRouteGuard.svelte';

  let isLoggedIn = false

  onMount(async () => {
    const response = await fetch('http://localhost:8080/auth/me', {
      credentials: 'include'
    })
    isLoggedIn = response.ok
  })
</script>

<Router> 
  <nav> 
    {#if !isLoggedIn}
      <Link to="/login">Login</Link> 
      <Link to="/signup">Sign up</Link> 
    {/if}

    {#if isLoggedIn}
      <Link to="/profile">Profile</Link> 
    {/if}

    <Link to="/about">About</Link>
    <Link to="/footballSummarizer">Football Summarizer</Link>
  </nav>


<Route path="/login"> <ReversePrivateRouteGuard> <Login/> </ReversePrivateRouteGuard></Route>
<Route path="/signup"> <ReversePrivateRouteGuard> <Signup/> </ReversePrivateRouteGuard></Route>

<Route path="/profile"> <PrivateRouteGuard> <Profile /> </PrivateRouteGuard></Route>

<Route path="/about"><About/> </Route>

<Route path="/footballSummarizer"> <PrivateRouteGuard> <FootballSummarizer/> </PrivateRouteGuard></Route>

</Router>