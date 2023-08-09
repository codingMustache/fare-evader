<script>
  import { onMount } from "svelte";
  $: time = new Date();
  $: popup = false;
  let today = new Date();
  today.setHours(today.getHours() + 3);
  const showPopup = () => (popup ? (popup = false) : (popup = true));
  onMount(() => setInterval(() => (time = new Date()), 1000));
</script>

<div id="main">
  <h1>Fare Evader</h1>
  <button on:click={showPopup}>Ticket</button>
</div>
<dialog open={popup}>
  <div>
    <h1>RTA</h1>
    <p>Show operator your ticket</p>
  </div>
  <button on:click={showPopup}>x</button>
  <div id="outerCricle" class="circle">
    <div id="innerCricle" class="circle">
      <img src="logo.jpeg" alt="logo" width="75px" />
    </div>
  </div>
  <h1 id="time">{time.toLocaleTimeString("en-US")}</h1>
  <div id="card">
    <h1>Adult Single Ride, Bus & <br /> Streetcar</h1>
    <p>New Orleans, LA</p>
    <h2>
      Expires {today.toLocaleDateString("en-US", {
        month: "short",
        day: "numeric",
        year: "numeric",
      })} at {today.toLocaleTimeString("en-US", {
        hour: "numeric",
        minute: "numeric",
      })}
    </h2>
  </div>
</dialog>

<style>
  #main {
    display: flex;
    height: 90%;
    flex-direction: column;
    align-items: center;
    justify-content: space-evenly;
    padding: 10px;
  }
  h1 {
    font-family: "Franklin Gothic Medium", "Arial Narrow", Arial, sans-serif;
    font-size: xx-large;
  }
  #main button {
    border-radius: 20px;
    border-style: none;
    background-color: rgb(104, 104, 254);
    height: 80px;
    color: white;
    width: 50%;
    box-shadow: 0 0 30px rgb(79, 79, 233);
    font-size: larger;
  }
  dialog {
    position: fixed;
    width: 95%;
    height: 100%;
    top: 0px;
    border: unset;
    margin: 0px;
    padding: 10px;
  }
  dialog button {
    border-radius: 50%;
    -moz-border-radius: 50%;
    -webkit-border-radius: 50%;
    border-style: unset;
    background-color: white;
    color: rgb(87, 86, 86);
    box-shadow: 0px 3px 10px rgba(0, 0, 0, 0.384);
    font-family: "Varela Round", sans-serif;
    font-size: 20pt;
    height: 40px;
    width: 40px;
    position: fixed;
    top: 20px;
    right: 18px;
    padding: 0px;
  }
  dialog h1 {
    font-size: 1.8rem;
    margin-top: 64px;
    margin-left: 13px;
    font-family: arial;
    font-weight: 550;
  }
  dialog p {
    font-family: Arial, Helvetica, sans-serif;
    margin: 4px 0px 0px 15px;
    font-size: 1.1rem;
    letter-spacing: 0.01em;
  }
  .circle {
    background-image: url("logo.jpg");
    height: 120px;
    width: 120px;
    margin: 90px auto;
    border-radius: 100%;
  }
  #outerCricle {
    animation: outerShadow 3s ease-in-out 0s infinite;
  }
  #innerCricle {
    animation: innerShadow 3s ease-in-out 0s infinite;
  }

  .circle img {
    display: flex;
    margin: auto;
    padding-top: 45px;
  }
  #time {
    margin-top: 103px;
    display: flex;
    justify-content: center;
    color: #3d4146;
    font-size: 4rem;
    margin-left: -1px;
    letter-spacing: -0.02em;
  }
  #card h1 {
    margin-top: 11px;
    margin-left: 15px;
    font-weight: 100;
    letter-spacing: -0.03em;
  }
  #card {
    padding: 5px;
    margin: auto;
    margin-top: 16px;
    border-radius: 3px;
    width: 90%;
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.649);
    min-height: 171px;
    max-width: 345px;
  }
  #card p {
    color: rgb(110, 109, 109);
    margin-top: 9px;
    margin-left: 15px;
    font-size: medium;
    letter-spacing: -0.05em;
  }
  #card h2 {
    margin-top: 40px;
    margin-left: 15px;
    font-family: Arial, Helvetica, sans-serif;
    letter-spacing: 0.6px;
    font-size: 1.1rem;
    color: #8a8a90;
  }

  @keyframes outerShadow {
    0% {
      box-shadow: 0 0 0 10px rgb(255, 176, 28);
    }
    20% {
      box-shadow: 0 0 0 30px rgb(255, 176, 28);
    }
    40% {
      box-shadow: 0 0 0 10px rgb(255, 176, 28);
    }
    60% {
      box-shadow: 0 0 0 40px rgb(255, 176, 28);
    }
    80% {
      box-shadow: 0 0 0 10px rgb(255, 176, 28);
    }
    100% {
      box-shadow: 0 0 0 10px rgb(255, 176, 28);
    }
  }
  @keyframes innerShadow {
    0% {
      box-shadow: 0 0 0 10px rgba(0, 0, 0, 0.451);
    }
    20% {
      box-shadow: 0 0 0 3px rgba(0, 0, 0, 0.451);
    }
    40% {
      box-shadow: 0 0 0 15px rgba(0, 0, 0, 0.451);
    }
    60% {
      box-shadow: 0 0 0 0px rgba(0, 0, 0, 0.451);
    }
    80% {
      box-shadow: 0 0 0 25px rgba(0, 0, 0, 0.451);
    }
    100% {
      box-shadow: 0 0 0 0px rgba(0, 0, 0, 0.451);
    }
  }
</style>
