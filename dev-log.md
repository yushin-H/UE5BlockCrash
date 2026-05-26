# 開発ログ
## 2026/05/26
### Changed
- `Blueprints/`
    - `Environment/`
       - `BP_KillZoneVolume`弾が触れたらFireComponentにBPIを送る
    - `Projectile/`
        - `BP_NormalBullet`StaticMeshComponentの重さ、初速の初期化機能を追加
        - `BP_Projectile_Base`すべてPhysics Simulationで動かすために、Sphere Collisionと発射物コンポーネントを削除
    - `System/`
        - `Player/`
            - `BP_FireComponent`弾生成時にカメラの向きを発射物に送る/すべての弾が消えたらStageManagerにBPIを送る
            - `BP_SkillComponent`パラメータ参照用関数のバグを修正
        - `Interface/`
            - `BPI_GameEvent`OnProjectileFallenを追加
        - `Manager/`
            - `BP_StageManager`手元の弾がなくなって5秒後にブロックの静止判定をする機能を追加
    - `Data/`
        - `DT_SkillTree`パラメータ調整
        - `S_SkillTreeLevels`UpgradeCostの型をintに変更
    - `UI/`
        - `Widget/`
            - `WBP_SkillNode`レベルアップ可・不可・MAXでノードの色を変える機能を追加

---

## 2026/05/21
### Add
- `Blueprints/`
    - `UI/`
        - `Widget/`
            - `WBP_TreeLines`SkillNode間に線を引く
### Changed
- `Blueprints/`
    - `UI/`
        - `Widget/`
            - `WBP_SkillNode`TreeLinesにノードサイズを渡す用の参照を送る
            - `WBP_SkillTree`TreeLinesにノードのインデックスを渡す用の参照を送る

---

## 2026/05/20
### Changed
- `Blueprints/`
    - `UI/`
        - `Widget/`
            - `WBP_SkillNode`PrerequisiteIDで表示するスキルの表示切替機能追加
            - `WBP_SkillTree`スキル習得後にUIを更新するイベントディスパッチャーを追加
### Deleted
- `Blueprints/`
    - `Data/`
        - `DT_NB_MaxAmmo`
        - `DT_NB_Speed`
        - `DT_NB_Weight`DT_SkillTreeに統合する前のDTを削除

---

## 2026/05/18
### Changed
- `Blueprints/`
    - `System/`
        - `Interface/`
            - `BPI_UIMessage`UpdateSkillTreeParameterを追加
        - `Manager/`
            - `BP_CoinManager`SpendCoins関数でスキルツリーにBPIでUI更新イベントを送る
    - `UI/`
        - `Widget/`
            - `WBP_SkillNode`ノード強化時にパラメーターUI変更イベントを送る
            - `WBP_SkillTree`パラメータUIを追加

---

## 2026/05/16
### Changed
- `Blueprints/`
    - `UI/`
        - `Widget/`
            - `WBP_SkillTree`ステージセレクト画面に遷移するボタンを追加
            - `WBP_StageSelect`スキルツリー画面に遷移するボタンを追加

---

## 2026/05/15
### Changed
- `Blueprints/`
    - `Data/`
         - `DT_SkillTree`DT内にテスト用のデータを追加
         - `S_SkillTree`SkillID関連をname型から列挙型に変更
    - `System/`
        - `BPFL_SkillTree`SkillID関連をname型から列挙型に変更
        - `GI_Parameter`SkillID関連をname型から列挙型に変更
        - `Player/`
            - `BP_SkillComponent`SkillID関連をname型から列挙型に変更
    - `UI/`
        - `Widget/`
            - `WBP_SkillNode`SkillID関連をname型から列挙型に変更
            - `WBP_SkillTree`列挙型を用い、ノードの解放条件をもとにノードを木構造で並べる機能追加

---

## 2026/05/14
### Changed
- `Blueprints/`
    - `UI/`
        - `Widget/`
            - `WBP_SkillTree`背景、マウスでドラッグできる機能を追加

---

## 2026/05/11
### Changed
- `Blueprints/`
    - `System/`
        - `BPFL_SkillTree`スキルツリーレベルアップ用の関数追加
        - `Manager/`
            - `BP_CoinManager`コイン消費用関数を追加
        - `Player/`
            - `BP_SkillComponent`現在コイン参照用関数を削除、`BP_CoinManager`に移動
    - `UI/`
        - `Widget/`
            - `WBP_PlayerHUD` `BP_CoinManger`を参照してコイン数を表示するように変更
            - `WBP_SkillNode`ボタンが押されたらスキルレベルが上がる機能を追加
            
---

## 2026/05/10
### Added
- `Blueprints/`
    - `System/`
        - `BPFL_SkillTree`スキルツリー用のBP関数ライブラリ作成
    - `UI/`
        - `Widget/`
            - `WBP_SkillTree`スキルツリーのノード配置用BP作成
            - `WBP_SkillNode`スキルノード用UI作成

