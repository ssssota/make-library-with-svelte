<script lang="ts">
  import Markdown from "svelte-exmarkdown";
  import PaddingPane from "../components/PaddingPane.svelte";
  const md = `
## Svelte5について

キターーー！！！🔥🔥🔥（まだですが）

すでにライブラリを作っている皆様、対応頑張りましょう。  
まだ作ってない皆様、Svelte5で作り始めましょう。

イベントハンドラが第一級オブジェクト(相当)として扱えるようになり**かなり**柔軟性が向上しています。

Context+Storeだった箇所もContext+Runesで置き換えることができパフォーマンス向上も期待できます。
  `;
</script>

<PaddingPane>
  <Markdown {md} />
</PaddingPane>
