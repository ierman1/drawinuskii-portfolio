<template>
    <footer class="footer">
        <p class="desc">
            <span class="name">Drawinuskii</span>
            <a href=""><font-awesome-icon icon="fa-brands fa-instagram" /> Instagram</a> · 
            <a href=""><font-awesome-icon icon="fa-brands fa-artstation" /> ArtStation</a>
        </p>
        <span class="author">Developed by <a href="https://github.com/ierman1">@ierman1</a> - 2022</span>
    </footer>
</template>

<style lang="scss">

	.footer {
        background-color: $primary-color;
        opacity: 80%;
        padding: 3rem;
        text-align: center;

        * {
            color: $light-color;
        }

        .desc {
            span {
                display: block;
            }
        }

        .name {
            font-weight: bold;
        }
    }

</style>