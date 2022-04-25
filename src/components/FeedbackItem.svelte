<script>
  import Card from './UI/Card.svelte';

  export let item;
</script>

<Card>
  <div class="num-display">
    {item.rating}
  </div>
</Card>
