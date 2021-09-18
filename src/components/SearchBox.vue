<template>
    <form action="" @submit.prevent="searchProfile" class="form">
        <button type="submit" class="form__btn">
            <svg width="18" height="18" fill="none" xmlns="http://www.w3.org/2000/svg"><path opacity=".54" fill-rule="evenodd" clip-rule="evenodd" d="M12.502 11h-.794l-.276-.274A6.47 6.47 0 0 0 13 6.5 6.5 6.5 0 1 0 6.5 13a6.47 6.47 0 0 0 4.225-1.566l.276.274v.792l4.998 4.991L17.49 16l-4.988-5ZM6.5 11a4.5 4.5 0 1 1 0-9 4.5 4.5 0 0 1 0 9Z" fill="#000"/></svg>
        </button>
        <input type="search" name="" class="form__input">
    </form>
</template>

<script>
export default {
    methods: {
        searchProfile: () => {
            console.log('searched')
        }
    }
}

</script>

<style scoped>
.form {
    position: relative;
    margin-bottom: 20px;
}

.form__input {
    background-color: #fafafa;
    box-shadow: 0px 0px 2px rgba(0, 0, 0, 0.12), 0px 2px 2px rgba(0, 0, 0, 0.24);
    border-radius: 2px;
    border: none;
    font-family: 'Roboto', sans-serif;
    font-size: 24px;
    line-height: 1;
    color: rgba(0, 0, 0, 0.75);
    padding: 12px 30px 12px 50px;
    width: 100%;
}

.form__btn {
    position: absolute;
    z-index: 1;
    top: 0;
    bottom: 0;
    left: 20px;
    display: grid;
    place-items: center;
    background-color: transparent;
    border: none;
    padding: 0;
}
</style>