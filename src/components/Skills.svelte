<script>
    export let full = false;
  </script>
  
  <div class="skills-card">
    <h2>Skills</h2>
    <ul>
      <li>
        JavaScript
        <img src="https://raw.githubusercontent.com/Atcs-645/VISIT-MUSANZE/main/js.png" alt="JavaScript" class:full />
      </li>
      <li>
        Svelte
        <img src="https://raw.githubusercontent.com/Atcs-645/VISIT-MUSANZE/main/svelte.png" alt="Svelte" class:full />
      </li>
      {#if full}
        <li>
          Node.js
          <img src="https://raw.githubusercontent.com/Atcs-645/VISIT-MUSANZE/main/node.png" alt="Node.js" class:full />
        </li>
        <li>
          GraphQL
        </li>
        <li>
          PostgreSQL
          <img src="https://raw.githubusercontent.com/Atcs-645/VISIT-MUSANZE/main/postgresql.png" alt="PostgreSQL" class:full />
        </li>
      {/if}
    </ul>
  </div>
  
  <style>
  
    img {
      height: 30px; /* Set a consistent height for a clean look */
      width: auto;
      border-radius: 5px;
      transition: height 0.3s ease;
    }
  
    img.full {
      height: 30px; /* Larger size when 'full' is true */
    }
  </style>