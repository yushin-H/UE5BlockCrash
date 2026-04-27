# 開発ログ
## 2026/04/27
### Added
- `Maps\`
    - `Stages\`
        - `Stage_1\`
            - `Stage_1_GrayBox`ステージのフォルダを追加し、ブロック用サブレベルを作成
- `Content\`
    - `UI\`
        - `WBP_StageButton`ステージセレクト用ボタン作成
        - `WBP_StageSelect`GIのUnlockedStageLevelを参照してステージレベルを生成
### Cahnged
- `Content\`
    - `UI\`
        - `WBP_ResultMenu`セレクトボタンでステージセレクトUIを呼び出す機能追加
    - `Blueprint\`
        - `Environment\`
            - `BP_BlockBase`物理シミュレーションをデフォルトに

---

## 2026/04/26
### Added
- `Blueprint\`
    - `Data\`スキルツリー用データ管理タブ
        - `S_SkillTree`スキルツリーのデータテーブル(DT)の行構造体{Value\UpgradeCost}
        - `DT_NB_MaxAmmo`通常弾(NormalBullet)の最大弾数DT
        - `DT_NB_Speed`NBの初期速度DT
        - `DT_NB_Weight`NBの重さDT
    - `System\`
        - `GI_Parameter`スキルツリーの各ノードのレベル、装備された弾の種類、を保持するゲームインスタンス
### Changed
- `Blueprint\`
    - `Projectile\`
        - `BP_NormalBullet`初期速度、重さのパラメータを`GI_Parameter`から取得するように変更
    - `System\`
        - `BP_PlayerPawn`最大弾数と装備された弾の種類を`GI_Parameter`から取得するように変更
### Removed
- `Blueprint\`
    - `Projectile\`
        - `DA_ProjectileConfig_Base`DTでスキルツリーで操作するパラメータの種類を拡張できるようにするため、DAは削除
        - `DA_NormalBullet`同上

---

## 2026/04/25
### Added
- `UI\WBP_ResultMenu`でクリア画面の作成
- `BP_Projectile_Base`として発射物の親コンポーネントを作成
- `BP_NormalBullet`として通常弾を作成
- `DA_ProjectileConfig_Base`で発射物のデータアセットの種類を作成
- `DA_NormalBullet`の初期パラメータを作成
- `BP_PlayerPawn`で発射物の数の現在数を管理
- `BP_PlayerPawn`と`BP_StageManager`で失敗判定を追加
### Changed
### Fixed
- `UI\WBP_CrossHair`のバグ修正、カーソル追従機能を`BP_PlayerPawn`に移動

---

## 2026/04/24
- `Maps\Shared\L_Environment_Base`
→`BP_KillZonevolume`や`BP_StageManager`やLighting関連が配置されている
全ステージのベースになるサブレベル

---

## 2026/04/23
**Blueprints**
- `BP_FloorBase`
- `BP_BlockBase` — 床上ブロック(積み木)の親クラス/メッシュ・マテリアル変更可能
- `BP_KillZoneVolume` — 6面コリジョンケージ作成
- `BP_StageManager` — ブロック残数管理・二重判定防止・クリア判定
- `BPI_GameRules` — BP間のイベント通信

---

## 2026/04/22
**Blueprints**
- `BP_Projection`

**Input**
- `IA_Fire`
- `IA_Mouse`

- クロスヘアのマウス追従
- 左クリックでクロスヘアから弾を発射

---

## 2026/04/21
- UE5.7 空の C++ プロジェクト作成

**Blueprints**
- `BP_GameMode`
- `BP_PlayerPawn`

**Input**
- `IA_Move`
- `IMC_Default`


- WASD で天球上をカメラが移動