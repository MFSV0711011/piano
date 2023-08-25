<template>
    <ul class="piano-container" >


                <KeyItem
                    v-for="key of keys"
                    :key="key.id"
                    :class="{'white-td': !key.name.includes('b'), 'black-td': key.name.includes('b')}"
                    :key-name="key.name"
                    :note="key.name"
                    :key-code="key.keyCode"
                    :src="key.src"
                    @mousedown="play(key.src)"
                    ref="keyitem"
                />
    </ul>
</template>

<script>
import KeyItem from "@/components/KeyItem";
export default {
    name: "PianoContainer",
    components: {
        KeyItem
    },
    data() {
        return {
            keyboard: {
                a: 'C4',

            },
            keys: [
                {id: 6, name: 'A0', src: 'A0.mp3', keyCode: ''},
                {id: 7, name: 'A#0', src: 'Bb0.mp3', keyCode: ''},
                {id: 7, name: 'B0', src: 'B0.mp3', keyCode: ''},
                {id: 8, name: 'C1', src: 'C1.mp3', keyCode: ''},
                {id: 9, name: 'C#1', src: 'Db1.mp3', keyCode: ''},
                {id: 9, name: 'D1', src: 'D1.mp3', keyCode: ''},
                {id: 10, name: 'D#1', src: 'Eb1.mp3', keyCode: ''},
                {id: 10, name: 'E1', src: 'E1.mp3', keyCode: ''},
                {id: 11, name: 'F1', src: 'F1.mp3', keyCode: ''},
                {id: 12, name: 'F#1', src: 'Gb1.mp3', keyCode: ''},
                {id: 12, name: 'G1', src: 'G1.mp3', keyCode: ''},
                {id: 13, name: 'G#1', src: 'Ab1.mp3', keyCode: ''},
                {id: 13, name: 'A1', src: 'A1.mp3', keyCode: ''},
                {id: 14, name: 'A#1', src: 'Bb1.mp3', keyCode: ''},
                {id: 14, name: 'B1', src: 'B1.mp3', keyCode: ''},
                {id: 15, name: 'C2', src: 'C2.mp3', keyCode: 'z'},
                {id: 16, name: 'C#2', src: 'Db2.mp3', keyCode: 's'},
                {id: 16, name: 'D2', src: 'D2.mp3', keyCode: 'x'},
                {id: 17, name: 'D#2', src: 'Eb2.mp3', keyCode: 'd'},
                {id: 17, name: 'E2', src: 'E2.mp3', keyCode: 'c'},
                {id: 18, name: 'F2', src: 'F2.mp3', keyCode: 'v'},
                {id: 19, name: 'F#2', src: 'Gb2.mp3', keyCode: 'g'},
                {id: 19, name: 'G2', src: 'G2.mp3', keyCode: 'b'},
                {id: 20, name: 'G#2', src: 'Ab2.mp3', keyCode: 'h'},
                {id: 20, name: 'A2', src: 'A2.mp3', keyCode: 'n'},
                {id: 21, name: 'A#2', src: 'Bb2.mp3', keyCode: 'j'},
                {id: 21, name: 'B2', src: 'B2.mp3', keyCode: 'm'},
                {id: 22, name: 'C3', src: 'C3.mp3', keyCode: ','},
                {id: 23, name: 'C#3', src: 'Db3.mp3', keyCode: 'l'},
                {id: 23, name: 'D3', src: 'D3.mp3', keyCode: '.'},
                {id: 24, name: 'D#3', src: 'Eb3.mp3', keyCode: ';'},
                {id: 24, name: 'E3', src: 'E3.mp3', keyCode: '/'},
                {id: 25, name: 'F3', src: 'F3.mp3', keyCode: 'Shift'},
                {id: 26, name: 'F#3', src: 'Gb3.mp3', keyCode: 'Enter'},
                {id: 26, name: 'G3', src: 'G3.mp3', keyCode: ''},
                {id: 27, name: 'G#3', src: 'Ab3.mp3', keyCode: ''},
                {id: 27, name: 'A3', src: 'A3.mp3', keyCode: ''},
                {id: 28, name: 'A#3', src: 'Bb3.mp3', keyCode: ''},
                {id: 28, name: 'B3', src: 'B3.mp3', keyCode: ''},
                {id: 29, name: 'C4', src: 'C4.mp3', keyCode: 'q'},
                {id: 30, name: 'C#4', src: 'Db4.mp3', keyCode: '2'},
                {id: 30, name: 'D4', src: 'D4.mp3', keyCode: 'w'},
                {id: 31, name: 'D#4', src: 'Eb4.mp3', keyCode: '3'},
                {id: 31, name: 'E4', src: 'E4.mp3', keyCode: 'e'},
                {id: 32, name: 'F4', src: 'F4.mp3', keyCode: 'r'},
                {id: 33, name: 'F#4', src: 'Gb4.mp3', keyCode: '5'},
                {id: 33, name: 'G4', src: 'G4.mp3', keyCode: 't'},
                {id: 34, name: 'G#4', src: 'Ab4.mp3', keyCode: '6'},
                {id: 34, name: 'A4', src: 'A4.mp3', keyCode: 'y'},
                {id: 35, name: 'A#4', src: 'Bb4.mp3', keyCode: '7'},
                {id: 35, name: 'B4', src: 'B4.mp3', keyCode: 'u'},
                {id: 36, name: 'C5', src: 'C5.mp3', keyCode: 'i'},
                {id: 37, name: 'C#5', src: 'Db5.mp3', keyCode: '9'},
                {id: 37, name: 'D5', src: 'D5.mp3', keyCode: 'o'},
                {id: 38, name: 'D#5', src: 'Eb5.mp3', keyCode: '0'},
                {id: 38, name: 'E5', src: 'E5.mp3', keyCode: 'p'},
                {id: 39, name: 'F5', src: 'F5.mp3', keyCode: "["},
                {id: 40, name: 'F#5', src: 'Gb5.mp3', keyCode: '='},
                {id: 40, name: 'G5', src: 'G5.mp3', keyCode: ']'},
                {id: 41, name: 'G#5', src: 'Ab5.mp3', keyCode: 'Backspace'},
                {id: 41, name: 'A5', src: 'A5.mp3', keyCode: '\\'},
                {id: 42, name: 'A#5', src: 'Bb5.mp3', keyCode: 'Insert'},
                {id: 42, name: 'B5', src: 'B5.mp3', keyCode: 'Delete'},
            ]
        }
    },
    computed: {
      whiteKey() {
          return  this.keys.filter(item => !item.name.includes('b'))
      },
      blackKey() {
          return  this.keys.filter(item => item.name.includes('b'))
      }
    },
    methods: {
        play(src){
            let note = new Audio(require('@/assets/notes/' + src));
            note.play()
        }
    },
    mounted() {
        window.addEventListener('keydown', e => {
            console.log(e.key)
            this.$refs.keyitem.forEach(item => {
                if(item.keyCode === e.key) {
                    this.play(item.src)
                    item.$el.classList.add('active')
                }
            })
        })
        window.addEventListener('keyup', e => {
            this.$refs.keyitem.forEach(item => {
                if(item.keyCode === e.key) {
                    item.$el.classList.remove('active')
                }
            })
        })
    }

}
</script>

<style scoped>
.piano-container {
    position: relative;
    margin: 0 auto;
    display: flex;
    justify-content: center;
    border-collapse: collapse;
    overflow: hidden;
    list-style: none;
}

</style>