# 行動解析 Transformer

## DeepHLについて

DeepHL（Deep Highlighting）は、動物の軌跡データにおいて意味のある部分を自動的に特定・分析する深層学習ベースのシステムです。このシステムは、アテンション機構を使用して2つのグループ間の違いを特徴づける軌跡の部分を自動的にハイライトし、研究者が新しい行動パターンを発見することを支援します。

## プロジェクト概要

このリポジトリは、DeepLabCutで取得したマウスの軌跡データを解析するTransformerベースのニューラルネットワークを提供します。DeepHLと同様に、以下の機能を備えています：

* 行動の重要なセグメントを自動的に特定
* 行動学的に重要なパターンをハイライト
* 研究者に注目すべき行動を提示
* 行動の違いを解釈可能な形で可視化

## 主な機能

### データ処理

- DeepLabCutの出力座標データの読み込み
- 以下の基本的な移動特徴量の計算：
  - 速度
  - 角速度
  - 開始位置からの距離
  - 移動パターン
- Transformerモデル用のシーケンス準備

### Transformerモデル

```python
class TransformerModel:
    - マルチヘッドアテンション機構
    - 時間情報のための位置エンコーディング
    - レイヤー単位のアテンション機構
    - 行動分析用の分類ヘッド
```

### 可視化機能

* アテンションの重みに基づく軌跡のハイライト
* 重要な行動セグメントのインタラクティブな可視化
* 手作業で設計した特徴量との相関分析
![image](https://github.com/user-attachments/assets/825c9ee4-926d-49e2-b0ff-4955de5dcc1c)
![image](https://github.com/user-attachments/assets/a0ac3148-615c-45ea-889f-87a17af29981)


## 使用方法

```python
from mouse_analyzer import MouseTrajectoryDataset, TransformerModel

# データの読み込み
dataset = MouseTrajectoryDataset("dlc_output.csv")

# モデルの初期化
model = TransformerModel(
    input_dim=dataset.features.shape[1],
    d_model=128,
    nhead=8,
    num_layers=4
)

# モデルの訓練
history = train_model(model, dataset)

# 結果の可視化
visualize_results(dataset, model)
```

## 必要環境

* Python 3.7+
* PyTorch 1.7+
* pandas
* numpy
* matplotlib
* seaborn

## 解析の流れ

1. DeepLabCutで取得した座標データを読み込み
2. 基本的な行動特徴量を計算
3. Transformerモデルで重要なセグメントを特定
4. アテンション機構を用いて注目すべき部分をハイライト
5. 結果の可視化と解釈

## 参考文献

- DeepHL: Deep learning-assisted comparative analysis of animal trajectories with DeepHL (Nature Communications, 2020)
- DeepLabCut: Markerless pose estimation of user-defined body parts with deep learning





