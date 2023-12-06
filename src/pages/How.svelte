<script lang="ts">
  import Markdown from "svelte-exmarkdown";
  import PaddingPane from "../components/PaddingPane.svelte";
  const md = `
## はじめかた

ここにいる人は叩いたことがありそう↓

\`\`\`sh
pnpm init svelte
\`\`\`

テンプレートにライブラリ用があるのでそれを使う  
\`src/lib\`ディレクトリにライブラリのコードを書く  
\`src/routes\`ディレクトリにサンプルコードを書く  
\`package.json\`に必要な情報を埋める！
\`npm publish\`！

see: [https://kit.svelte.dev/docs/packaging](https://kit.svelte.dev/docs/packaging)
  `;
</script>

<PaddingPane>
  <Markdown {md} />
</PaddingPane>
