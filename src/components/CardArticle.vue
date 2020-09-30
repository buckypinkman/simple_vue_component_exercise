<template>
    <div class="col-lg-10">
      <div class="card-body shadow-sm">
        <div class="card p-4">
          <slot></slot>
        </div>
      </div>
    </div>
</template>

<style scoped>
    * {
        padding: 0;
        margin: 0;
    }

    .card-body {
        font-size: 20px;
        font-family: Georgia, 'Times New Roman', Times, serif;
        color: rgb(70, 69, 69);
    }

    .card {
        cursor: pointer;
        transition: .25s;
    }

    .card:hover {
        background-color: rgb(255, 199, 197);
    }

</style>