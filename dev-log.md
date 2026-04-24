# 開発ログ
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