<script setup>
import { ref, onMounted } from 'vue'
import * as THREE from "three"

const myCanvas = ref(null)

onMounted(() => {
  // レンダラーを作成
  const renderer = new THREE.WebGLRenderer({
    canvas: myCanvas.value,
  })
  renderer.setPixelRatio(window.devicePixelRatio)

  // 画面全体にサイズを設定
  function resizeRenderer() {
    const width = window.innerWidth
    const height = window.innerHeight
    renderer.setSize(width, height)
  }

  // 初期サイズ設定
  resizeRenderer()

  // シーンを作成
  const scene = new THREE.Scene()

  // カメラを作成
  const camera = new THREE.PerspectiveCamera(45, window.innerWidth / window.innerHeight)
  camera.position.set(0, 0, +1000)

  // 箱を作成
  const geometry = new THREE.BoxGeometry(400, 400, 400)
  const material = new THREE.MeshNormalMaterial()
  const box = new THREE.Mesh(geometry, material)
  scene.add(box)

  // 毎フレーム時に実行されるループイベントです
  function tick () {
    box.rotation.y += 0.01
    renderer.render(scene, camera) // レンダリング
    requestAnimationFrame(tick)
  }

  // リサイズイベントを処理
  window.addEventListener('resize', () => {
    // 画面リサイズ時にレンダラーのサイズとカメラのアスペクト比を更新
    resizeRenderer()
    camera.aspect = window.innerWidth / window.innerHeight
    camera.updateProjectionMatrix()
  })

  tick()
})
</script>

<template>
  <h2>step2：四角形回転（画面全体）</h2>
  <canvas ref="myCanvas"></canvas>
</template>
