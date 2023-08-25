<template>
    <li
        :class="{'white-key': !src.includes('b'), 'black-key': src.includes('b')}"
        class="key"
    >
        <span style="margin-bottom: 1rem;"> {{ keyName }} </span>
    </li>
</template>

<script>
export default {
    name: "KeyItem",
    props: {
        keyName: {
            type: String,
            required: true
        },
        note: {
            type: String,
            required: true
        },
        keyCode: {
            type: String,
            required: true
        },
        src: {
            type: String,
            required: true
        }
    },


}
</script>

<style scoped>
.key {
    display: flex;
    justify-content: center;
    align-items: flex-end;
    font-size: .7rem;
    font-family: sans-serif;
    user-select: none;
    cursor: pointer;
}

.white-key {
    position: relative;
    width: 1.9rem;
    height: 10rem;
    background: linear-gradient(#fff 97%, #ddd 3%);
    border-radius: 0 0 5px 5px;
    border: 1px solid #000;
}
.white-key:active, .white-key.active {
    background: #ddd;
}
.white-key:not(:first-child) {
}
.black-key {
    border: 1px solid #000;
    background: linear-gradient(#000000, #333333);
    height: 7rem;
    color: white;
    margin: -3rem -.7rem 0 -.7rem;
    z-index: 1;
}

.black-key:active, .black-key.active{
    background: linear-gradient(#333, #000);
}
</style>