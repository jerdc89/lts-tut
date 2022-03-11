<script>
    export let title = "Ninja Gaming"
</script>

<div class="title">
    <img src="/VdV.svg" alt="vdv logo">
    <h1>{title}</h1>
</div>

<style>
    .title {
        display: flex;
    }
    .title img {
        height: 40px;
        width: 40px;
        display: inline-block;
        align-self: center;
        filter: invert(88%) sepia(18%) saturate(886%) hue-rotate(199deg) brightness(100%) contrast(90%);
    }
    .title h1 {
        margin-left: 20px;
    }
</style>