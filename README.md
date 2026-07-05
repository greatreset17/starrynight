# 🌌 Starry Night: The Painted Universe (3D Procedural WebGL Experience)

フィンセント・ファン・ゴッホの名作『星月夜（The Starry Night）』のビジョンを極限まで高解像度に言語化し、AIとの「ビジョンからの逆算型インバース・デザイン」によって生み出された、自己完結型の無限3D WebGLアート体験です。

外部のアセット（画像や3Dモデル）は一切使用せず、たった1枚の `index.html`（約39 KB）の中に、最大16万個の立体的な筆跡（インパスト・リボン）をリアルタイムに制御する数理流体ロジックとシェーダーコードが完全に組み込まれています。

**🚀 Live Demo:** [https://greatreset17.github.io/starrynight/](https://greatreset17.github.io/starrynight/)

---

## 🎨 主な機能と体験（Features）

*   **Flat-to-3D Reveal (平面から立体への覚醒):**
    起動時の最初の1フレームは、原作の絵画『星月夜』とミリ単位で構図（11個の星、三日月、二重螺旋の渦、糸杉、サン＝レミの村）が完全に一致します。マウスを動かした瞬間に、3D空間に配置された筆跡のレイヤーが視差効果（パララックス）を伴って牙をむくように滑り出し、圧倒的な奥行きが顔を出します。
*   **Living Paint (生きている絵の具の流体シミュレーション):**
    空を構成する数万〜十数万のインパスト・リボンは、2つの巨大な逆回転渦、星ごとの攪拌（かくはん）渦、そしてカールノイズ（Curl Noise）を組み合わせた高度なベクトル場（Flow Field）をリアルタイムに流動しています。
*   **Infinite Flight (無限の飛行):**
    キーボードの `WASD` またはマウスホイールで、ゴッホの脳内宇宙を無限に飛行できます。カメラの進行方向に応じて新しいストロークの深度シェルがプロシージャルに自動生成され続けるため、この旅に終わりはありません。
*   **Cinematic Presets & Interactive UI (インタラクティブ制御):**
    マウスを動かすとスマートな制御UIがフェードインし、空のうねりの激しさを「becalmed（静穏）」「van gogh（本来のうねり）」「storm（嵐）」へとリアルタイムに変更可能。また、村の屋根、月の真横、巨大な螺旋の核心部などを巡る美しいカメラプリセットも内蔵しています。

---

## 🛠️ 技術スタックとアーキテクチャ（Technical Architecture）

*   **Core Engine:** Three.js 0.160.0 (pinned via Import Map)
*   **Architecture:** 完全単一ファイル構成 (`index.html` のみ、約39 KB)
*   **Rendering Technique:** `THREE.InstancedMesh` + カスタムGLSLシェーダーによるGPU駆動描画

### 1. 数理流体ロジック（Mathematical Flow Field）
空のダイナミックな流動は、CPUでの物理演算ではなく、頂点シェーダー内での数学的ベクトル合成によって処理されています。
