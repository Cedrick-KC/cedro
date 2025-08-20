<script>
  import Sidebar from './Sidebar.svelte';
  import Projects from './Projects.svelte';
  import Contact from './Contact.svelte';

  // Pinned = sticky on desktop, Free = fully scrollable
  let isPinned = true;
  const toggleSidebar = () => (isPinned = !isPinned);
</script>

<div class="portfolio-container" class:pinned={isPinned} class:free={!isPinned}>
  <main class="main-content">
    <Projects />
    <Contact />
  </main>

  <aside class="sidebar">
    <Sidebar full={!isPinned} />

    <div class="sidebar-footer">
      <button on:click={toggleSidebar}>
        {isPinned ? 'View All Content' : 'Pin Sidebar'}
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

  /* GRID: main + sidebar (no overlap) */
  .portfolio-container {
    display: grid;
    grid-template-columns: minmax(0, 1fr); /* mobile: single column */
    gap: 2rem;
    padding: 2rem;
    max-width: 1200px;
    margin: 0 auto;
  }

  @media (min-width: 768px) {
    /* desktop: sidebar column width stays fixed, main grows */
    .portfolio-container {
      grid-template-columns: minmax(0, 1fr) 320px;
      align-items: start;
    }
  }

  .main-content {
    background: #161b22;
    padding: 1.5rem;
    border-radius: 12px;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.5);
    min-width: 0; /* prevents overflow in grid */
  }

  .sidebar {
    background: #161b22;
    padding: 1.5rem;
    border-radius: 12px;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.5);
  }

  /* ✅ Sticky (non-overlapping) on desktop when pinned */
  @media (min-width: 768px) {
    .pinned .sidebar {
      position: sticky;
      top: 2rem;
      align-self: start;
      max-height: calc(100vh - 4rem);
      overflow: auto;
    }
  }

  /* ✅ When "free", sidebar just scrolls in-flow */
  .free .sidebar {
    position: static;
    max-height: none;
    overflow: visible;
  }

  /* ✅ FORCE: Mobile/tablet — sidebar BELOW, never sticky/fixed */
  @media (max-width: 767px) {
    .sidebar {
      position: static !important;
      top: auto !important;
      max-height: none !important;
      overflow: visible !important;
      width: 100%;
      border-top: 1px solid #333;
    }
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
