---
layout: default
title: Home
---

<!-- Include Three.js & FontAwesome from CDN -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

<style>
  :root {
    --bg-dark: #0b0f19;
    --card-bg: rgba(17, 24, 39, 0.75);
    --border-glow: rgba(59, 130, 246, 0.25);
    --accent-blue: #3b82f6;
    --accent-cyan: #06b6d4;
    --text-primary: #f3f4f6;
    --text-muted: #9ca3af;
  }

  body {
    background-color: var(--bg-dark);
    color: var(--text-primary);
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
    margin: 0;
    overflow-x: hidden;
  }

  /* 3D Hero Section */
  .hero-container {
    position: relative;
    min-height: 88vh;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 2rem 5%;
    overflow: hidden;
  }

  #canvas-container {
    position: absolute;
    top: 0;
    right: 0;
    width: 55%;
    height: 100%;
    z-index: 1;
    pointer-events: auto;
  }

  .hero-content {
    position: relative;
    z-index: 2;
    max-width: 600px;
    backdrop-filter: blur(8px);
    background: rgba(11, 15, 25, 0.6);
    padding: 2.5rem;
    border-radius: 20px;
    border: 1px solid var(--border-glow);
  }

  .hero-badge {
    display: inline-block;
    padding: 6px 14px;
    background: rgba(59, 130, 246, 0.15);
    color: var(--accent-cyan);
    border: 1px solid rgba(6, 182, 212, 0.4);
    border-radius: 20px;
    font-size: 0.85rem;
    font-weight: 600;
    margin-bottom: 1.2rem;
    letter-spacing: 0.05em;
  }

  .hero-title {
    font-size: 3rem;
    line-height: 1.15;
    font-weight: 800;
    margin-bottom: 1rem;
    background: linear-gradient(135deg, #ffffff 0%, #93c5fd 50%, #06b6d4 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }

  .hero-subtitle {
    font-size: 1.15rem;
    color: var(--text-muted);
    line-height: 1.6;
    margin-bottom: 2rem;
  }

  .btn-group {
    display: flex;
    gap: 1rem;
  }

  .btn-primary {
    background: linear-gradient(135deg, #2563eb, #06b6d4);
    color: #fff;
    padding: 12px 28px;
    border-radius: 10px;
    font-weight: 600;
    text-decoration: none;
    transition: all 0.3s ease;
    box-shadow: 0 4px 15px rgba(37, 99, 235, 0.3);
  }

  .btn-primary:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 25px rgba(6, 182, 212, 0.45);
  }

  .btn-secondary {
    background: rgba(255, 255, 255, 0.05);
    color: #fff;
    padding: 12px 28px;
    border-radius: 10px;
    font-weight: 600;
    text-decoration: none;
    border: 1px solid rgba(255, 255, 255, 0.15);
    transition: all 0.3s ease;
  }

  .btn-secondary:hover {
    background: rgba(255, 255, 255, 0.1);
  }

  /* Grid Layouts */
  .section-container {
    padding: 5rem 5%;
    max-width: 1280px;
    margin: 0 auto;
  }

  .section-header {
    text-align: center;
    margin-bottom: 3.5rem;
  }

  .section-title {
    font-size: 2.2rem;
    font-weight: 700;
    margin-bottom: 0.5rem;
  }

  .card-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 2rem;
  }

  .glass-card {
    background: var(--card-bg);
    border: 1px solid var(--border-glow);
    border-radius: 16px;
    padding: 2rem;
    backdrop-filter: blur(12px);
    transition: transform 0.3s ease, border-color 0.3s ease;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }

  .glass-card:hover {
    transform: translateY(-6px);
    border-color: var(--accent-cyan);
  }

  .card-icon {
    font-size: 2rem;
    color: var(--accent-cyan);
    margin-bottom: 1.2rem;
  }

  .card-title {
    font-size: 1.35rem;
    margin-bottom: 0.8rem;
    font-weight: 700;
  }

  .card-text {
    color: var(--text-muted);
    font-size: 0.95rem;
    line-height: 1.6;
    margin-bottom: 1.5rem;
  }

  @media (max-width: 900px) {
    .hero-container {
      flex-direction: column;
      padding-top: 4rem;
    }
    #canvas-container {
      position: relative;
      width: 100%;
      height: 350px;
    }
    .hero-content {
      max-width: 100%;
    }
    .hero-title {
      font-size: 2.2rem;
    }
  }
