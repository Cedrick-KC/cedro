<script>
    export let full = false;
  </script>
  
  <div>
    <h2>Contact</h2>
    <p>Email: cedrique.dev@example.com</p>
    {#if full}
      <p>LinkedIn: /cedrique-dev</p>
      <p>GitHub: @cedrique</p>
    {/if}
  </div>
  