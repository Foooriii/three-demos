<script setup>

</script>

<template>
  <h1>ThreeJS チートシート</h1>

  <h2>参考記事</h2>
  <ul>
    <li><a href="https://ics.media/tutorial-three/quickstart/" target="_blank">簡単なThree.jsのサンプルを試そう - ICS MEDIA</a></li>
    <li><a href="https://coosy.co.jp/blog/3dmodel-threejs/" target="_blank">Three.jsの使い方！3DモデルをWeb上で表示させる8ステップ</a></li>
  </ul>
  
  <hr>
  <h2>各用語集</h2>
  <p>
    <strong>レンダラー</strong><br>
    ・WebGLのレンダリングをするためのもの。THREE.WebGLRendererで宣言して、中にはサイトに表示するDOMを指定する。<br>
    ・THREE.WebGLRenderer() は Three.js のレンダラーオブジェクトを作成します。Three.jsでは、WebGLというブラウザのAPIを使用して3Dグラフィックスを描画します。このレンダラーは、WebGLを利用して描画を行うためのエンジンをセットアップしています。<br>
    ・renderer.setPixelRatio(window.devicePixelRatio)<br>
      ・setPixelRatio() は、ディスプレイのピクセル比に応じた描画の品質を調整するメソッドです。<br>
    　  ・例えば、devicePixelRatio が2の場合、1つのCSSピクセルに2×2の物理ピクセルが使われるため、より細かい表示が必要です。<br>
    　  ・このメソッドを使わないと、通常のディスプレイでは問題ないですが、Retinaディスプレイなどでは画質が粗くなってしまうことがあります。<br>
    ・renderer.setSize(width, height)<br>
    　・setSize() メソッドは、キャンバスの描画領域のサイズを設定します。<br>
    　　・width や height がウィンドウのサイズに応じて変化する場合、ウィンドウのリサイズイベントに応じて renderer.setSize() を再実行することが必要です。
  </p>
</template>

<style scoped>

</style>