</style>

<!-- 3D HERO SECTION -->
<div class="hero-container">
  <div class="hero-content">
    <span class="hero-badge"><i class="fas fa-atom"></i> Next-Gen Materials Engineering</span>
    <h1 class="hero-title">Master Metallurgy & Materials Science</h1>
    <p class="hero-subtitle">
      Explore crystal structures, thermodynamics, and kinetics with interactive visualizations and high-yield course curricula.
    </p>
    <div class="btn-group">
      <a href="#courses" class="btn-primary">Explore Courses</a>
      <a href="#blog" class="btn-secondary">Read Articles</a>
    </div>
  </div>

  <div id="canvas-container"></div>
</div>

<!-- COURSES SECTION -->
<section id="courses" class="section-container">
  <div class="section-header">
    <h2 class="section-title">Core Engineering Modules</h2>
    <p style="color: var(--text-muted)">Engineered for conceptual depth and competitive exams (GATE & BARC)</p>
  </div>

  <div class="card-grid">
    <div class="glass-card">
      <div>
        <div class="card-icon"><i class="fas fa-cube"></i></div>
        <h3 class="card-title">Physical Metallurgy & Crystallography</h3>
        <p class="card-text">Deep-dive into unit cells, dislocation mechanisms, phase transformations, TTT/CCT diagrams, and microstructure evolution.</p>
      </div>
      <a href="#contact" class="btn-secondary" style="text-align: center;">View Syllabus</a>
    </div>

    <div class="glass-card">
      <div>
        <div class="card-icon"><i class="fas fa-fire-alt"></i></div>
        <h3 class="card-title">Thermodynamics & Kinetics</h3>
        <p class="card-text">Master Ellingham diagrams, driving force calculations, diffusion equations, and interfacial reaction kinetics.</p>
      </div>
      <a href="#contact" class="btn-secondary" style="text-align: center;">View Syllabus</a>
    </div>

    <div class="glass-card">
      <div>
        <div class="card-icon"><i class="fas fa-compress-arrows-alt"></i></div>
        <h3 class="card-title">Mechanical Metallurgy & Fracture</h3>
        <p class="card-text">Comprehensive analysis of generalized Hooke's Law, slip systems, creep deformation, fatigue lifecycles, and failure mechanics.</p>
      </div>
      <a href="#contact" class="btn-secondary" style="text-align: center;">View Syllabus</a>
    </div>
  </div>
</section>

<!-- BLOG ARTICLES PREVIEW SECTION -->
<section id="blog" class="section-container" style="background: rgba(0,0,0,0.2); border-radius: 24px;">
  <div class="section-header">
    <h2 class="section-title">Technical Insights & Publications</h2>
    <p style="color: var(--text-muted)">Latest mathematical derivations, exam strategies, and research breakdowns</p>
  </div>

  <div class="card-grid">
    <div class="glass-card">
      <div>
        <span style="color: var(--accent-cyan); font-size: 0.85rem; font-weight: 600;">METALLURGICAL KINETICS</span>
        <h3 class="card-title" style="margin-top: 0.5rem;">Analyzing FCC vs BCC Stability and Energy</h3>
        <p class="card-text">A rigorous breakdown of atomic packing, interstitial void geometry, and transformation thermodynamics under high temperature.</p>
      </div>
      <a href="/blog/understanding-fcc-bcc-phase-transformations/" class="btn-secondary" style="text-align: center;">Read Full Article &rarr;</a>
    </div>

    <div class="glass-card">
      <div>
        <span style="color: var(--accent-cyan); font-size: 0.85rem; font-weight: 600;">EXAM ANALYTICS</span>
        <h3 class="card-title" style="margin-top: 0.5rem;">GATE MT & XE Strategic Blueprint</h3>
        <p class="card-text">Topic-wise weightage breakdown, past question trends, and high-accuracy numerical evaluation methods.</p>
      </div>
      <a href="#contact" class="btn-secondary" style="text-align: center;">Read Full Article &rarr;</a>
    </div>
  </div>
</section>

