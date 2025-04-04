<script>
  import { onMount } from "svelte";
  import { auth, db, collection, getDocs } from "../lib/firebase.js";

  let user = null;
  let datos = [];

  onMount(async () => {
    try {
      const userCredential = await auth.currentUser;
      if (userCredential) {
        user = userCredential;
        const querySnapshot = await getDocs(collection(db, "tuColección"));
        datos = querySnapshot.docs.map((doc) => doc.data());
      }
    } catch (error) {
      console.error("Error fetching data: ", error);
    }
  });
</script>

<h1>Dashboard</h1>
{#if user}
  <p>Bienvenido {user.email}</p>
{:else}
  <p>No estás autenticado</p>
{/if}

<ul>
  {#each datos as dato}
    <li>{dato.nombre}</li>
  {/each}
</ul>
