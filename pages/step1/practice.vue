<script setup>
import { ref, onMounted } from 'vue'
import * as THREE from "three"

const myCanvas = ref(null)
const width = 960
const height = 540

onMounted(() => {
  // レンダラーを宣言する
  const renderer = new THREE.WebGLRenderer({
    canvas: myCanvas.value
  })
  // ディスプレイのピクセル値に応じた描画の荒さを指定
  renderer.setPixelRatio(window.devicePixelRatio)
  // キャンバス要素領域のサイズを指定
  renderer.setSize(width, height)
  
  // シーンを作成
  const scene = new THREE.Scene()
  // 背景をピンクにしてみた
  scene.background = new THREE.Color('lightpink')
  
  // カメラを用意
  const camera = new THREE.PerspectiveCamera(45, width/height)
  camera.position.set(0,0,+1500)
  
  // 四角形の箱を作成
  const geometry = new THREE.BoxGeometry(300,500,1000)
  const material = new THREE.MeshNormalMaterial()
  const box = new THREE.Mesh(geometry, material)
  scene.add(box)

  // 毎フレーム時に実行されるループイベントです
  function tick () {
    box.rotation.y += 0.01
    renderer.render(scene, camera) // レンダリング

    requestAnimationFrame(tick)
  }

  tick()
})
</script>

<template>
  <h2>練習：：step1：四角形回転（サイズ指定）</h2>
  <canvas ref="myCanvas"></canvas>
</template>
