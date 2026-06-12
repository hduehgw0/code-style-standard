# コーディング規約テンプレート (Code Style Standard)

チーム開発において、コード品質の均一化と開発スピードの向上を両立させるための、VS Code ワークスペース用のコーディング規約設定集です。
Next.js などの新規プロジェクトに安全に適用できるよう設計されています。

## 導入されている機能

- **Formatter (Prettier)**: 保存時にコードの見た目（インデント、引用符など）を自動整形します。
- **Linter (markuplint / stylelint)**: HTMLとCSSのコーディング規約（命名規則、HTML構造など）をリアルタイムでチェックします。
- **Linter (ESLint)**:
JavaScriptやTypeScriptの構文チェックやバグの早期発見を行う静的解析ツールです。

## 環境要件

- **Node.js**: v22 以上 (nvm 推奨)
- **Package Manager**: pnpm
  - ※ ロックファイルの競合を防ぐため、`npm` や `yarn` ではなく必ず `pnpm` (`corepack enable` で有効化) を使用してください。

## セットアップ手順（新規プロジェクトへの適用方法）

1. **プロジェクトの土台を作成**
   適用先のプロジェクト（例: `create-next-app` や `pnpm init` を実行したディレクトリ）を用意します。

2. **設定ファイルの移植**
   このリポジトリの以下のファイル/ディレクトリを、対象プロジェクトのルートディレクトリにコピー（ペースト）してください。
   - `.vscode/`
   - `.prettierrc`
   - `.markuplintrc`
   - `.stylelintrc.json`

3. **依存パッケージの安全なインストール**
   対象プロジェクトのターミナルを開き、以下のコマンドを実行して Linter 関連のパッケージを `package.json` に追加します。
   （※直接 package.json を書き換えず、必ずこのコマンドを使用してください）
   ```bash
   pnpm add -D prettier markuplint stylelint stylelint-config-standard eslint-config-prettier
   ```

4. **VS Code 拡張機能の有効化**
  VS Codeでプロジェクトを開くと、右下に「推奨される拡張機能」のポップアップが表示されます。「すべてインストール」をクリックしてください。
