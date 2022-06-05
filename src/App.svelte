<script>
  import FeedbackStats from "./components/FeedbackStats.svelte";
  import FeedbackList from "./components/FeedbackList.svelte";

  let feedback = [
    {
      id: 1,
      rating: 10,
      text: "Lorem ipsum dolor sit amet consectetur adipisicing elit. consequuntur vel vitae commodi alias voluptatem est voluptatum ipsa quae.",
    },
    {
      id: 2,
      rating: 9,
      text: "Lorem ipsum dolor sit amet consectetur adipisicing elit. consequuntur vel vitae commodi alias voluptatem est voluptatum ipsa quae.",
    },
    {
      id: 3,
      rating: 8,
      text: "Lorem ipsum dolor sit amet consectetur adipisicing elit. consequuntur vel vitae commodi alias voluptatem est voluptatum ipsa quae.",
    },
  ];

  //reactivity declaration, same als useState in React
  $: count = feedback.length;

  //multiply rating devide by feedback.length to get the average
  //0 = start index
  $: average = feedback.reduce((item, { rating }) => item + rating, 0) / count;

  const deleteFeedback = (e) => {
    const itemId = e.detail;
    feedback = feedback.filter((item) => item.id != itemId);
  };
</script>

<main class="container">
  <FeedbackStats {count} {average} />
  <FeedbackList {feedback} on:delete-feedback={deleteFeedback} />
</main>
