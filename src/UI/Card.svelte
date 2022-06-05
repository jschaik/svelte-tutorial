<div class="card">
  <!-- Before a component can accept children, though, 
    it needs to know where to put them. 
    You do this with the <slot> element. -->
  <slot></slot>
</div>

<style>
    .card {
        background-color: white;
        color: #333;
        border-radius: 15px;
        padding: 40px 50px;
        margin: 20px 0;
        position: relative

    }
</style>