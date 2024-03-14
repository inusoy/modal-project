<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal"
            :class="{ sale: theme === 'sale', dark: theme === 'dark', other: theme !== ('sale' || 'dark') }">
            <slot></slot>
            <div class="actions">
                <slot name="links"></slot>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['theme'],
    methods: {
        closeModal() {
            this.$emit('close')
        }
    }
}
</script>

<style>
.modal {
    width: 400px;
    padding: 20px;
    margin: 100px auto;
    background: white;
    border-radius: 10px;
}

.backdrop {
    top: 0;
    position: fixed;
    background-color: rgba(0, 0, 0, 0.5);
    width: 100%;
    height: 100%;
}

.modal h1 {
    color: #03cfb4;
    border: none;
    padding: 0;
}

.modal.sale {
    background-color: crimson;
    color: white;

    h1 {
        color: white;
    }
}
</style>