# Kustomizationでマニフェストの一部を変更する

## フォルダ構成

- base
    - 変更のベースとなるマニフェストの保存場所
- overlays/dev
    - 開発環境用の設定に上書きするための設定の保存場所
- overlays/prod
    - 商用環境用の設定に上書きするための設定の保存場所

## コマンド

- Dryrun
    - `kubectl kustomize overlays/dev`
- Apply
    - `kubectl apply -k overlays/dev`