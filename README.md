# zebramask
Leaflet zebra mask from GSI DEM

# Demo
<http://frogcat.github.io/zebramask/#12/35.2661/138.8284>

# Note
こんな手順で実現。

1. Leaflet 0.73 TileLayer の loadtile イベントをトリガーにして、国土地理院標高タイルを取りにいく
2. 取得した 256x256 データをスキャンして、動的に生成した256x256 キャンバスに書き込み
3. キャンバスを toDataURL して PNG マスク画像 URL を作成
4. タイルの HTML Element に対して -webkit-mask-image をセットすることでマスクをかける

手順2で標高に応じて Fill Color の透明度を変更することで、マスク形状をコントロールできる。
ストライプ状にしたり、最大値・最小値でカットオフしたりするなど。

