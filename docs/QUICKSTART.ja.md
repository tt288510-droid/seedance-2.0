# Seedance 2.0 Skill OS クイックスタート

> バージョン 6.6.0 · インストールから最初の「演出された」プロンプトまで、約 5 分。
> 詳細は [README](../README.md) と [日本語ガイド](README.ja.md) を参照。

## これは何か

Seedance 2.0 Skill OS は、形容詞を積み重ねるのではなく、映画監督のように Seedance 2.0 を演出する agent skill です。原則はひとつ——**モデルを演出し、フレームを細かく操作しない。** シーンが「何をしているか」を伝えれば、その意図を実用的なプロンプトへコンパイルします。

## 1. インストール（約 5 分）

このリポジトリを `seedance-20` という**ひとつの**ルートスキルとして導入します。サブスキルと references は相対パスで自動的に読み込まれます。

**Codex（ワンコマンドのインストーラーあり）：**

```bash
python scripts/install_codex_skill.py --force
```

リポジトリを `~/.codex/skills/seedance-20`（または `$CODEX_HOME/skills/seedance-20`）へコピーします。Codex を再起動し、`$seedance-20` を呼び出します。

**GitHub から導入（リポジトリ URL 指定に対応するクライアントの場合）：**

```text
https://github.com/Emily2040/seedance-2.0
```

**手動コピー（その他のクライアント）：** フォルダをクライアントのスキルディレクトリへ、名前 `seedance-20` のままコピーします。よくある配置先（保証ではなく、必ず自分のクライアントで確認）は [README のインストール表](../README.md#install) にあります。例：Claude Code `.claude/skills/`、Cursor `.cursor/skills/`、GitHub Copilot `.github/skills/`、Windsurf `.windsurf/skills/`。

> セキュリティ優先：信頼できる agent クライアントにのみ導入してください。第三者や不明な agent で使う前に [SECURITY.md](../SECURITY.md) を必ずお読みください。

## 2. 状況に合わせてスキルを選ぶ

| こんなとき | まず読み込む |
|---|---|
| 曖昧なアイデア | `seedance-interview` |
| 明確なシーン | `seedance-prompt` |
| 複数クリップの物語 | `seedance-sequence` |
| 受け入れ済みクリップの続き | `seedance-continuation` |
| 出来が悪い・ブロックされた結果 | `seedance-troubleshoot` |
| キャラクター・ブランド・著名人・実在人物 | `seedance-copyright` |

## 3. 書く前に「演出」する——4 つの問い

1. **このシーンは何をしているか？** 転換、開示、感情、それとも提示か。
2. **カメラはそれをどう語るか？** 孤立を示すワイド、表情を見せるクロース、悟りを運ぶプッシュイン。
3. **光は何をするか？** 時間帯、硬い/柔らかい、暖色/寒色——すべて意図のために。
4. **音は何をするか？** ほぼ無音、ひとつの環境音、あるいは一言のセリフ。

## 4. 一例

**装飾的（弱い）：**

```
壮大でシネマティックな、手紙を読む女性、感情的、美しいライティング、4K
```

**演出的（強い）：**

```
ミディアムクローズアップ、目線の高さ。手紙を下ろすと手が止まり、ゆっくりとしたプッシュインが訪れる。柔らかな窓明かりが顔を素のまま保つ。ほぼ無音、椅子のこすれる音がひとつ。
```

## 5. テイクを節約する 2 つのルール

- **参照タグは書かれたとおりに保持**——`[Image1]`、`[Video1]`、`[Audio1]`、`@图1`、`@视频1`。翻訳も整形もしないこと。
- **物語全体を一度の生成で求めない。** まず Clip 01 を生成し、それが「実際に」どう終わったかを観察してから、その本当の終わりをもとに Clip 02 を書く（`seedance-continuation`）。

## 6. 安全

- **コンテンツの安全：** 保護されたキャラクター、著名人、ブランド、ロゴ、楽曲、または実在人物の顔や声を使う場合、別の言語で隠さないこと。`seedance-copyright` でオリジナル・ライセンス済み・ポスプロ代替へ書き換えます。
- **agent の安全：** このパッケージは**ネットワーク通信を行わず、テレメトリも含みません**。スクリプトは決定論的でオフライン動作です。API キー、アカウント Cookie、非公開素材を信頼できない agent に貼り付けないでください。[SECURITY.md](../SECURITY.md) を参照。

## 7. さらに深く

- `references/directing-engine.md` — シーンを読み、ひとつの意図を選ぶ（35 の作例）。
- `references/capability-map.md` — モデルの強みに沿い、既知の限界を避けて設計する。
- `references/api-workflow.md` — API、プロバイダー、価格、モデル ID（出典日付つき）。
- `references/examples-by-mode.md` — T2V、I2V、V2V、R2V、FLF2V、編集、延長の例。

---

他の言語：[English](QUICKSTART.md) · [中文](QUICKSTART.zh.md) · [한국어](QUICKSTART.ko.md) · [Español](QUICKSTART.es.md) · [Русский](QUICKSTART.ru.md)
