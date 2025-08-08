<script>
  export let full = false;
</script>

<div>
  <h2>Profile</h2>
  <img src="https://raw.githubusercontent.com/Atcs-645/VISIT-MUSANZE/main/cedrique.png" alt="Cedrique" style="width: {full ? '200px' : '80px'}; border-radius: 10px;" />

  <p><strong>Name:</strong> Cedrique</p>
  {#if full}
  <div id="intro">
   <p id="par">Am a young Software engineer <br>Driven by coding where I began the  Coding journey at 14 years old and <br>for now I have been called out for numerous projects <br>feeling engaged lets reach out. </p>
   </div>
    <p><strong>Role:</strong> Software Engineer</p>
    <p><strong>Experience:</strong> 2+ years</p>
    <p><strong>Location:</strong> Remote / Global</p>
  {/if}
</div>
<style>
  #intro{
    background-color: rgba(95, 158, 160, 0.23);
    color: gainsboro; 
  }
#par{
  position:absolute; left: 35%; bottom: 100%; top: 20%;
  width: 270px;
  height: auto;
}
</style>