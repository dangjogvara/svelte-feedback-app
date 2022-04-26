<script>
  import FeedbackList from './components/FeedbackList.svelte';
  import FeedbackStats from './components/FeedbackStats.svelte';
  import FeedbackForm from './components/FeedbackForm.svelte';

  let feedback = [
    {
      id: 1,
      rating: 10,
      text: `Lorem ipsum 
      dolor sit, amet consectetur 
      adipisicing elit. Labore mollitia dolorem 
      iste. Sapiente beatae deserunt similique hic tempore aperiam itaque molestiae, tenetur 
      asperiores dignissimos ea. Aut deleniti accusamus itaque totam.`,
    },
    {
      id: 2,
      rating: 9,
      text: `Lorem ipsum, dolor sit amet consectetur 
      adipisicing elit. Possimus, voluptates laboriosam eligendi nobis praesentium 
      totam numquam? Voluptatum, libero molestias. Commodi neque dolorem ratione expedita tempore 
      cupiditate nobis fuga repellat officiis.`,
    },
    {
      id: 3,
      rating: 8,
      text: `Lorem ipsum dolor, sit amet consectetur 
      adipisicing elit. Deleniti eum quis vitae, at praesentium sint, 
      voluptatum dolorem est a eos facilis beatae veritatis optio unde explicabo? 
      Assumenda magni dolorem porro?`,
    },
  ];

  const deleteFeedback = e => {
    const itemId = e.detail;
    feedback = feedback.filter(item => item.id !== itemId);
  };

  $: count = feedback.length;
  $: average = feedback.reduce((a, { rating }) => a + rating, 0) / feedback.length;
</script>

<main class="container">
  <FeedbackForm />
  <FeedbackStats {count} {average} />
  <FeedbackList {feedback} on:delete-feedback={deleteFeedback} />
</main>

<style>
</style>