<!-- THREE.JS 3D FLOATING LATTICE SCRIPT -->
<script>
  (function() {
    const container = document.getElementById('canvas-container');
    if (!container) return;

    // Scene Setup
    const scene = new THREE.Scene();
    const camera = new THREE.PerspectiveCamera(45, container.clientWidth / container.clientHeight, 0.1, 1000);
    camera.position.z = 8;

    const renderer = new THREE.WebGLRenderer({ alpha: true, antialias: true });
    renderer.setSize(container.clientWidth, container.clientHeight);
    renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));
    container.appendChild(renderer.domElement);

    // Group for Crystal Lattice
    const crystalGroup = new THREE.Group();
    scene.add(crystalGroup);

    // Materials
    const atomMaterial = new THREE.MeshPhongMaterial({
      color: 0x06b6d4,
      emissive: 0x083344,
      shininess: 100,
      specular: 0xffffff
    });

    const centerAtomMaterial = new THREE.MeshPhongMaterial({
      color: 0x3b82f6,
      emissive: 0x1e3a8a,
      shininess: 100,
      specular: 0xffffff
    });

    const bondMaterial = new THREE.MeshBasicMaterial({
      color: 0x60a5fa,
      wireframe: true,
      transparent: true,
      opacity: 0.35
    });

    // Outer Bounding Lattice Cube
    const cubeGeo = new THREE.BoxGeometry(3, 3, 3);
    const cubeEdges = new THREE.LineSegments(
      new THREE.EdgesGeometry(cubeGeo),
      new THREE.LineBasicMaterial({ color: 0x3b82f6, linewidth: 2, transparent: true, opacity: 0.6 })
    );
    crystalGroup.add(cubeEdges);

    // Corner Atoms (BCC / FCC style representation)
    const atomGeo = new THREE.SphereGeometry(0.24, 32, 32);
    const cornerPositions = [
      [-1.5, -1.5, -1.5], [ 1.5, -1.5, -1.5], [-1.5,  1.5, -1.5], [ 1.5,  1.5, -1.5],
      [-1.5, -1.5,  1.5], [ 1.5, -1.5,  1.5], [-1.5,  1.5,  1.5], [ 1.5,  1.5,  1.5],
    ];

    cornerPositions.forEach(pos => {
      const atom = new THREE.Mesh(atomGeo, atomMaterial);
      atom.position.set(pos[0], pos[1], pos[2]);
      crystalGroup.add(atom);
    });

    // Central Atom
    const centerAtom = new THREE.Mesh(new THREE.SphereGeometry(0.36, 32, 32), centerAtomMaterial);
    crystalGroup.add(centerAtom);

    // Diagonal Internal Bonds
    cornerPositions.forEach(pos => {
      const points = [new THREE.Vector3(0, 0, 0), new THREE.Vector3(pos[0], pos[1], pos[2])];
      const lineGeo = new THREE.BufferGeometry().setFromPoints(points);
      const line = new THREE.Line(lineGeo, new THREE.LineBasicMaterial({ color: 0x0ea5e9, transparent: true, opacity: 0.3 }));
      crystalGroup.add(line);
    });

    // Lighting
    const ambientLight = new THREE.AmbientLight(0xffffff, 0.7);
    scene.add(ambientLight);

    const pointLight = new THREE.PointLight(0x06b6d4, 2, 50);
    pointLight.position.set(5, 5, 5);
    scene.add(pointLight);

    const blueLight = new THREE.PointLight(0x3b82f6, 1.5, 50);
    blueLight.position.set(-5, -5, -2);
    scene.add(blueLight);

    // Mouse Interaction
    let mouseX = 0;
    let mouseY = 0;
    window.addEventListener('mousemove', (e) => {
      mouseX = (e.clientX / window.innerWidth - 0.5) * 0.8;
      mouseY = (e.clientY / window.innerHeight - 0.5) * 0.8;
    });

    // Animation Loop
    function animate() {
      requestAnimationFrame(animate);

      // Smooth floating and rotating animation
      crystalGroup.rotation.y += 0.005;
      crystalGroup.rotation.x += 0.003;

      // Parallax interaction with mouse
      crystalGroup.rotation.y += (mouseX - crystalGroup.rotation.y * 0.1) * 0.05;
      crystalGroup.rotation.x += (mouseY - crystalGroup.rotation.x * 0.1) * 0.05;

      renderer.render(scene, camera);
    }
    animate();

    // Resize Handler
    window.addEventListener('resize', () => {
      if (!container) return;
      camera.aspect = container.clientWidth / container.clientHeight;
      camera.updateProjectionMatrix();
      renderer.setSize(container.clientWidth, container.clientHeight);
    });
  })();
</script>
