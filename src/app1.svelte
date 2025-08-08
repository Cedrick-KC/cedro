<script>
    import Profile from './components/Profile.svelte';
    import Skills from './components/Skills.svelte';
    import Contact from './components/Contact.svelte';
  
    let selected = 'profile'; // Default main view
  
    const handleSelect = (component) => {
      selected = component;
    };
  </script>
  
  <div class="main-content">
    {#if selected === 'profile'}
      <Profile full={true} />
    {:else if selected === 'skills'}
      <Skills full={true} />
    {:else if selected === 'contact'}
      <Contact full={true} />
    {/if}
  </div>
  
  <div class="sidebar">
    <div on:click={() => handleSelect('profile')}>
      <Profile full={false} />
    </div>
  
    <div on:click={() => handleSelect('skills')}>
      <Skills full={false} />
    </div>
  
    <div on:click={() => handleSelect('contact')}>
      <Contact full={false} />
    </div>
  </div>
  
  <style>
    @import './app.css';
  
    .sidebar div {
      cursor: pointer;
      border: 1px solid #333;
      border-radius: 8px;
      padding: 10px;
      background: #1a1a1a;
      transition: background 0.2s;
    }
  
    .sidebar div:hover {
      background: #696666;
    }
  </style>
  