<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Advanced N-Body Simulation (3D)</title>
    <!-- Load Tailwind CSS for styling -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- Load three.js (3D Library) -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
    
    <!-- Load three.js Post-Processing (for Bloom/Glow effects) -->
    <script src="https://cdn.jsdelivr.net/npm/three@0.128.0/examples/js/postprocessing/EffectComposer.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/three@0.128.0/examples/js/postprocessing/RenderPass.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/three@0.128.0/examples/js/postprocessing/ShaderPass.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/three@0.128.0/examples/js/shaders/CopyShader.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/three@0.128.0/examples/js/shaders/LuminosityHighPassShader.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/three@0.128.0/examples/js/postprocessing/UnrealBloomPass.js"></script>
    
    <!-- Load three.js Lensflare (for star effects) -->
    <script src="https://cdn.jsdelivr.net/npm/three@0.128.0/examples/js/objects/Lensflare.js"></script>

    <style>
        /* Custom styles for the body and canvas */
        body {
            font-family: 'Inter', sans-serif;
            overflow: hidden; /* Prevent scrolling */
        }
        canvas {
            display: block; /* Remove default margin */
            width: 100%;
            height: 100%;
        }
        /* Style for the controls overlay */
        #controls {
            position: absolute;
            top: 1rem;
            left: 1rem;
            background-color: rgba(17, 24, 39, 0.9); /* bg-gray-900 with alpha */
            backdrop-filter: blur(8px);
            border-radius: 0.5rem;
            border: 1px solid #374151; /* gray-700 */
            color: white;
            width: 300px; /* Fixed width */
            z-index: 10;
            max-height: calc(100vh - 2rem);
            overflow-y: auto;
        }
        #controls-content {
            padding: 1rem;
        }
        #controls-toggle {
            background-color: #374151; /* gray-700 */
            border-bottom-right-radius: 0.5rem;
            border-top-right-radius: 0.5rem;
            position: absolute;
            left: 100%;
            top: 0;
            padding: 0.75rem 0.5rem;
            writing-mode: vertical-rl;
            text-orientation: mixed;
            font-weight: 600;
            cursor: pointer;
            border: 1px solid #374151;
            border-left: none;
        }

        .control-group {
            margin-bottom: 0.75rem;
        }
        .control-group h3 {
            font-weight: 600; /* semibold */
            margin-bottom: 0.5rem;
            border-bottom: 1px solid #4b5563; /* gray-600 */
            padding-bottom: 0.25rem;
        }
        .control-group button, .control-group select {
            width: 100%;
            padding: 0.5rem;
            border-radius: 0.375rem; /* rounded-md */
            font-weight: 500; /* medium */
            transition: all 0.2s;
            border: none;
            color: white;
            background-color: #4b5563; /* gray-600 */
        }
        .control-group button:hover {
            background-color: #6b7280; /* gray-500 */
        }
        .control-group button.active {
            background-color: #3b82f6; /* blue-500 */
            font-weight: 600; /* semibold */
        }
        .control-group .btn-pair {
            display: flex;
            gap: 0.5rem;
        }
        .control-group label {
            display: block;
            font-size: 0.875rem;
            margin-bottom: 0.25rem;
            color: #d1d5db; /* gray-300 */
        }
        .control-group input {
            width: 100%;
            padding: 0.5rem;
            border-radius: 0.375rem;
            background-color: #374151; /* gray-700 */
            border: 1px solid #4b5563; /* gray-600 */
            color: white;
        }
        .input-group-3 {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 0.5rem;
        }

        #simulationCanvas {
            position: absolute;
            top: 0;
            left: 0;
            z-index: 1;
            cursor: grab;
        }
        #simulationCanvas:active {
            cursor: grabbing;
        }
        
        /* Info Displays */
        #infoDisplay {
            position: absolute;
            bottom: 1rem;
            right: 1rem;
            background-color: rgba(17, 24, 39, 0.8);
            backdrop-filter: blur(5px);
            border-radius: 0.5rem;
            padding: 0.75rem 1rem;
            border: 1px solid #374151;
            color: white;
            z-index: 10;
            font-size: 0.875rem;
            line-height: 1.25rem;
            min-width: 200px;
        }
        #selectionInfo {
            position: absolute;
            bottom: 1rem;
            left: 1rem;
            background-color: rgba(17, 24, 39, 0.8);
            backdrop-filter: blur(5px);
            border-radius: 0.5rem;
            padding: 0.75rem 1rem;
            border: 1px solid #374151;
            color: white;
            z-index: 10;
            font-size: 0.875rem;
            line-height: 1.25rem;
            min-width: 220px;
            display: none; /* Hidden by default */
        }
    </style>
