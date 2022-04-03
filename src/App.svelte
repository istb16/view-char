<script lang="ts">
  let word = "鸞";
  let size = 300;

  const onFocus = (e: FocusEvent) => {
    const it = e.currentTarget as HTMLInputElement;
    it.select();
  };
</script>

<main>
  <div class="inputFields">
    <input
      type="text"
      bind:value={word}
      autofocus
      on:focus={onFocus}
      placeholder="文字を入力してください。"
    />
    <input type="range" bind:value={size} min="7" max="1000" />
  </div>
  <div class="word" style="font-size: {size}px">{word}</div>
</main>

<style>
  .inputFields {
    position: fixed;
    inset: 0;
    margin: auto;
  }
  .word {
    margin-top: 2.5rem;
  }
</style>
