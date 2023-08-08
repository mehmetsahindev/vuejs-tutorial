<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal">
        <h1>{{ title }}</h1>
        <p>{{ text }}</p>
        <div class="modal-content">
            <slot></slot>
        </div>
        <div class="actions">
            <slot name="actions"></slot>
        </div>
    </div>
  </div>
</template>

<script>
export default {
    props: ["title", "text"],
    methods: {
        closeModal() {
            this.$emit("close-modal")
        }
    }
}
</script>

<style>
    .backdrop {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: rgb(0, 0, 0, 0.5);
    }

    .modal {
        width: 400px;
        margin: 100px auto;
        background-color: #ffffff;
        border-radius: 15px;
        padding: 20px;
    }
    .modal .modal-content {
        margin-top: 30px;
        margin-bottom: 30px;
    }
    .modal .input-group {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        margin-bottom: 15px;
    }
    .modal .input-group input {
        border: 1px solid #ccc;
        padding: 10px 5px;
        display: block;
        width: 100%;
        box-sizing: border-box;
        border-radius: 8px;
    }

    .modal .actions {
        display: flex;
        justify-content: center;
        margin-bottom: 20px;
    }
    .modal .actions a {
        display: block;
        margin: 0 10px;
        border: 1px solid #ccc;
        text-decoration: none;
        color: #000;
        padding: 5px 10px;
        border-radius: 8px;
    }
</style>