<template>
  <body>
  <div class="layout">
      <!-- トップバー・ナビゲーションなど -->
      <todo-header />
      <!-- サイドバー、メニューなど -->

    <main>
      <!-- この部分にページの主要なコンテンツや他のコンポーネントが入る -->
      <slot></slot>
    </main>

      <!-- フッター情報、リンクなど -->
      <todo-footer />

  </div>
  </body>
</template>

<script>
import TodoHeader from '@/components/organisms/TodoHeader.vue';
import TodoFooter from '@/components/organisms/TodoFooter.vue';

export default {
  name: 'LayoutComponent',
  components: {
    TodoHeader,
    TodoFooter
  },
}
</script>

<style scoped>
.layout {
  display: flex;
  flex-direction: column;
  justify-content: center; /* 横方向の中央寄せ */
  width: 100%;
  margin: 16px;
  max-width: min(100%, 1200px);
  min-height: 100vh; /* 画面の高さを100%にします。これにより縦の中央寄せが効くようになります */

  /* クールなデザインを追加する場合、以下のようなプロパティを追加してください */
  background: rgb(8, 8, 8); /* 背景色 */
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); /* 影 */
  border-radius: 8px; /* 角の丸み */
  padding: 20px; /* 内部のスペース */
}

body, html {
  margin: 0;
  padding: 0;
  height: 100%;
  display: flex;
  justify-content: center;  /* 横方向の中央寄せ */
  align-items: center;      /* 縦方向の中央寄せ */
}
</style>

