<script>
    import { currentColor } from '../stores'
    let colorNow
    currentColor.subscribe((value) => {
        colorNow = value
    })

    const pallete = [
        'FFFFFF',
        'E4E4E4',
        '888888',
        '222222',
        'FFA7D1',
        'E50000',
        'E59500',
        'A06A42',
        'E5D900',
        '94E044',
        '02BE01',
        '00D3DD',
        '0083C7',
        '0000EA',
        '820080',
        'CF6EE4',
    ]

    const changeColor = (e) => {
        currentColor.set(e.target.className.split(' ')[0])
    }
</script>

<div class="pallete">
    <p>
        Current color : <button
            style="background-color:#{colorNow};margin:0 10px;padding:20px;border-radius:50%"
        />
    </p>
    {#each pallete as color}
        <button
            on:click={changeColor}
            class={color}
            style="background-color:#{color}"
        />
    {/each}
</div>

<style>
    button {
        padding: 15px 25px;
        margin: 5px;
        border: none;
    }
    p {
        font-family: 'Righteous', cursive;
        letter-spacing: 1px;
        font-size: 18px;
    }
</style>
