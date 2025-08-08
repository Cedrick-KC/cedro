<script>
    const projects = [
      {
        name: 'E-commerce Platform',
        description: 'A full-stack e-commerce site built with Node.js and PostgreSQL.',
        tech: ['Svelte', 'Node.js', 'PostgreSQL'],
        link: '#'
      },
      {
        name: 'Task Manager App',
        description: 'A simple and intuitive task management application.',
        tech: ['Svelte', 'JavaScript'],
        link: 'https://noote-sece.onrender.com'
      },
      {
        name: 'Portfolio Website',
        description: 'This very portfolio, designed and built from scratch.',
        tech: ['Svelte', 'HTML', 'CSS'],
        link: ''
      }
    ];
  </script>
  
  <section class="projects-section">
    <h2 class="section-title">Projects</h2>
    <div class="projects-grid">
      {#each projects as project}
        <div class="project-card">
          <h3>{project.name}</h3>
          <p>{project.description}</p>
          <div class="tech-stack">
            {#each project.tech as tech}
              <span>{tech}</span>
            {/each}
          </div>
          <a href={project.link} target="_blank" rel="noopener noreferrer">View Project</a>
        </div>
      {/each}
    </div>
  </section>
  
  <style>
    .projects-section {
      margin-top: 2rem;
    }
    .section-title {
      color: #58a6ff;
      border-bottom: 1px solid #333;
      padding-bottom: 0.5rem;
      margin-bottom: 1rem;
    }
    .projects-grid {
      display: grid;
      gap: 1.5rem;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    }
    .project-card {
      background-color: #21262d;
      padding: 1.5rem;
      border-radius: 12px;
      box-shadow: 0 2px 8px rgba(0, 0, 0, 0.3);
      transition: transform 0.2s ease;
    }
    .project-card:hover {
      transform: translateY(-5px);
    }
    .project-card h3 {
      margin-top: 0;
      color: #79c0ff;
    }
    .tech-stack span {
      display: inline-block;
      background-color: #30363d;
      color: #c9d1d9;
      padding: 0.25rem 0.75rem;
      border-radius: 15px;
      font-size: 0.75rem;
      margin-right: 0.5rem;
      margin-top: 0.5rem;
    }
    .project-card a {
      display: inline-block;
      margin-top: 1rem;
      color: #58a6ff;
      text-decoration: none;
      font-weight: bold;
    }
  </style>