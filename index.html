<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <title>Simulação 3D - Mapa de Calor e Piso Piezoelétrico</title>
  <style>
    body { margin: 0; overflow: hidden; font-family: sans-serif; }
    #info {
      position: absolute; top: 10px; left: 10px; color: white;
      background: rgba(0,0,0,0.7); padding: 10px; border-radius: 5px;
    }
  </style>
</head>
<body>
  <div id="info">
    <h3>Monitoramento de Fluxo Urbano</h3>
    <p>Simulação de pedestres em setores</p>
    <p>Status Setor Central: <b id="status" style="color: green;">Baixo Fluxo</b></p>
  </div>

  <!-- Bibliotecas 3D e Mapa de Calor via CDN -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>

  <script>
    // 1. Configuração da Cena e Câmera
    const scene = new THREE.Scene();
    scene.background = new THREE.Color(0x1a1a1a);

    const camera = new THREE.PerspectiveCamera(60, window.innerWidth / window.innerHeight, 0.1, 1000);
    camera.position.set(0, 12, 12);
    camera.lookAt(0, 0, 0);

    const renderer = new THREE.WebGLRenderer({ antialias: true });
    renderer.setSize(window.innerWidth, window.innerHeight);
    document.body.appendChild(renderer.domElement);

    // 2. Criar o Piso dividido em Setores
    const geometry = new THREE.PlaneGeometry(10, 10);
    const materialPiso = new THREE.MeshBasicMaterial({ color: 0x00ff00, side: THREE.DoubleSide });
    const piso = new THREE.Mesh(geometry, materialPiso);
    piso.rotation.x = Math.PI / 2;
    scene.add(piso);

    // Grid para visualização dos setores
    const grid = new THREE.GridHelper(10, 10);
    scene.add(grid);

    // 3. Criar os Pedestres (Agentes)
    const pedestres = [];
    const numeroPedestres = 5;

    for (let i = 0; i < numeroPedestres; i++) {
      const pGeo = new THREE.SphereGeometry(0.3, 16, 16);
      const pMat = new THREE.MeshBasicMaterial({ color: 0xffffff });
      const pedestre = new THREE.Mesh(pGeo, pMat);
      
      pedestre.position.set(
        (Math.random() - 0.5) * 8,
        0.3,
        (Math.random() - 0.5) * 8
      );
      
      scene.add(pedestre);
      pedestres.push({
        mesh: pedestre,
        dx: (Math.random() - 0.5) * 0.08,
        dz: (Math.random() - 0.5) * 0.08
      });
    }

    let contadorPassosCentral = 0;

    // 4. Loop de Animação e Lógica do Mapa de Calor
    function animate() {
      requestAnimationFrame(animate);

      pedestres.forEach(p => {
        p.mesh.position.x += p.dx;
        p.mesh.position.z += p.dz;

        // Rebater nas bordas
        if (Math.abs(p.mesh.position.x) > 4.5) p.dx *= -1;
        if (Math.abs(p.mesh.position.z) > 4.5) p.dz *= -1;

        // Checar se passou pelo Setor Central (Área de alta relevância)
        if (Math.abs(p.mesh.position.x) < 2 && Math.abs(p.mesh.position.z) < 2) {
          contadorPassosCentral++;
        }
      });

      // Atualizar cor do piso de acordo com o acúmulo de tráfego
      const statusEl = document.getElementById("status");
      if (contadorPassosCentral > 300) {
        materialPiso.color.setHex(0xff0000); // Vermelho: Recomendado para Piso Piezoelétrico
        statusEl.innerText = "ALTO FLUXO (Ideal para Piso Piezoelétrico)";
        statusEl.style.color = "red";
      } else if (contadorPassosCentral > 100) {
        materialPiso.color.setHex(0xffff00); // Amarelo: Fluxo Médio
        statusEl.innerText = "Médio Fluxo";
        statusEl.style.color = "yellow";
      }

      renderer.render(scene, camera);
    }

    animate();
  </script>
</body>
</html>
