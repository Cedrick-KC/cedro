<script>
    let imageSrc = 'https://raw.githubusercontent.com/Atcs-645/VISIT-MUSANZE/main/coding_guy.png';
  </script>
  
  <div class="main-content-inner">
    <h2>Welcome to My Portfolio</h2>
    <p>Hello! I'm Cedrique, a passionate software engineer with over 2 years of experience. I specialize in building modern web applications using technologies like Svelte, Node.js, and PostgreSQL.</p>
    <p>I enjoy coding and solving complex problems to create elegant and efficient solutions.</p>
  
    <div class="coding-image-container">
      <img src={imageSrc} alt="A simple guy coding" />
    </div>
  </div>
  
  <style>
    h2 {
      color: #00ffcc;
    }
  
    .coding-image-container {
      margin-top: 40px;
      text-align: center;
    }
  
    .coding-image-container img {
      max-width: 100%;
      height: auto;
      border-radius: 10px;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.5);
    }
  </style>