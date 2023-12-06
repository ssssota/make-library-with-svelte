<script lang="ts">
  import Markdown from "svelte-exmarkdown";
  import PaddingPane from "../components/PaddingPane.svelte";
  const md = `
## Tips

- 作ったらMade with Svelteに登録しよう！
  - 日本人以外にもリーチできる(Hacker Newsなども?)
- 作ったらSvelte日本Discord\`#ショーケース\`で紹介しよう！
  - 反応もらえます。コミュニティ温かい
- changesetsとrenovateの設定をしておくと便利
  - ライブラリ開発をサステナブルにしよう
- 一応v0.1から始めつつ、はやくv1をリリースしよう！
  - 大体リリース直後インターフェース迷いがちなのでv0.1で
  - v1になるとライブラリ採用のハードルが下がる
  `;
</script>

<PaddingPane>
  <Markdown {md} />
</PaddingPane>
