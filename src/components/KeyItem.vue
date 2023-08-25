<template>
    <div
        :class="{'white-key': !keyName.includes('b'), 'black-key': keyName.includes('b')}"
        class="key"
    >
        <span style="margin-bottom: 1rem;"> {{ keyName }} </span>
    </div>
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

.key:active, .key.active {
    background: lime;
}
.white-key {
    width: 1.9rem;
    height: 10rem;
    background: #fff;

}
.black-key {
    position: absolute;
    background: #000;
    height: 7rem;
    color: white;
    top: -1px;
}
.black-key:nth-child(1n) {
    margin-left: -.8rem;
}
</style>