### Changed
- `Blueprints/`
    - `Data/`
        - `DT_SkillTree`スキルツリー用DTの名前を変更
        - `S_SkillTreeLevels`スキルレベル用構造体の名前を変更
    - `System/`
        - `GI_Parameter`NB用変数をMap型に変更。また、GIを参照しているBPも合わせて変更(SkillIDでスキルレベルをFindできるようにするため)

---

## 2026/05/08
### Added
- `Blueprints/`
    - `System/`
        - `BP_SkillComponent` GI参照用関数を持ったコンポーネント
### Changed
- `Blueprints/`
    - `Data/`
        - `S_SkillTree`スキルツリー用DT用構造体
        - `DT_MaxAmmoIncrease`スキルツリー用DT
    - `UI/`
        - `Widget/`
            - `WBP_PlayerHUD` GI参照用関数でリファクタリング
---

## 2026/05/05
### Changed
- `Blueprints/`
    - `System/`
        - `Interface/`
            - `BPI_ManagerMessage`コイン数管理用BPI追加
        - `Manager/`
            - `BP_CoinManager`コイン数管理をイベントディスパッチャーからBPIに変更
            - `BP_UIManager`BPIでUIを更新するメッセージを送るように変更
- `UI/`
    - `Widget/`
        - `WBP_PlayerHUD`コイン数管理をイベントディスパッチャーからBPIに変更
### Fixed
- `Blueprints/`
    - `Environment/`
        - `BP_KillZoneVolume`ボリューム初期化を関数で管理し、DTを読み込めないバグを修正

---

## 2026/05/04
### Changed
- `Blueprints/`
    - `System/`
        - `BP_PlayerPawn`発射関連の処理を削除
        - `BP_FireConponent`発射関連の処理を追加
        - `Interface/`発射関連のBPIを整理
        - `Manager/`発射した時のフローを整理

---

## 2026/04/30
### Added
- `Blueprints/`
    - `System/`
        - `BP_FireConponent`プレイヤーに追加する発射用アクタコンポーネント
        - `Interface/`BPI用フォルダ
        - `Manager/`CoinManagerやStageManagerなどManager用フォルダ

--- 

## 2026/04/29
### Added
- `UI/`
    - `WBP_PlayerHUD`パラメータ表示UI作成

---

## 2026/04/28
### Added
- `Blueprints/`
    - `Data/`
        - `S_LevelConfig` `DT_LevelSettings`の構造体
        - `DT_LevelSettings`ステージの床やKillZoneの広さ、カメラ距離のデータベース
    - `Environment/`
        - `Blocks/` `BP_BlockBase`の子BPでブロックアセットを作成、`BP_FloorBase`で床の親BP作成
- `Maps/`
    - `Stages/`
        - `Stage_1/`
            - `Stage_1_GrayBox`ブロック設置
        - `Stage_2/`
            - `Stage_2_GrayBox`ブロック設置
        - `Stage_3/`
            - `Stage_3_GrayBox`ブロック設置
- `Meshes/`
    - `SM_CircleFloor`床のメッシュ

### Changed
- `Blueprints/`
    - `System/`
        - `BP_PlayerPawn`クロスヘアの前方にブロックが無くても発射可能に変更
- `Maps\`
    - `Stages\`
        - `Stage_2\`
            - `Stage_2_GrayBox`仮ステージ制作
    - `Shared/`
        - `BP_Environment_Base` `BP_FloorBase`で円形の床を設定
### Removed
### Fixed

---

## 2026/04/27
### Added
- `Maps\`
    - `Stages\`ステージのフォルダを追加し、ブロック用サブレベルを作成
        - `Stage_1\`
            - `Stage_1_GrayBox`
        - `Stage_2\`
            - `Stage_2`
            - `Stage_2_GrayBox`
        - `Stage_3\`
            - `Stage_3`
            - `Stage_3_GrayBox`
        - `Stage_4\`
            - `Stage_4`
            - `Stage_4_GrayBox`
        - `Stage_5\`
            - `Stage_5`
            - `Stage_5_GrayBox`
- `Content\`
    - `UI\`
        - `WBP_StageButton`ステージセレクト用ボタン作成
        - `WBP_StageSelect`GIのUnlockedStageLevelを参照してステージレベルを生成
### Changed
- `Content\`
    - `UI\`
        - `WBP_ResultMenu`セレクトボタンでステージセレクトUIを呼び出す機能追加
    - `Blueprint\`
        - `Environment\`
            - `BP_BlockBase`物理シミュレーションをデフォルトでtrue
        - `System\`
            - `BP_StageManager`Clear変数を参照してリザルトUIをcreateする仕様に変更, クリアしたら次ステージを解放する機能追加
            - `GI_Parameter`UnlockedStageLevel変数を追加
### Removed
### Fixed
- `Config/DefaultEngine.ini`の指定ステージを編集したことによる起動時のクラッシュを修正

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