<script>
  // CPI indices for "Food Away from Home" (Feb 2020 = 100 baseline)
  const cpi = {
    2020: 100,
    2021: 104.5,
    2022: 112.5,
    2023: 120.5,
    2024: 125.4,
    2025: 130.1
  };

  // user-editable state
  let basePrice = $state(0);
  let baseYear = $state(2020);
  let targetYear = $state(2025);
  let total = $derived(basePrice * (cpi[targetYear] / cpi[baseYear]));
</script>

<div class="inflation-calculator">
  <h3>Inflation Calculator</h3>

  <label>
    Year:
    <select bind:value={targetYear}>
      {#each Object.keys(cpi) as year}
        <option value={+year}>{year}</option>
      {/each}
    </select>
  </label>

  <label>
    Menu price in {baseYear}:
    <div class="input-group">
    <div class="input-wrapper">
      <span class="currency">$</span>
      <input 
        min="0" 
        bind:value={basePrice} />
  </label>

  <div class="result">
    <span class="label">Total</span>
     <span class="value">${total.toFixed(2)}</span>
    </div>
</div>

<style>
  .inflation-calculator {
    padding: 1.5rem;
    background: var(--color-light-gray);
    margin: 2rem 0;
    max-width: 400px;
    justify-content: center;
  }

  h3 {
    margin: 0 0 1.5rem !important;
    font-weight: bold !important;
    font-size: 1.75rem !important;
    text-transform: uppercase;
  }

  .input-group {
    margin-bottom: 1.5rem;
  }

  .input-wrapper {
    display: flex;
    align-items: center;
    border: 2px solid #ddd;
  }

 .currency {
    padding: 0.75rem;
    background: #eee;
    font-weight: bold;
  }

  .inflation-calculator label {
    display: block;
    margin-bottom: 0.5rem;
  }

  .inflation-calculator input,
  .inflation-calculator select {
    width: 100%;
    box-sizing: border-box;
    padding: 0.25rem;
    margin-top: 0.25rem;
    margin-right: 0.25rem;
  }

  .inflation-calculator p {
    margin: 0.5rem 0;
  }

  .result {
    padding: 1rem;
    background: var(--color-accent);
    color: white;
    display: flex;
    justify-content: space-between;
    align-items: center;
    }
</style>