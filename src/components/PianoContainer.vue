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
                {id: 1, name: 'A0', src: 'A0.mp3', keyCode: ''},
                {id: 2, name: 'A#0', src: 'Bb0.mp3', keyCode: ''},
                {id: 3, name: 'B0', src: 'B0.mp3', keyCode: ''},
                {id: 4, name: 'C1', src: 'C1.mp3', keyCode: ''},
                {id: 5, name: 'C#1', src: 'Db1.mp3', keyCode: ''},
                {id: 6, name: 'D1', src: 'D1.mp3', keyCode: ''},
                {id: 7, name: 'D#1', src: 'Eb1.mp3', keyCode: ''},
                {id: 8, name: 'E1', src: 'E1.mp3', keyCode: ''},
                {id: 9, name: 'F1', src: 'F1.mp3', keyCode: ''},
                {id: 10, name: 'F#1', src: 'Gb1.mp3', keyCode: ''},
                {id: 11, name: 'G1', src: 'G1.mp3', keyCode: ''},
                {id: 12, name: 'G#1', src: 'Ab1.mp3', keyCode: ''},
                {id: 13, name: 'A1', src: 'A1.mp3', keyCode: ''},
                {id: 14, name: 'A#1', src: 'Bb1.mp3', keyCode: ''},
                {id: 15, name: 'B1', src: 'B1.mp3', keyCode: ''},
                {id: 16, name: 'C2', src: 'C2.mp3', keyCode: 'z'},
                {id: 17, name: 'C#2', src: 'Db2.mp3', keyCode: 's'},
                {id: 18, name: 'D2', src: 'D2.mp3', keyCode: 'x'},
                {id: 19, name: 'D#2', src: 'Eb2.mp3', keyCode: 'd'},
                {id: 20, name: 'E2', src: 'E2.mp3', keyCode: 'c'},
                {id: 21, name: 'F2', src: 'F2.mp3', keyCode: 'v'},
                {id: 22, name: 'F#2', src: 'Gb2.mp3', keyCode: 'g'},
                {id: 23, name: 'G2', src: 'G2.mp3', keyCode: 'b'},
                {id: 24, name: 'G#2', src: 'Ab2.mp3', keyCode: 'h'},
                {id: 25, name: 'A2', src: 'A2.mp3', keyCode: 'n'},
                {id: 26, name: 'A#2', src: 'Bb2.mp3', keyCode: 'j'},
                {id: 27, name: 'B2', src: 'B2.mp3', keyCode: 'm'},
                {id: 28, name: 'C3', src: 'C3.mp3', keyCode: ','},
                {id: 29, name: 'C#3', src: 'Db3.mp3', keyCode: 'l'},
                {id: 30, name: 'D3', src: 'D3.mp3', keyCode: '.'},
                {id: 31, name: 'D#3', src: 'Eb3.mp3', keyCode: ';'},
                {id: 32, name: 'E3', src: 'E3.mp3', keyCode: '/'},
                {id: 33, name: 'F3', src: 'F3.mp3', keyCode: 'Shift'},
                {id: 34, name: 'F#3', src: 'Gb3.mp3', keyCode: 'Enter'},
                {id: 35, name: 'G3', src: 'G3.mp3', keyCode: ''},
                {id: 36, name: 'G#3', src: 'Ab3.mp3', keyCode: ''},
                {id: 37, name: 'A3', src: 'A3.mp3', keyCode: ''},
                {id: 38, name: 'A#3', src: 'Bb3.mp3', keyCode: ''},
                {id: 39, name: 'B3', src: 'B3.mp3', keyCode: ''},
                {id: 40, name: 'C4', src: 'C4.mp3', keyCode: 'q'},
                {id: 41, name: 'C#4', src: 'Db4.mp3', keyCode: '2'},
                {id: 42, name: 'D4', src: 'D4.mp3', keyCode: 'w'},
                {id: 43, name: 'D#4', src: 'Eb4.mp3', keyCode: '3'},
                {id: 44, name: 'E4', src: 'E4.mp3', keyCode: 'e'},
                {id: 45, name: 'F4', src: 'F4.mp3', keyCode: 'r'},
                {id: 46, name: 'F#4', src: 'Gb4.mp3', keyCode: '5'},
                {id: 47, name: 'G4', src: 'G4.mp3', keyCode: 't'},
                {id: 48, name: 'G#4', src: 'Ab4.mp3', keyCode: '6'},
                {id: 49, name: 'A4', src: 'A4.mp3', keyCode: 'y'},
                {id: 50, name: 'A#4', src: 'Bb4.mp3', keyCode: '7'},
                {id: 51, name: 'B4', src: 'B4.mp3', keyCode: 'u'},
                {id: 52, name: 'C5', src: 'C5.mp3', keyCode: 'i'},
                {id: 53, name: 'C#5', src: 'Db5.mp3', keyCode: '9'},
                {id: 54, name: 'D5', src: 'D5.mp3', keyCode: 'o'},
                {id: 55, name: 'D#5', src: 'Eb5.mp3', keyCode: '0'},
                {id: 56, name: 'E5', src: 'E5.mp3', keyCode: 'p'},
                {id: 57, name: 'F5', src: 'F5.mp3', keyCode: "["},
                {id: 58, name: 'F#5', src: 'Gb5.mp3', keyCode: '='},
                {id: 59, name: 'G5', src: 'G5.mp3', keyCode: ']'},
                {id: 60, name: 'G#5', src: 'Ab5.mp3', keyCode: 'Backspace'},
                {id: 61, name: 'A5', src: 'A5.mp3', keyCode: '\\'},
                {id: 62, name: 'A#5', src: 'Bb5.mp3', keyCode: 'Insert'},
                {id: 63, name: 'B5', src: 'B5.mp3', keyCode: 'Delete'},
                {id: 64, name: 'C6', src: 'C6.mp3', keyCode: ''},
                {id: 65, name: 'C#6', src: 'Db6.mp3', keyCode: ''},
                {id: 66, name: 'D6', src: 'D6.mp3', keyCode: ''},
                {id: 67, name: 'D#6', src: 'Eb6.mp3', keyCode: ''},
                {id: 68, name: 'E6', src: 'E6.mp3', keyCode: ''},
                {id: 69, name: 'F6', src: 'F6.mp3', keyCode: ""},
                {id: 70, name: 'F#6', src: 'Gb6.mp3', keyCode: ''},
                {id: 71, name: 'G6', src: 'G6.mp3', keyCode: ''},
                {id: 72, name: 'G#6', src: 'Ab6.mp3', keyCode: ''},
                {id: 73, name: 'A6', src: 'A6.mp3', keyCode: ''},
                {id: 74, name: 'A#6', src: 'Bb6.mp3', keyCode: ''},
                {id: 75, name: 'B6', src: 'B6.mp3', keyCode: ''},
                {id: 76, name: 'C7', src: 'C7.mp3', keyCode: ''},
                {id: 77, name: 'C#7', src: 'Db7.mp3', keyCode: ''},
                {id: 78, name: 'D7', src: 'D7.mp3', keyCode: ''},
                {id: 79, name: 'D#7', src: 'Eb7.mp3', keyCode: ''},
                {id: 80, name: 'E7', src: 'E7.mp3', keyCode: ''},
                {id: 81, name: 'F7', src: 'F7.mp3', keyCode: ""},
                {id: 82, name: 'F#7', src: 'Gb7.mp3', keyCode: ''},
                {id: 83, name: 'G7', src: 'G7.mp3', keyCode: ''},
                {id: 84, name: 'G#7', src: 'Ab7.mp3', keyCode: ''},
                {id: 85, name: 'A7', src: 'A7.mp3', keyCode: ''},
                {id: 86, name: 'A#7', src: 'Bb7.mp3', keyCode: ''},
                {id: 87, name: 'B7', src: 'B7.mp3', keyCode: ''},
                {id: 88, name: 'C8', src: 'C8.mp3', keyCode: ''},
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
    transform: scale(0.8);
}

</style>