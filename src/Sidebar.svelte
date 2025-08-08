<script>
  export let full = false;
</script>

<div class="sidebar-content">
  <div class="intro-section">
    <img
      src="https://raw.githubusercontent.com/Atcs-645/VISIT-MUSANZE/main/cedro.png"
      alt="Cedrique"
      class:full
    />
    <h3>Cedrique</h3>
    <p>Software Engineer</p>
  </div>
  
  <div class="profile-section">
    <h2 class="section-title">About Me</h2>
    <p>
      I am a passionate and results-driven Software 
      Engineer who started development journey with 
      14 years with over 4 years of experience in web app development and in hardware IoT things. My expertise lies in
       both front-end development and back-end services. I thrive on solving complex problems and creating clean, efficient code that delivers a great user experience.
    </p>
    {#if full}
      <p><strong>Experience:</strong> 3+ years</p>
      <p><strong>Location:</strong> Remote / Global</p>
    {/if}
  </div>

  {#if full}
    <div class="certifications-section">
      <h2 class="section-title">Certifications</h2>
      <ul>
        <li>Professional Svelte Developer</li>
        <li>Node.js API Development</li>
        <li>PostgreSQL for Developers</li>
        <li>Robotics and IoT development Certificate</li>
        <li>Digital Skills Foundation Certificate</li>
      </ul>
    </div>
  {/if}

  <div class="skills-section">
    <h2 class="section-title">Skills</h2>
    <div class="skills-grid" class:full-grid={full}>
      <div class="skill-card">
        <img src="https://raw.githubusercontent.com/Atcs-645/VISIT-MUSANZE/main/js.png" alt="JavaScript" />
        <span>JavaScript</span>
      </div>
      <div class="skill-card">
        <img src="https://raw.githubusercontent.com/Atcs-645/VISIT-MUSANZE/main/svelte.png" alt="Svelte" />
        <span>Svelte</span>
      </div>
      {#if full}
        <div class="skill-card">
          <img src="https://raw.githubusercontent.com/Atcs-645/VISIT-MUSANZE/main/node.png" alt="Node.js" />
          <span>Node.js</span>
        </div>
        <div class="skill-card">
          <img src="https://raw.githubusercontent.com/Atcs-645/VISIT-MUSANZE/main/arduino.png" alt="Node.js" />
          <span>Arduiono IoT Setups</span>
        </div>
        <div class="skill-card">
          <img src="https://raw.githubusercontent.com/Atcs-645/VISIT-MUSANZE/main/raspberry.png" alt="PostgreSQL" />
          <span>RaspBerry Pi</span>
        </div>
        <div class="skill-card">
          <img src="https://raw.githubusercontent.com/Atcs-645/VISIT-MUSANZE/main/postgresql.png" alt="PostgreSQL" />
          <span>PostgreSQL</span>
        </div>
      {/if}
    </div>
  </div>
</div>

<style>
  *{
    font-size: medium;
  }
  .sidebar-content {
    display: flex;
    flex-direction: column;
    gap: 2rem;
  }
  
  .intro-section {
    text-align: center;
    padding-bottom: 2rem;
    border-bottom: 1px solid #333;
    margin-bottom: 2rem;
  }
  
  .intro-section img {
    width: 100px;
    border-radius: 50%;
    border: 2px solid #58a6ff;
    transition: width 0.3s ease;
  }
  
  .intro-section img.full {
    width: 180px;
  }
  
  .intro-section h3 {
    margin: 1rem 0 0.25rem 0;
    color: #e6edf3;
  }
  
  .intro-section p {
    margin: 0;
    color: #8b949e;
  }

  .profile-section p {
    margin-bottom: 1em;
  }

  .section-title {
    color: #58a6ff;
    border-bottom: 1px solid #333;
    padding-bottom: 0.5rem;
    margin-bottom: 1rem;
  }

  .certifications-section ul {
    list-style-type: none;
    padding-left: 0;
  }

  .certifications-section li {
    background-color: #21262d;
    padding: 10px 15px;
    border-radius: 8px;
    margin-bottom: 10px;
  }
  
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 1rem;
  }
  
  .skills-grid.full-grid {
    grid-template-columns: repeat(3, 1fr);
  }
  
  .skill-card {
    background-color: #21262d;
    padding: 1rem;
    border-radius: 8px;
    text-align: center;
    transition: transform 0.2s ease;
  }
  
  .skill-card:hover {
    transform: translateY(-5px);
  }
  
  .skill-card img {
    height: 40px;
    width: auto;
    margin-bottom: 0.5rem;
  }
  
  .skill-card span {
    display: block;
    font-size: 0.8rem;
    font-weight: bold;
  }
</style>