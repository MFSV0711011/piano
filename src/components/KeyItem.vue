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
.white-key {
    width: 2rem;
    height: 10rem;
    background: #fff;
    border: 1px solid #000;
    background: linear-gradient(#bbb, #fff 97%, #ddd 3%);
    border-radius: 0 0 2px 2px;
}
.white-key:not(:first-child) {
    border-left: none;
}

.black-key {
    width: 1.5rem;
    height: 7rem;
    background: #000;
    margin-left: -.75rem;
    margin-right: -.75rem;
    z-index: 1;
    color: white;
    background: linear-gradient(#000000, #333333);
    border-radius: 0 0 2px 2px;
}
.key {
    display: flex;
    justify-content: center;
    align-items: flex-end;
    font-size: .7rem;
    font-family: sans-serif;
    user-select: none;
    cursor: pointer;
}

.white-key:active, .white-key.active {
    background: #ddd;
}

.black-key:active, .black-key.active{
    background: linear-gradient(#333, #000);
}

</style>