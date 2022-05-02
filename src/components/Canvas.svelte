<script>
    import { currentColor } from '../stores'

    let colorNow
    currentColor.subscribe((value) => {
        colorNow = value
    })

    const width = 50

    window.onload = () => {
        const count = width * width
        const canvas = document.getElementById('canvas')
        canvas.style.gridTemplateColumns = `repeat(${width}, 1fr)`
        canvas.style.gridTemplateRows = `repeat(${width}, 1fr)`
        for (let i = 0; i < count; i++) {
            const div = document.createElement('div')
            div.classList.add('grid-element')
            div.addEventListener('click', () => {
                div.style.backgroundColor = `#${colorNow}`
            })
            canvas.appendChild(div)
        }
    }
</script>

<div class="canvasContainer">
    <div id="canvas" />
</div>

<style>
    .canvasContainer {
        width: 100%;
        text-align: center;
        overflow: scroll;
    }

    .canvasContainer {
        -ms-overflow-style: none; /* Internet Explorer 10+ */
        scrollbar-width: none; /* Firefox */
    }
    .canvasContainer::-webkit-scrollbar {
        display: none; /* Safari and Chrome */
    }

    #canvas {
        border: 1px solid #fff;
        display: grid;
        color: black;
        margin: 30px auto;
        height: 1000px;
        width: 1000px;
        background-color: #fff;
    }
</style>
