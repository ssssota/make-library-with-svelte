<script lang="ts">
  import PaddingPane from '../components/PaddingPane.svelte';
  import Markdown from 'svelte-exmarkdown';
  const md = `
## 誰？

- 冨川宗太郎
- フロントエンドエンジニア
- \`{ x: 'ssssotaro', github: 'ssssota' }\`
- ![icon](https://github.com/ssssota.png?size=100)
- 業務Svelte経験ほぼ無し
- svelte-exmarkdown作者
  - このスライドもsvelte-exmarkdownが使われています
  `;
</script>

<PaddingPane>
  <Markdown {md} />
</PaddingPane>
