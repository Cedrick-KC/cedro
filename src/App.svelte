<script>
  import Sidebar from './Sidebar.svelte';
  import Projects from './Projects.svelte';
  import Contact from './Contact.svelte';
  
  // This prop will now control if the sidebar is fixed or fully scrollable.
  let isSidebarFixed = true;

  function toggleSidebar() {
    isSidebarFixed = !isSidebarFixed;
  }
</script>

<div class="portfolio-container" class:scrollable-sidebar={!isSidebarFixed}>
  <main class="main-content">
    <Projects />
    <Contact />
  </main>
  <aside class="sidebar">
    <Sidebar full={!isSidebarFixed} />
    <div class="sidebar-footer">
      <button on:click={toggleSidebar}>
        {isSidebarFixed ? 'View All Content' : 'Fix Sidebar'}
      </button>
    </div>
  </aside>
</div>

<style>
  :global(body) {
    margin: 0;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background-color: #0d1117;
    color: #e6edf3;
  }

  .portfolio-container {
    display: grid;
    grid-template-columns: 1fr;
    gap: 2rem;
    padding: 2rem;
    max-width: 1200px;
    margin: 0 auto;
  }

  @media (min-width: 768px) {
    .portfolio-container {
      grid-template-columns: 2fr 1fr;
    }
  }

  .main-content {
    background-color: #161b22;
    padding: 1.5rem;
    border-radius: 12px;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.5);
  }

  .sidebar {
    background-color: #161b22;
    padding: 1.5rem;
    border-radius: 12px;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.5);
    position: fixed;
    right: 2rem;
    top: 2rem;
    height: calc(100vh - 4rem);
    width: calc(33.33% - 2.5rem);
    overflow-y: auto;
    z-index: 10;
  }
  
  /* When the 'scrollable-sidebar' class is active, the sidebar behaves normally */
  .portfolio-container.scrollable-sidebar .sidebar {
    position: static;
    height: auto;
    width: auto;
    overflow-y: visible;
  }

  .sidebar-footer {
    padding-top: 1rem;
    border-top: 1px solid #333;
    margin-top: 1rem;
    text-align: center;
  }

  .sidebar-footer button {
    background-color: #58a6ff;
    color: white;
    border: none;
    padding: 0.75rem 1.5rem;
    border-radius: 8px;
    cursor: pointer;
    font-weight: bold;
  }
</style>