</head>
<body class="bg-black text-white flex flex-col items-center justify-center min-h-screen p-0">

    <!-- This canvas will be controlled by three.js -->
    <canvas id="simulationCanvas"></canvas>
    
    <!-- Controls Panel -->
    <div id="controls">
        <div id="controls-toggle" title="Toggle Controls">CONTROLS</div>
        <div id="controls-content">
            <h2 class="text-xl font-bold text-center mb-3">Advanced N-Body Controls</h2>
            
            <!-- Main Controls -->
            <div class="control-group">
                <h3>Simulation</h3>
                <div class="btn-pair">
                    <button id="startButton">Start</button>
                    <button id="stopButton">Stop</button>
                </div>
                <button id="resetButton" class="mt-2">Reset Scenario</button>
                <button id="clearAllButton" class="mt-2 bg-red-600 hover:bg-red-500">Clear All Bodies</button>
            </div>

            <!-- Speed Controls -->
            <div class="control-group">
                <h3>Speed</h3>
                <div class="btn-pair">
                    <button id="normalSpeedButton" class="active">Normal</button>
                    <button id="fastForwardButton">Fast</button>
                </div>
            </div>
            
            <!-- Camera Controls -->
            <div class="control-group">
                <h3>Camera</h3>
                <label for="cameraFollowSelect">Follow Target</label>
                <select id="cameraFollowSelect" class="bg-gray-700 border border-gray-600">
                    <option value="none">None (Free Look)</option>
                    <option value="com">Center of Mass (COM)</option>
                </select>
                <div class="btn-pair mt-2">
                    <button id="resetViewButton">Reset View</button>
                    <button id="zeroComVelButton">Zero COM Velocity</button>
                </div>
            </div>

            <!-- Graphics Controls -->
            <div class="control-group">
                <h3>Graphics</h3>
                <div class="btn-pair">
                    <button id="toggleTrailsButton" class="active">Trails: ON</button>
                    <button id="toggleBloomButton" class="active">Bloom: ON</button>
                </div>
            </div>

            <!-- Scenario Controls -->
            <div class="control-group">
                <h3>Scenario</h3>
                <select id="scenarioSelect" class="bg-gray-700 border border-gray-600">
                    <option value="empty">Empty</option>
                    <option value="sun_planets" selected>Sun + 2 Planets</option>
                    <option value="binary_planet">Binary Star + Planet</option>
                    <option value="figure_eight">Figure-Eight</option>
                    <option value="ejection">Slingshot Ejection</option>
                    <option value="lagrange_L4">Lagrange Point (L4)</option>
                    <option value="ring_system">Ring System</option>
                    <option value="galaxy_collision">Galaxy Collision</option>
                </select>
            </div>
            
            <!-- Collision Controls -->
            <div class="control-group">
                <h3>Collisions</h3>
                <select id="collisionSelect" class="bg-gray-700 border border-gray-600">
                    <option value="none">None</option>
                    <option value="merge" selected>Merge</option>
                    <option value="bounce">Bounce (Elastic)</option>
                </select>
            </div>
            
            <!-- Spawn Menu -->
            <div class="control-group">
                <h3>Spawn Object</h3>
                <label for="spawnTypeSelect">Type</label>
                <select id="spawnTypeSelect" class="bg-gray-700 border border-gray-600">
                    <option value="earth">Earth-like Planet</option>
                    <option value="neutron_star">Neutron Star</option>
                    <option value="giant_star">Giant Star (Supernova)</option>
                    <option value="black_hole">Black Hole</option>
                    <option value="custom">Custom</option>
                </select>
                
                <div id="customSpawnParams" class="mt-2 space-y-2 hidden">
                    <label>Mass</label>
                    <input type="number" id="customMass" value="100">
                    <label>Position (X, Y, Z)</label>
                    <div class="input-group-3">
                        <input type="number" id="customPx" value="0">
                        <input type="number" id="customPy" value="0">
                        <input type="number" id="customPz" value="0">
                    </div>
                    <label>Velocity (X, Y, Z)</label>
                    <div class="input-group-3">
                        <input type="number" id="customVx" value="0">
                        <input type="number" id="customVy" value="0">
                        <input type="number" id="customVz" value="0">
                    </div>
                </div>

                <div class="btn-pair mt-2">
                    <button id="spawnAtOriginButton">Spawn at Origin</button>
                    <button id="spawnWithVelButton" class="active">Spawn w/ Velocity (Drag)</button>
                </div>
            </div>
            
            <p class="text-xs text-gray-400 mt-4 text-center">Drag to rotate, Scroll to zoom, Right-drag to pan, Click to select/drag-spawn</p>
        </div>
    </div>

    <!-- Info Displays -->
    <div id="infoDisplay">
        <strong>Camera (X, Y, Z):</strong><br>
        <span id="camCoords">0.0, 0.0, 0.0</span><br>
        <strong>Total Bodies:</strong> <span id="bodyCount">0</span><br>
        <strong>Total Mass:</strong> <span id="totalMass">0.0</span><br>
        <strong>Kinetic Energy:</strong> <span id="kineticEnergy">0.0</span><br>
        <strong>Potential Energy:</strong> <span id="potentialEnergy">0.0</span><br>
        <strong>Total Energy:</strong> <span id="totalEnergy">0.0</span>
    </div>
    <div id="selectionInfo">
        <strong>Selected Body</strong><br>
        <strong>ID:</strong> <span id="selectId">N/A</span><br>
        <strong>Mass:</strong> <span id="selectMass">N/A</span><br>
        <strong>Pos (X,Y,Z):</strong> <span id="selectPos">N/A</span><br>
        <strong>Vel (X,Y,Z):</strong> <span id="selectVel">N/A</span><br>
        <span id="selectLifetime"></span>
    </div>

    <script>
        // Check if all three.js components loaded
        if (typeof THREE === 'undefined' || typeof THREE.EffectComposer === 'undefined' || typeof THREE.UnrealBloomPass === 'undefined' || typeof THREE.Lensflare === 'undefined') {
            document.body.innerHTML = '<h1 style="color: red; text-align: center; margin-top: 50px;">Error: Could not load three.js libraries. Please check your internet connection.</h1>';
        } else {
            // --- Simulation Logic (3D Version) ---
            window.addEventListener('DOMContentLoaded', () => {

                // --- Simulation Constants ---
                const G = 1.0;
                const DT = 0.001;
                const EPSILON = 0.01;
                const MAX_TRACE_POINTS = 2000;
                const SUPERNOVA_LIFETIME = 15; // in seconds
                
                // --- Simulation State ---
                let bodies = [];
                let bodyIdCounter = 0;
                let stepsPerFrame = 10;
                let collisionMode = 'merge';
                let scenario = 'sun_planets';
                let animationId = null;
                let visualEffects = []; // For supernovas, etc.
                let systemCOM = {
                    position: new THREE.Vector3(),
                    velocity: new THREE.Vector3(),
                    totalMass: 0
                };
                
                // --- Three.js State ---
                const canvas = document.getElementById('simulationCanvas');
                let scene, camera, renderer, sunLight, starField;
                let composer, bloomPass;
                let clock = new THREE.Clock();
                let selectionOutline, velocityGizmo;

                // --- Controls State ---
                let mouseControls = {
                    dragging: false,
                    panning: false,
                    lastMouse: { x: 0, y: 0 },
                    rotation: { x: Math.PI / 3, y: -Math.PI / 4 },
                    target: new THREE.Vector3(0, 0, 0), // Camera target
                    zoom: 50
                };
                let raycaster = new THREE.Raycaster();
                let plane = new THREE.Plane(new THREE.Vector3(0, 1, 0), 0); // Spawning plane
                let mouse = new THREE.Vector2();
                let spawnMode = 'drag'; // 'origin' or 'drag'
                let isSpawning = false;
                let spawnStartPosition = new THREE.Vector3();
                let cameraFollowId = 'none'; // 'none', 'com', or a body ID
                let selectedBody = null;

                /**
                 * @class Body
                 * @brief JS 3D equivalent of the Body struct
                 */
                class Body {
                    constructor(mass, px, py, pz, vx, vy, vz, color, isStar = false, lifetime = -1) {
                        this.id = bodyIdCounter++;
                        this.mass = mass;
                        this.px = px; this.py = py; this.pz = pz;
                        this.vx = vx; this.vy = vy; this.vz = vz;
                        this.ax = 0.0; this.ay = 0.0; this.az = 0.0;
                        this.color = new THREE.Color(color);
                        this.isStar = isStar;
                        
                        this.lifetime = lifetime; // -1 for infinite
                        this.age = 0;

                        // Physics radius for collision
                        this.physicsRadius = Math.pow((3 * this.mass) / (4 * Math.PI), 1/3) * 0.1;
                        
                        // Visual radius (log-scaled for better aesthetics)
                        const logMass = this.mass <= 1 ? 0 : Math.log10(this.mass);
                        const visualRadius = Math.max(0.1, logMass * 0.5 + 0.2);
                        this.visualRadius = visualRadius; // Store for outline

                        // Create 3D Mesh
                        const geometry = new THREE.SphereGeometry(visualRadius, 32, 16);
                        let material;
                        if (isStar) {
                            material = new THREE.MeshBasicMaterial({ color: this.color });
                        } else {
                            material = new THREE.MeshStandardMaterial({ 
                                color: this.color, 
                                metalness: 0.3, 
                                roughness: 0.5 
                            });
                        }
                        this.mesh = new THREE.Mesh(geometry, material);
                        this.mesh.position.set(px, py, pz);
                        this.mesh.userData.bodyId = this.id; // Link mesh back to body
                        
                        // Special graphics for black holes
                        if (this.color.getHexString() === '000000') {
                            this.mesh.material = new THREE.MeshStandardMaterial({ color: 0x000000, metalness: 0.0, roughness: 0.5 });
                            this.physicsRadius *= 5; 
                            
                            const diskGeo = new THREE.RingGeometry(visualRadius * 1.5, visualRadius * 3.5, 32);
                            const diskMat = new THREE.MeshBasicMaterial({ color: 0xf97316, side: THREE.DoubleSide, transparent: true, opacity: 0.7 });
                            this.accretionDisk = new THREE.Mesh(diskGeo, diskMat);
                            this.accretionDisk.rotation.x = Math.PI / 2.2;
                            this.mesh.add(this.accretionDisk);
                        }
                        
                        // Special graphics for neutron stars
                        if (this.mass > 3000 && this.mass < 5000) {
                            // scene.remove(this.mesh); // We don't add to scene here
                            const nsGeo = new THREE.SphereGeometry(0.1, 32, 16);
                            this.mesh = new THREE.Mesh(nsGeo, material);
                            this.mesh.position.set(px, py, pz);
                            this.mesh.userData.bodyId = this.id;
                            
                            // Add pulsating light
                            this.light = new THREE.PointLight(this.color, 5, 100);
                            this.mesh.add(this.light);
                        }
                        
                        // Add Lensflare to stars
                        if (this.isStar) {
                            const lensflare = new THREE.Lensflare();
                            const textureLoader = new THREE.TextureLoader();
                            // Placeholder textures (cannot load external files, so this part won't work in-browser)
                            // In a real scenario, you'd load flare textures
                            // We will simulate it with a simple bright material
                            this.mesh.material = new THREE.MeshBasicMaterial({ 
                                color: this.color, 
                                emissive: this.color,
                                emissiveIntensity: 1 
                            });
                        }

                        // Create orbital trail
                        const trailMaterial = new THREE.LineBasicMaterial({ 
                            color: this.color, 
                            transparent: true, 
                            opacity: 0.6,
                            vertexColors: true // Enable vertex colors for fading
                        });
                        const trailGeometry = new THREE.BufferGeometry();
                        const trailPositions = new Float32Array(MAX_TRACE_POINTS * 3); // x, y, z
                        const trailColors = new Float32Array(MAX_TRACE_POINTS * 3); // r, g, b
                        trailGeometry.setAttribute('position', new THREE.BufferAttribute(trailPositions, 3));
                        trailGeometry.setAttribute('color', new THREE.BufferAttribute(trailColors, 3));
                        
                        this.trail = new THREE.Line(trailGeometry, trailMaterial);
                        this.trailPoints = trailPositions;
                        this.trailColors = trailColors;
                        this.trailHead = 0;
                        this.trailDrawCount = 0;
                    }
                    
                    // Add a point to the trail, with fading color
                    updateTrail() {
                        const i = this.trailHead * 3;
                        this.trailPoints[i]   = this.px;
                        this.trailPoints[i+1] = this.py;
                        this.trailPoints[i+2] = this.pz;
                        
                        this.trailHead = (this.trailHead + 1) % MAX_TRACE_POINTS;
                        
                        if (this.trailDrawCount < MAX_TRACE_POINTS) {
                            this.trailDrawCount++;
                        }
                        
                        // Update colors for fade
                        for (let j = 0; j < this.trailDrawCount; j++) {
                            const alpha = 1.0 - (j / this.trailDrawCount);
                            const colorIndex = ((this.trailHead - 1 - j + MAX_TRACE_POINTS) % MAX_TRACE_POINTS) * 3;
                            this.trailColors[colorIndex]   = this.color.r * alpha;
                            this.trailColors[colorIndex+1] = this.color.g * alpha;
                            this.trailColors[colorIndex+2] = this.color.b * alpha;
                        }

                        this.trail.geometry.setDrawRange(0, this.trailDrawCount);
                        this.trail.geometry.attributes.position.needsUpdate = true;
                        this.trail.geometry.attributes.color.needsUpdate = true;
                    }

                    // Remove object from scene
                    removeFromScene(scene) {
                        scene.remove(this.mesh);
                        scene.remove(this.trail);
                        if (this.light) this.mesh.remove(this.light);
                        this.mesh.geometry.dispose();
                        this.mesh.material.dispose();
                        if (this.accretionDisk) {
                            this.accretionDisk.geometry.dispose();
                            this.accretionDisk.material.dispose();
                        }
                        this.trail.geometry.dispose();
                        this.trail.material.dispose();
                    }
                }
                
                // --- Function Implementations ---

                /**
                 * @brief Main initialization function
                 */
                function init() {
                    // Create Scene
                    scene = new THREE.Scene();
                    
                    // Create Camera
                    camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 5000);
                    updateCameraPosition();
                    
                    // Create Renderer
                    renderer = new THREE.WebGLRenderer({ canvas: canvas, antialias: true });
                    renderer.setSize(window.innerWidth, window.innerHeight);
                    renderer.setPixelRatio(window.devicePixelRatio);
                    renderer.toneMapping = THREE.ReinhardToneMapping;
                    
                    // Add Lights
                    scene.add(new THREE.AmbientLight(0xffffff, 0.2));
                    sunLight = new THREE.PointLight(0xffffff, 1.5, 4000);
                    scene.add(sunLight);
                    
                    // Add Starfield
                    generateStarfield();
                    
                    // Add Selection Outline (hidden)
                    const outlineMat = new THREE.MeshBasicMaterial({ color: 0x00ff00, side: THREE.BackSide, transparent: true, opacity: 0.5 });
                    const outlineGeo = new THREE.SphereGeometry(1, 32, 16);
                    selectionOutline = new THREE.Mesh(outlineGeo, outlineMat);
                    selectionOutline.visible = false;
                    scene.add(selectionOutline);
                    
                    // Add Velocity Gizmo (hidden)
                    const gizmoMat = new THREE.LineBasicMaterial({ color: 0xffaa00 });
                    const gizmoGeo = new THREE.BufferGeometry().setFromPoints([new THREE.Vector3(), new THREE.Vector3()]);
                    velocityGizmo = new THREE.Line(gizmoGeo, gizmoMat);
                    velocityGizmo.visible = false;
                    scene.add(velocityGizmo);

                    // Setup Post-Processing (Bloom)
                    setupPostProcessing();

                    // Setup scene
                    initialize_bodies();

                    // Add Event Listeners
                    setupEventListeners();
                    
                    // Render one frame to show initial state
                    updateCameraPosition();
                    composer.render();
                    
                    updateUI();
                }
                
                /**
                 * @brief Sets up the EffectComposer for bloom
                 */
                function setupPostProcessing() {
                    const renderScene = new THREE.RenderPass(scene, camera);
                    
                    bloomPass = new THREE.UnrealBloomPass(new THREE.Vector2(window.innerWidth, window.innerHeight), 1.0, 0.4, 0.85);
                    bloomPass.threshold = 0.0;
                    bloomPass.strength = 1.0; 
                    bloomPass.radius = 0.5;

                    composer = new THREE.EffectComposer(renderer);
                    composer.addPass(renderScene);
                    composer.addPass(bloomPass);
                }

                /**
                 * @brief Generates a 3D starfield
                 */
                function generateStarfield() {
                    const starVertices = [];
                    for (let i = 0; i < 10000; i++) {
                        const x = THREE.MathUtils.randFloatSpread(4000);
                        const y = THREE.MathUtils.randFloatSpread(4000);
                        const z = THREE.MathUtils.randFloatSpread(4000);
                        starVertices.push(x, y, z);
                    }
                    const starGeometry = new THREE.BufferGeometry();
                    starGeometry.setAttribute('position', new THREE.Float32BufferAttribute(starVertices, 3));
                    const starMaterial = new THREE.PointsMaterial({ color: 0xffffff, size: 0.7, transparent: true, opacity: 0.8 });
                    starField = new THREE.Points(starGeometry, starMaterial);
                    scene.add(starField);
                }

                /**
                 * @brief Clears and re-initializes bodies based on the selected scenario.
                 */
                function initialize_bodies() {
                    // Clear old bodies
                    clearAllBodies();
                    
                    let lightPos = new THREE.Vector3(0, 0, 0);
                    
                    switch(scenario) {
                        case 'empty':
                            mouseControls.zoom = 50;
                            break;
                        case 'sun_planets':
                            mouseControls.zoom = 50;
                            bodies.push(new Body(1000.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 'yellow', true));
                            bodies.push(new Body(1.0, 10.0, 0.0, 0.0, 0.0, 10.0, 0.0, '#3b82f6'));
                            bodies.push(new Body(1.0, 0.0, -20.0, 0.0, 7.0, 0.0, 0.0, '#22c55e'));
                            lightPos.set(0, 0, 0);
                            break;
                        
                        case 'binary_planet':
                            mouseControls.zoom = 70;
                            bodies.push(new Body(800.0, -10.0, 0.0, 0.0, 0.0, -5.0, 0.0, '#f97316', true));
                            bodies.push(new Body(800.0, 10.0, 0.0, 0.0, 0.0, 5.0, 0.0, '#3b82f6', true));
                            bodies.push(new Body(5.0, 30.0, 0.0, 0.0, 0.0, 10.0, 0.0, '#a855f7'));
                            lightPos.set(0, 0, 0);
                            break;
                            
                        case 'figure_eight':
                            mouseControls.zoom = 5;
                            bodies.push(new Body(1.0, 0.97000436, -0.24308753, 0.0, 0.46620368, 0.43236573, 0.0, '#e11d48'));
                            bodies.push(new Body(1.0, -0.97000436, 0.24308753, 0.0, 0.46620368, 0.43236573, 0.0, '#22c55e'));
                            bodies.push(new Body(1.0, 0.0, 0.0, 0.0, -0.93240736, -0.86473146, 0.0, '#3b82f6'));
                            lightPos.set(0, 0, 0);
                            break;
                        
                        case 'ejection':
                            mouseControls.zoom = 60;
                            bodies.push(new Body(1000.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 'yellow', true));
                            bodies.push(new Body(50.0, 20.0, 0.0, 0.0, 0.0, 8.0, 0.0, '#a855f7'));
                            bodies.push(new Body(1.0, 19.0, 1.0, 3.0, -1.0, 12.0, 0.0, '#e11d48'));
                            lightPos.set(0, 0, 0);
                            break;

                        case 'lagrange_L4':
                            mouseControls.zoom = 30;
                            const m1 = 1000.0;
                            const m2 = 1.0;
                            const r = 20.0;
                            const v1 = -Math.sqrt(G * m2 * m2 / ((m1 + m2) * r));
                            const v2 = Math.sqrt(G * m1 * m1 / ((m1 + m2) * r));
                            bodies.push(new Body(m1, 0, 0, 0, 0, v1, 0, 'yellow', true)); // Sun
                            bodies.push(new Body(m2, r, 0, 0, 0, v2, 0, '#4fA7f0')); // Earth
                            // L4 point
                            const l4_x = r * 0.5;
                            const l4_y = r * Math.sqrt(3) / 2.0;
                            bodies.push(new Body(0.001, l4_x, 0, l4_y, -v2 * Math.sin(Math.PI/3), v2 * Math.cos(Math.PI/3), 0, '#cccccc'));
                            lightPos.set(0, 0, 0);
                            break;

                        case 'ring_system':
                            mouseControls.zoom = 80;
                            bodies.push(new Body(2000.0, 0, 0, 0, 0, 0, 0, 'orange', true));
                            const num_asteroids = 150;
                            const ring_inner = 15;
                            const ring_outer = 25;
                            for (let i = 0; i < num_asteroids; i++) {
                                const angle = Math.random() * 2 * Math.PI;
                                const r_ast = ring_inner + Math.random() * (ring_outer - ring_inner);
                                const v_ast = Math.sqrt(G * 2000.0 / r_ast);
                                const px = r_ast * Math.cos(angle);
                                const pz = r_ast * Math.sin(angle);
                                const vx = -v_ast * Math.sin(angle);
                                const vz = v_ast * Math.cos(angle);
                                const py = Math.random() * 2 - 1; // Slightly offset
                                bodies.push(new Body(0.01, px, py, pz, vx, 0, vz, '#888888'));
                            }
                            lightPos.set(0, 0, 0);
                            break;
                        
                        case 'galaxy_collision':
                            mouseControls.zoom = 200;
                            const num_stars = 100;
                            // Galaxy 1 (like 'ring')
                            bodies.push(new Body(20000.0, -100, 0, 0, 0, 0, 20, '#000000')); // BH 1
                            for (let i = 0; i < num_stars; i++) {
                                const angle = Math.random() * 2 * Math.PI;
                                const r_ast = 5 + Math.random() * 30;
                                const v_ast = Math.sqrt(G * 20000.0 / r_ast);
                                const px = -100 + r_ast * Math.cos(angle);
                                const pz = r_ast * Math.sin(angle);
                                const vx = -v_ast * Math.sin(angle);
                                const vz = 20 + v_ast * Math.cos(angle);
                                bodies.push(new Body(10.0, px, Math.random()*4-2, pz, vx, 0, vz, 'yellow', true));
                            }
                            // Galaxy 2 (like 'ring')
                            bodies.push(new Body(20000.0, 100, 0, 0, 0, 0, -20, '#000000')); // BH 2
                            for (let i = 0; i < num_stars; i++) {
                                const angle = Math.random() * 2 * Math.PI;
                                const r_ast = 5 + Math.random() * 30;
                                const v_ast = Math.sqrt(G * 20000.0 / r_ast);
                                const px = 100 + r_ast * Math.cos(angle);
                                const pz = r_ast * Math.sin(angle);
                                const vx = -v_ast * Math.sin(angle);
                                const vz = -20 + v_ast * Math.cos(angle);
                                bodies.push(new Body(10.0, px, Math.random()*4-2, pz, vx, 0, vz, '#3b82f6', true));
                            }
                            lightPos.set(0, 0, 0);
                            break;
                    }
                    
                    // Add new bodies to scene
                    bodies.forEach(body => {
                        scene.add(body.mesh);
                        scene.add(body.trail);
                    });
                    
                    // Update light position
                    sunLight.position.copy(lightPos);
                    
                    // Reset camera and UI
                    resetView();
                    updateCameraFollowDropdown();
                    updateUI();
                }
                
                /**
                 * @brief Removes all bodies from the simulation
                 */
                function clearAllBodies() {
                    bodies.forEach(body => body.removeFromScene(scene));
                    bodies = [];
                    visualEffects.forEach(effect => scene.remove(effect));
                    visualEffects = [];
                    selectedBody = null;
                    selectionOutline.visible = false;
                    updateUI();
                }

                /**
                 * @brief Calculates accelerations for all bodies (O(N^2)) in 3D.
                 */
                function calculate_accelerations() {
                    for (let i = 0; i < bodies.length; i++) {
                        const bodyI = bodies[i];
                        let f_total_x = 0.0, f_total_y = 0.0, f_total_z = 0.0;

                        for (let j = 0; j < bodies.length; j++) {
                            if (i === j) continue;
                            const bodyJ = bodies[j];
                            
                            const dx = bodyJ.px - bodyI.px;
                            const dy = bodyJ.py - bodyI.py;
                            const dz = bodyJ.pz - bodyI.pz;
                            
                            const r_squared = (dx * dx) + (dy * dy) + (dz * dz) + (EPSILON * EPSILON);
                            const r = Math.sqrt(r_squared);
                            
                            const force_mag = (G * bodyI.mass * bodyJ.mass) / r_squared;
                            
                            const fx = force_mag * dx / r;
                            const fy = force_mag * dy / r;
                            const fz = force_mag * dz / r;

                            f_total_x += fx;
                            f_total_y += fy;
                            f_total_z += fz;
                        }

                        bodyI.ax = f_total_x / bodyI.mass;
                        bodyI.ay = f_total_y / bodyI.mass;
                        bodyI.az = f_total_z / bodyI.mass;
                    }
                }
                
                /**
                 * @brief Handles collisions between bodies based on selected mode.
                 */
                function handleCollisions() {
                    if (collisionMode === 'none' || bodies.length < 2) return;
                    
                    for (let i = 0; i < bodies.length - 1; i++) {
                        for (let j = i + 1; j < bodies.length; j++) {
                            // Check if bodies exist
                            if (!bodies[i] || !bodies[j]) continue;
                            
                            const bodyI = bodies[i];
                            const bodyJ = bodies[j];

                            const dx = bodyJ.px - bodyI.px;
                            const dy = bodyJ.py - bodyI.py;
                            const dz = bodyJ.pz - bodyI.pz;
                            const dist = Math.sqrt(dx * dx + dy * dy + dz * dz);
                            
                            const sumRadii = bodyI.physicsRadius + bodyJ.physicsRadius;
                            
                            if (dist < sumRadii) {
                                if (collisionMode === 'merge') {
                                    mergeBodies(i, j);
                                } else if (collisionMode === 'bounce') {
                                    elasticCollision(bodyI, bodyJ);
                                }
                                // Restart loop after collision
                                i = -1; 
                                break;
                            }
                        }
                    }
                }
                
                /**
                 * @brief Merges two bodies, conserving mass and momentum in 3D.
                 */
                function mergeBodies(i, j) {
                    const [body1, body2] = (bodies[i].mass > bodies[j].mass) ? [bodies[i], bodies[j]] : [bodies[j], bodies[i]];
                    const body1_idx = bodies.indexOf(body1);
                    const body2_idx = bodies.indexOf(body2);

                    const newMass = body1.mass + body2.mass;
                    
                    // Conserve momentum
                    const newVx = (body1.mass * body1.vx + body2.mass * body2.vx) / newMass;
                    const newVy = (body1.mass * body1.vy + body2.mass * body2.vy) / newMass;
                    const newVz = (body1.mass * body1.vz + body2.mass * body2.vz) / newMass;
                    
                    // New position is center of mass
                    const newPx = (body1.mass * body1.px + body2.mass * body2.px) / newMass;
                    const newPy = (body1.mass * body1.py + body2.mass * body2.py) / newMass;
                    const newPz = (body1.mass * body1.pz + body2.mass * body2.pz) / newMass;
                    
                    const newBody = new Body(newMass, newPx, newPy, newPz, newVx, newVy, newVz, body1.color.getHexString(), body1.isStar || body2.isStar, body1.lifetime);
                    
                    // Remove old bodies
                    body1.removeFromScene(scene);
                    body2.removeFromScene(scene);
                    
                    // If one was selected, select the new one
                    if (selectedBody && (selectedBody.id === body1.id || selectedBody.id === body2.id)) {
                        selectedBody = newBody;
                    }
                    if (cameraFollowId === body1.id || cameraFollowId === body2.id) {
                        cameraFollowId = newBody.id;
                    }
                    
                    // Remove from array (higher index first)
                    bodies.splice(Math.max(body1_idx, body2_idx), 1);
                    bodies.splice(Math.min(body1_idx, body2_idx), 1);
                    
                    // Add new body
                    bodies.push(newBody);
                    scene.add(newBody.mesh);
                    scene.add(newBody.trail);
                    
                    updateCameraFollowDropdown();
                }
                
                /**
                 * @brief Handles 3D elastic collision between two bodies
                 */
                function elasticCollision(body1, body2) {
                    // Ref: https://en.wikipedia.org/wiki/Elastic_collision#Three-dimensional
                    let v1 = new THREE.Vector3(body1.vx, body1.vy, body1.vz);
                    let v2 = new THREE.Vector3(body2.vx, body2.vy, body2.vz);
                    let x1 = new THREE.Vector3(body1.px, body1.py, body1.pz);
                    let x2 = new THREE.Vector3(body2.px, body2.py, body2.pz);
                    let m1 = body1.mass;
                    let m2 = body2.mass;
                    
                    let v1_new = v1.clone().sub(
                        x1.clone().sub(x2).multiplyScalar(
                            v1.clone().sub(v2).dot(x1.clone().sub(x2)) /
                            x1.clone().sub(x2).lengthSq() *
                            (2 * m2 / (m1 + m2))
                        )
                    );
                    let v2_new = v2.clone().sub(
                        x2.clone().sub(x1).multiplyScalar(
                            v2.clone().sub(v1).dot(x2.clone().sub(x1)) /
                            x2.clone().sub(x1).lengthSq() *
                            (2 * m1 / (m1 + m2))
                        )
                    );
                    
                    body1.vx = v1_new.x; body1.vy = v1_new.y; body1.vz = v1_new.z;
                    body2.vx = v2_new.x; body2.vy = v2_new.y; body2.vz = v2_new.z;
                    
                    // Separate them slightly to prevent sticking
                    let overlap = (body1.physicsRadius + body2.physicsRadius) - x1.distanceTo(x2);
                    let separation = x1.clone().sub(x2).normalize().multiplyScalar(overlap * 0.5);
                    body1.px += separation.x; body1.py += separation.y; body1.pz += separation.z;
                    body2.px -= separation.x; body2.py -= separation.y; body2.pz -= separation.z;
                }

                /**
                 * @brief Updates positions and velocities (3D).
                 */
                function update_bodies(deltaTime) {
                    let bodiesToRemove = [];
                    for (let i = 0; i < bodies.length; i++) {
                        const body = bodies[i];
                        
                        body.vx += body.ax * DT;
                        body.vy += body.ay * DT;
                        body.vz += body.az * DT;

                        body.px += body.vx * DT;
                        body.py += body.vy * DT;
                        body.pz += body.vz * DT;
                        
                        // Update 3D mesh position
                        body.mesh.position.set(body.px, body.py, body.pz);
                        
                        // Update trail
                        body.updateTrail();
                        
                        // Update special graphics
                        if (body.accretionDisk) {
                            body.accretionDisk.rotation.z += 0.05; // Spin disk
                        }
                        if (body.light) {
                            body.light.intensity = 5 + Math.sin(clock.getElapsedTime() * 10) * 2; // Pulse
                        }
                        
                        // Handle lifetime
                        if (body.lifetime > 0) {
                            body.age += deltaTime;
                            if (body.age >= body.lifetime) {
                                bodiesToRemove.push(body);
                                triggerSupernova(body);
                            }
                        }
                    }
                    
                    // Remove bodies that have "died"
                    bodiesToRemove.forEach(body => {
                        body.removeFromScene(scene);
                        if (selectedBody && selectedBody.id === body.id) selectedBody = null;
                        if (cameraFollowId === body.id) cameraFollowId = 'none';
                        bodies = bodies.filter(b => b.id !== body.id);
                    });
                    if (bodiesToRemove.length > 0) updateCameraFollowDropdown();
                }
                
                /**
                 * @brief Creates a supernova explosion
                 */
                function triggerSupernova(body) {
                    // Visual effect: expanding shell
                    const geometry = new THREE.SphereGeometry(body.visualRadius, 32, 16);
                    const material = new THREE.MeshBasicMaterial({ color: 0xffa500, transparent: true, opacity: 0.8 });
                    const explosion = new THREE.Mesh(geometry, material);
                    explosion.position.set(body.px, body.py, body.pz);
                    scene.add(explosion);
                    visualEffects.push(explosion);
                    
                    // Debris
                    const numDebris = 10;
                    for (let i = 0; i < numDebris; i++) {
                        const debrisMass = body.mass / 500 + Math.random() * (body.mass / 500);
                        const debrisVel = new THREE.Vector3(
                            (Math.random() - 0.5),
                            (Math.random() - 0.5),
                            (Math.random() - 0.5)
                        ).normalize().multiplyScalar(Math.random() * 20 + 10);
                        
                        const debris = new Body(
                            debrisMass,
                            body.px, body.py, body.pz,
                            body.vx + debrisVel.x, body.vy + debrisVel.y, body.vz + debrisVel.z,
                            '#4fA7f0' // Earth-like
                        );
                        bodies.push(debris);
                        scene.add(debris.mesh);
                        scene.add(debris.trail);
                    }
                    updateCameraFollowDropdown();
                }
                
                /**
                 * @brief Updates visual effects like explosions
                 */
                function updateVisualEffects(deltaTime) {
                    for (let i = visualEffects.length - 1; i >= 0; i--) {
                        const effect = visualEffects[i];
                        effect.scale.x *= (1 + deltaTime * 2);
                        effect.scale.y *= (1 + deltaTime * 2);
                        effect.scale.z *= (1 + deltaTime * 2);
                        effect.material.opacity -= deltaTime * 0.5;
                        
                        if (effect.material.opacity <= 0) {
                            scene.remove(effect);
                            effect.geometry.dispose();
                            effect.material.dispose();
                            visualEffects.splice(i, 1);
                        }
                    }
                }
                
                /**
                 * @brief Calculates system-wide properties (COM, Energy)
                 */
                function calculateSystemStats() {
                    let totalMass = 0;
                    let com_x = 0, com_y = 0, com_z = 0;
                    let com_vx = 0, com_vy = 0, com_vz = 0;
                    let kineticEnergy = 0;
                    let potentialEnergy = 0;
                    
                    for (const body of bodies) {
                        totalMass += body.mass;
                        
                        com_x += body.mass * body.px;
                        com_y += body.mass * body.py;
                        com_z += body.mass * body.pz;
                        
                        com_vx += body.mass * body.vx;
                        com_vy += body.mass * body.vy;
                        com_vz += body.mass * body.vz;
                        
                        const v_sq = body.vx * body.vx + body.vy * body.vy + body.vz * body.vz;
                        kineticEnergy += 0.5 * body.mass * v_sq;
                    }
                    
                    if (totalMass > 0) {
                        systemCOM.position.set(com_x / totalMass, com_y / totalMass, com_z / totalMass);
                        systemCOM.velocity.set(com_vx / totalMass, com_vy / totalMass, com_vz / totalMass);
                        systemCOM.totalMass = totalMass;
                    }

                    for (let i = 0; i < bodies.length - 1; i++) {
                        for (let j = i + 1; j < bodies.length; j++) {
                            const bodyI = bodies[i];
                            const bodyJ = bodies[j];
                            const dx = bodyJ.px - bodyI.px;
                            const dy = bodyJ.py - bodyI.py;
                            const dz = bodyJ.pz - bodyI.pz;
                            const r = Math.sqrt(dx * dx + dy * dy + dz * dz + EPSILON * EPSILON);
                            potentialEnergy -= (G * bodyI.mass * bodyJ.mass) / r;
                        }
                    }
                    
                    document.getElementById('kineticEnergy').textContent = kineticEnergy.toExponential(2);
                    document.getElementById('potentialEnergy').textContent = potentialEnergy.toExponential(2);
                    document.getElementById('totalEnergy').textContent = (kineticEnergy + potentialEnergy).toExponential(2);
                }
                
                /**
                 * @brief Updates camera position based on mouse controls.
                 */
                function updateCameraPosition() {
                    let targetPos = new THREE.Vector3(mouseControls.target.x, mouseControls.target.y, mouseControls.target.z);

                    if (cameraFollowId === 'com') {
                        targetPos.copy(systemCOM.position);
                    } else if (cameraFollowId !== 'none') {
                        const body = bodies.find(b => b.id === cameraFollowId);
                        if (body) {
                            targetPos.set(body.px, body.py, body.pz);
                        } else {
                            // Body was destroyed/merged
                            cameraFollowId = 'none';
                            updateCameraFollowDropdown();
                        }
                    }
                    
                    // Convert spherical-like coords to cartesian offset
                    const x = mouseControls.zoom * Math.sin(mouseControls.rotation.x) * Math.cos(mouseControls.rotation.y);
                    const z = mouseControls.zoom * Math.sin(mouseControls.rotation.x) * Math.sin(mouseControls.rotation.y);
                    const y = mouseControls.zoom * Math.cos(mouseControls.rotation.x);
                    
                    camera.position.set(targetPos.x + x, targetPos.y + y, targetPos.z + z);
                    camera.lookAt(targetPos);
                    mouseControls.target.copy(targetPos);
                }
                
                /**
                 * @brief Updates all UI info panels
                 */
                function updateUI() {
                    // Update main info display
                    document.getElementById('camCoords').textContent = `${camera.position.x.toFixed(1)}, ${camera.position.y.toFixed(1)}, ${camera.position.z.toFixed(1)}`;
                    document.getElementById('bodyCount').textContent = bodies.length;
                    document.getElementById('totalMass').textContent = systemCOM.totalMass.toExponential(2);
                    
                    // Update selection display
                    const selectionPanel = document.getElementById('selectionInfo');
                    if (selectedBody) {
                        selectionPanel.style.display = 'block';
                        document.getElementById('selectId').textContent = selectedBody.id;
                        document.getElementById('selectMass').textContent = selectedBody.mass.toExponential(2);
                        document.getElementById('selectPos').textContent = `${selectedBody.px.toFixed(1)}, ${selectedBody.py.toFixed(1)}, ${selectedBody.pz.toFixed(1)}`;
                        document.getElementById('selectVel').textContent = `${selectedBody.vx.toFixed(1)}, ${selectedBody.vy.toFixed(1)}, ${selectedBody.vz.toFixed(1)}`;
                        
                        const lifetimeEl = document.getElementById('selectLifetime');
                        if (selectedBody.lifetime > 0) {
                            lifetimeEl.textContent = `Lifetime: ${selectedBody.age.toFixed(1)} / ${selectedBody.lifetime.toFixed(0)}s`;
                        } else {
                            lifetimeEl.textContent = '';
                        }
                        
                        // Update selection outline
                        selectionOutline.position.set(selectedBody.px, selectedBody.py, selectedBody.pz);
                        const scale = selectedBody.visualRadius * 1.2;
                        selectionOutline.scale.set(scale, scale, scale);
                        selectionOutline.visible = true;
                    } else {
                        selectionPanel.style.display = 'none';
                        selectionOutline.visible = false;
                    }
                }
                
                /**
                 * @brief Updates the "Follow Body" dropdown list
                 */
                function updateCameraFollowDropdown() {
                    const select = document.getElementById('cameraFollowSelect');
                    const currentVal = cameraFollowId;
                    select.innerHTML = '<option value="none">None (Free Look)</option><option value="com">Center of Mass (COM)</option>';
                    
                    bodies.sort((a, b) => b.mass - a.mass); // Sort by mass
                    
                    bodies.forEach(body => {
                        const name = `Body ${body.id} (M: ${body.mass.toExponential(1)})`;
                        const option = document.createElement('option');
                        option.value = body.id;
                        option.textContent = name;
                        if (body.id === currentVal) {
                            option.selected = true;
                        }
                        select.appendChild(option);
                    });
                }
                
                /**
                 * @brief Resets camera to default view
                 */
                function resetView() {
                    mouseControls.rotation = { x: Math.PI / 3, y: -Math.PI / 4 };
                    mouseControls.target.set(0, 0, 0);
                    cameraFollowId = 'none';
                    // Find zoom from scenario
                    const scenarioData = {
                        'empty': 50, 'sun_planets': 50, 'binary_planet': 70, 
                        'figure_eight': 5, 'ejection': 60, 'lagrange_L4': 30,
                        'ring_system': 80, 'galaxy_collision': 200
                    };
                    mouseControls.zoom = scenarioData[scenario] || 50;
                    
                    updateCameraPosition();
                    updateCameraFollowDropdown();
                }

                /**
                 * @brief The main animation loop.
                 */
                function animate() {
                    animationId = requestAnimationFrame(animate);
                    const deltaTime = clock.getDelta();

                    // Run physics simulation steps
                    for (let i = 0; i < stepsPerFrame; i++) {
                        calculate_accelerations();
                        handleCollisions();
                        update_bodies(DT); // Pass physics timestep
                    }
                    
                    // Update non-physics things once per frame
                    calculateSystemStats();
                    updateVisualEffects(deltaTime);
                    
                    // Update light position (if first body is a star)
                    const star = bodies.find(b => b.isStar);
                    if (star) {
                        sunLight.position.set(star.px, star.py, star.pz);
                    } else if (bodies.length > 0) {
                        // find most massive body
                        const mostMassive = bodies.reduce((a, b) => a.mass > b.mass ? a : b);
                        sunLight.position.set(mostMassive.px, mostMassive.py, mostMassive.pz);
                    }
                    
                    // Update camera
                    updateCameraPosition();
                    
                    // Render the scene
                    composer.render(deltaTime);
                    
                    // Update UI
                    updateUI();
                }
                
                // --- Event Listeners Setup ---
                function setupEventListeners() {
                    // --- Sim Controls ---
                    document.getElementById('startButton').addEventListener('click', () => {
                        if (!animationId) {
                            clock.start();
                            animate();
                        }
                    });
                    
                    document.getElementById('stopButton').addEventListener('click', () => {
                        if (animationId) {
                            cancelAnimationFrame(animationId);
                            animationId = null;
                            clock.stop();
                        }
                    });
                    
                    document.getElementById('resetButton').addEventListener('click', () => {
                        if (animationId) {
                            cancelAnimationFrame(animationId);
                            animationId = null;
                        }
                        initialize_bodies();
                        composer.render(); // Render one frame
                    });
                    
                    document.getElementById('clearAllButton').addEventListener('click', () => {
                        if (animationId) {
                            cancelAnimationFrame(animationId);
                            animationId = null;
                        }
                        clearAllBodies();
                        resetView();
                        composer.render();
                    });

                    // --- Speed Controls ---
                    document.getElementById('normalSpeedButton').addEventListener('click', () => {
                        stepsPerFrame = 10;
                        document.getElementById('normalSpeedButton').classList.add('active');
                        document.getElementById('fastForwardButton').classList.remove('active');
                    });
                    
                    document.getElementById('fastForwardButton').addEventListener('click', () => {
                        stepsPerFrame = 40; // 4x speed
                        document.getElementById('fastForwardButton').classList.add('active');
                        document.getElementById('normalSpeedButton').classList.remove('active');
                    });
                    
                    // --- Camera Controls ---
                    document.getElementById('cameraFollowSelect').addEventListener('change', (e) => {
                        cameraFollowId = e.target.value === 'none' ? 'none' : e.target.value === 'com' ? 'com' : parseInt(e.target.value);
                        if (cameraFollowId === 'none') {
                            mouseControls.target.set(0, 0, 0);
                        }
                    });
                    document.getElementById('resetViewButton').addEventListener('click', resetView);
                    document.getElementById('zeroComVelButton').addEventListener('click', () => {
                        const comv = systemCOM.velocity;
                        bodies.forEach(body => {
                            body.vx -= comv.x;
                            body.vy -= comv.y;
                            body.vz -= comv.z;
                        });
                    });
                    
                    // --- Graphics Controls ---
                    document.getElementById('toggleTrailsButton').addEventListener('click', (e) => {
                        const visible = !e.target.classList.contains('active');
                        e.target.classList.toggle('active');
                        e.target.textContent = `Trails: ${visible ? 'ON' : 'OFF'}`;
                        bodies.forEach(body => body.trail.visible = visible);
                    });
                    document.getElementById('toggleBloomButton').addEventListener('click', (e) => {
                        const enabled = !e.target.classList.contains('active');
                        e.target.classList.toggle('active');
                        e.target.textContent = `Bloom: ${enabled ? 'ON' : 'OFF'}`;
                        bloomPass.enabled = enabled;
                    });

                    // --- Scenario & Physics Controls ---
                    document.getElementById('scenarioSelect').addEventListener('change', (e) => {
                        scenario = e.target.value;
                        if (animationId) cancelAnimationFrame(animationId);
                        animationId = null;
                        initialize_bodies();
                        composer.render();
                    });
                    
                    document.getElementById('collisionSelect').addEventListener('change', (e) => {
                        collisionMode = e.target.value;
                    });
                    
                    // --- Spawn Menu Logic ---
                    document.getElementById('spawnTypeSelect').addEventListener('change', (e) => {
                        document.getElementById('customSpawnParams').style.display = (e.target.value === 'custom') ? 'block' : 'none';
                    });
                    
                    document.getElementById('spawnAtOriginButton').addEventListener('click', () => {
                        spawnMode = 'origin';
                        document.getElementById('spawnAtOriginButton').classList.add('active');
                        document.getElementById('spawnWithVelButton').classList.remove('active');
                        spawnBody();
                    });

                    document.getElementById('spawnWithVelButton').addEventListener('click', () => {
                        spawnMode = 'drag';
                        document.getElementById('spawnWithVelButton').classList.add('active');
                        document.getElementById('spawnAtOriginButton').classList.remove('active');
                    });
                    
                    // --- Panel Toggle ---
                    document.getElementById('controls-toggle').addEventListener('click', () => {
                        const content = document.getElementById('controls-content');
                        const panel = document.getElementById('controls');
                        if (content.style.display === 'none') {
                            content.style.display = 'block';
                            panel.style.width = '300px';
                        } else {
                            content.style.display = 'none';
                            panel.style.width = 'auto';
                        }
                    });

                    // --- 3D Mouse Controls (Rotation, Pan, Zoom, Click) ---
                    canvas.addEventListener('wheel', (e) => {
                        e.preventDefault();
                        mouseControls.zoom += e.deltaY * 0.05;
                        mouseControls.zoom = Math.max(2, mouseControls.zoom);
                        if (!animationId) {
                            updateCameraPosition();
                            composer.render();
                        }
                    });

                    canvas.addEventListener('mousedown', (e) => {
                        e.preventDefault();
                        
                        mouse.x = (e.clientX / window.innerWidth) * 2 - 1;
                        mouse.y = -(e.clientY / window.innerHeight) * 2 + 1;
                        raycaster.setFromCamera(mouse, camera);

                        if (e.button === 0) { // Left click
                            if (spawnMode === 'drag') {
                                const intersect = new THREE.Vector3();
                                raycaster.ray.intersectPlane(plane, intersect);
                                if (intersect) {
                                    isSpawning = true;
                                    spawnStartPosition.copy(intersect);
                                    velocityGizmo.geometry.setFromPoints([spawnStartPosition, spawnStartPosition]);
                                    velocityGizmo.visible = true;
                                }
                            } else {
                                mouseControls.dragging = true;
                            }
                        } else if (e.button === 2) { // Right click
                            mouseControls.panning = true;
                        }
                        mouseControls.lastMouse = { x: e.clientX, y: e.clientY };
                        canvas.style.cursor = 'grabbing';
                    });
                    
                    canvas.addEventListener('mousemove', (e) => {
                        e.preventDefault();
                        const dx = e.clientX - mouseControls.lastMouse.x;
                        const dy = e.clientY - mouseControls.lastMouse.y;
                        
                        mouse.x = (e.clientX / window.innerWidth) * 2 - 1;
                        mouse.y = -(e.clientY / window.innerHeight) * 2 + 1;
                        raycaster.setFromCamera(mouse, camera);
                        
                        if (isSpawning) {
                            const intersect = new THREE.Vector3();
                            raycaster.ray.intersectPlane(plane, intersect);
                            if (intersect) {
                                velocityGizmo.geometry.setFromPoints([spawnStartPosition, intersect]);
                                velocityGizmo.geometry.attributes.position.needsUpdate = true;
                            }
                        }
                        else if (mouseControls.dragging) {
                            mouseControls.rotation.y += dx * 0.005;
                            mouseControls.rotation.x += dy * 0.005;
                            mouseControls.rotation.x = Math.max(0.1, Math.min(Math.PI - 0.1, mouseControls.rotation.x));
                        }
                        else if (mouseControls.panning) {
                            const v_fov = camera.fov * Math.PI / 180;
                            const h = 2 * Math.tan(v_fov / 2) * mouseControls.zoom;
                            const w = h * camera.aspect;
                            
                            const right = new THREE.Vector3().crossVectors(camera.up, camera.position.clone().sub(mouseControls.target).normalize()).normalize();
                            const up = new THREE.Vector3().crossVectors(camera.position.clone().sub(mouseControls.target).normalize(), right).normalize();

                            mouseControls.target.add(right.multiplyScalar(-dx * w / window.innerWidth));
                            mouseControls.target.add(up.multiplyScalar(dy * h / window.innerHeight));
                        }
                        
                        mouseControls.lastMouse = { x: e.clientX, y: e.clientY };
                        
                        if (!animationId) {
                            updateCameraPosition();
                            composer.render();
                        }
                    });
                    
                    canvas.addEventListener('mouseup', (e) => {
                        e.preventDefault();
                        
                        if (isSpawning) { // End of a spawn-drag
                            isSpawning = false;
                            velocityGizmo.visible = false;
                            
                            const intersect = new THREE.Vector3();
                            raycaster.ray.intersectPlane(plane, intersect);
                            if (intersect) {
                                const velocity = intersect.clone().sub(spawnStartPosition).multiplyScalar(0.5); // Scale velocity
                                spawnBody(spawnStartPosition, velocity);
                            }
                        }
                        else if (e.button === 0 && !mouseControls.dragging) { // A simple click
                            handleLeftClick(e);
                        }
                        
                        mouseControls.dragging = false;
                        mouseControls.panning = false;
                        canvas.style.cursor = 'grab';
                    });
                    
                    canvas.addEventListener('mouseleave', () => {
                        mouseControls.dragging = false;
                        mouseControls.panning = false;
                        isSpawning = false;
                        velocityGizmo.visible = false;
                        canvas.style.cursor = 'grab';
                    });
                    
                    // Prevent context menu on right-click
                    canvas.addEventListener('contextmenu', (e) => e.preventDefault());

                    // --- Window Resize ---
                    window.addEventListener('resize', () => {
                        camera.aspect = window.innerWidth / window.innerHeight;
                        camera.updateProjectionMatrix();
                        renderer.setSize(window.innerWidth, window.innerHeight);
                        composer.setSize(window.innerWidth, window.innerHeight);
                        if (!animationId) composer.render();
                    });
                }
                
                /**
                 * @brief Spawns a new body based on UI settings
                 */
                function spawnBody(position = null, velocity = null) {
                    const spawnType = document.getElementById('spawnTypeSelect').value;
                    let newBody;
                    let pos = position ? position : new THREE.Vector3(0, 0, 0);
                    let vel = velocity ? velocity : new THREE.Vector3(0, 0, 0);

                    switch(spawnType) {
                        case 'earth':
                            newBody = new Body(1.0, pos.x, pos.y, pos.z, vel.x, vel.y, vel.z, '#4fA7f0');
                            break;
                        case 'neutron_star':
                            newBody = new Body(4000.0, pos.x, pos.y, pos.z, vel.x, vel.y, vel.z, '#e0e0ff', true);
                            break;
                        case 'giant_star':
                            newBody = new Body(8000.0, pos.x, pos.y, pos.z, vel.x, vel.y, vel.z, '#f97316', true, SUPERNOVA_LIFETIME);
                            break;
                        case 'black_hole':
                            newBody = new Body(20000.0, pos.x, pos.y, pos.z, vel.x, vel.y, vel.z, '#000000');
                            break;
                        case 'custom':
                            const mass = parseFloat(document.getElementById('customMass').value);
                            const px = position ? pos.x : parseFloat(document.getElementById('customPx').value);
                            const py = position ? pos.y : parseFloat(document.getElementById('customPy').value);
                            const pz = position ? pos.z : parseFloat(document.getElementById('customPz').value);
                            const vx = velocity ? vel.x : parseFloat(document.getElementById('customVx').value);
                            const vy = velocity ? vel.y : parseFloat(document.getElementById('customVy').value);
                            const vz = velocity ? vel.z : parseFloat(document.getElementById('customVz').value);
                            newBody = new Body(mass, px, py, pz, vx, vy, vz, `#${Math.floor(Math.random()*16777215).toString(16)}`);
                            break;
                    }

                    if (newBody) {
                        bodies.push(newBody);
                        scene.add(newBody.mesh);
                        scene.add(newBody.trail);
                        updateCameraFollowDropdown();
                        if (!animationId) calculateSystemStats(); // Update stats if paused
                    }
                }
                
                /**
                 * @brief Handles left-click for selection
                 */
                function handleLeftClick(e) {
                    // This function is now only for selection, spawning is on mouseup
                    raycaster.setFromCamera(mouse, camera);
                    const intersects = raycaster.intersectObjects(bodies.map(b => b.mesh));
                    if (intersects.length > 0) {
                        const bodyId = intersects[0].object.userData.bodyId;
                        selectedBody = bodies.find(b => b.id === bodyId) || null;
                    } else {
                        selectedBody = null; // Clicked empty space
                    }
                    updateUI();
                }
                
                // --- Start Everything ---
                init();
            });
        }
    </script>
</body>
</html>
