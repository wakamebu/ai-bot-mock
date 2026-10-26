# ai-bot-mock

クリニック向け AI チャットボット（モック）の取りまとめリポジトリ。各ディレクトリは git submodule。

| ディレクトリ | リポジトリ・ブランチ | 内容 |
| --- | --- | --- |
| `backend` | [ai-bot-mock-backend](https://github.com/wakamebu/ai-bot-mock-backend) `main` | 共通の土台（mock 方式） |
| `backend-dify` | 同 `dify-develop` | Dify 方式（テナントごとに Dify インスタンス） |
| `backend-openai` | 同 `openai-develop` | OpenAI File Search 方式（テナントごとに Vector Store） |
| `front-mock` | [ai-bot-mock-front](https://github.com/wakamebu/ai-bot-mock-front) `main` | 各方式を並べて試すテスト用フロントエンド（Vite） |

## 取得

```bash
git clone --recurse-submodules https://github.com/wakamebu/ai-bot-mock.git
# 各 submodule を記録されたブランチの最新にする
git submodule update --remote
```

- 3つの backend は同じリポジトリの別ブランチ。手元では `git worktree` で作ったものをそのまま submodule にしている。
- このリポジトリが記録するのは各 submodule のコミット。各リポジトリで push したあと、ここで `git add <ディレクトリ>` してコミットすると記録が進む。

## 動かし方

各ディレクトリの README を参照。比べて試すときは、`backend-dify` と `backend-openai` で偽サーバーとアプリを起動し、`front-mock` で `npm run dev`（http://localhost:5173）。
費用の見積もりは各 backend の `docs/cost-*.md` と `/cost.html`。
