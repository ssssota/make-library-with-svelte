<script lang="ts">
  import Markdown from "svelte-exmarkdown";
  import PaddingPane from "../components/PaddingPane.svelte";
  const md = `
## 難しいこと

Svelteはその設計上UIコンポーネントライブラリの**設計**がReactなどJSX系ライブラリと比較して難しい。  
これは第一級オブジェクトとして扱える範囲が狭いことに起因する。  
→CSSカスタムプロパティ(変数)、svelte/action(use:*)もうまく使おう。
  `;
</script>

<PaddingPane>
  <Markdown {md} />
</PaddingPane>
