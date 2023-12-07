<script lang="ts">
  import Markdown from "svelte-exmarkdown";
  import PaddingPane from "../components/PaddingPane.svelte";
  const md = `
## 誰？

- 冨川宗太郎
- フロントエンドエンジニア
- \`{ x: 'ssssotaro', github: 'ssssota' }\`
- ![icon](https://github.com/ssssota.png?size=100)
- svelte-exmarkdownっていうのを作っている
  - このスライドもsvelte-exmarkdownが使われています
  `;
</script>

<PaddingPane>
  <Markdown {md} />
</PaddingPane>
