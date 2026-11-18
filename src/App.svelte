<script lang="ts">
  let word = $state("鸞");
  let size = $state(300);

  const onFocus = (e: FocusEvent) => {
    const it = e.currentTarget as HTMLInputElement;
    it.select();
  };
</script>

<header class="tk-header">
  <a class="tk-header__home" href="/">
    <img class="tk-header__icon" src="/icon.svg" alt="" />
    <span class="tk-header__name">VIEW CHARACTER</span>
  </a>
</header>

<main>
  <div class="inputFields tk-panel">
    <label class="field">
      <span class="tk-visually-hidden">表示する文字</span>
      <!-- svelte-ignore a11y_autofocus -->
      <input
        type="text"
        bind:value={word}
        autofocus
        onfocus={onFocus}
        placeholder="文字を入力してください。"
      />
    </label>
    <label class="field size">
      <span class="label">大きさ</span>
      <input type="range" bind:value={size} min="7" max="1000" />
      <output>{size}px</output>
    </label>
  </div>
  <div class="word" style="font-size: {size}px">{word}</div>
</main>

<footer class="tk-footer">
  <a href="https://tk3.biz/">tk3.biz</a>
</footer>

<style>
  main {
    flex: 1;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 16px;
    padding: 16px;
    text-align: center;
    min-inline-size: 0;
  }
  .inputFields {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    gap: 12px 20px;
    inline-size: min(100%, 640px);
    box-sizing: border-box;
  }
  .field {
    display: flex;
    align-items: center;
    gap: 8px;
  }
  .size {
    color: var(--tk-body);
    font-size: 0.875rem;
  }
  .size input {
    padding: 0;
    border: 0;
    background: transparent;
  }
  output {
    min-inline-size: 4.5em;
    text-align: end;
    font-family: var(--tk-font-mono);
    font-variant-numeric: tabular-nums;
  }
  .word {
    font-family: var(--vc-font-char);
    color: var(--tk-ink);
    line-height: 1.2;
    max-inline-size: 100%;
    overflow-wrap: anywhere;
  }
</style>
