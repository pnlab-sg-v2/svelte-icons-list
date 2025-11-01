<script>
  import VirtualList from '@sveltejs/svelte-virtual-list';
  let allEmojis = []
  for (let i=128100;i<128293;i++){
    allEmojis.push(String.fromCodePoint(`${i}`.toString(16)))  
   
  }
  
  let searchTerm = '';
  let filteredEmojis = allEmojis;
  
  $: {
    if (searchTerm.trim() === '') {
      filteredEmojis = allEmojis;
    } else {
      // Filter emojis by character - users can paste an emoji to find it
      filteredEmojis = allEmojis.filter(emoji => emoji.includes(searchTerm));
    }
  }
  
  let start;
	let end;
</script>

<div class="wrapper">
  <div class="search-container">
    <input 
      type="text" 
      bind:value={searchTerm} 
      placeholder="Search emojis..."
      class="search-input"
    />
    <span class="result-count">{filteredEmojis.length} emoji{filteredEmojis.length !== 1 ? 's' : ''}</span>
  </div>
  
  <div class="container">
    <VirtualList items={filteredEmojis} bind:start bind:end let:item>
      <p class="text">{item}</p>
    </VirtualList>
  </div>
</div>

<style>
  .wrapper {
    padding: 20px;
    height: 100vh;
    display: flex;
    flex-direction: column;
  }
  
  .search-container {
    margin-bottom: 20px;
    display: flex;
    align-items: center;
    gap: 15px;
  }
  
  .search-input {
    flex: 1;
    max-width: 400px;
    padding: 10px 15px;
    font-size: 16px;
    border: 2px solid #ddd;
    border-radius: 8px;
    outline: none;
    transition: border-color 0.3s;
  }
  
  .search-input:focus {
    border-color: #646cff;
  }
  
  .result-count {
    color: #666;
    font-size: 14px;
  }
  
  .text {
    font-size: 25px;
  }
  
  .container {
    display: grid;
    grid-template-columns: repeat(10, 1fr);
    flex: 1;
    overflow: hidden;
  }
</style>
