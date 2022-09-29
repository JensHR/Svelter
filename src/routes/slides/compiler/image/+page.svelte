<script lang="ts">
    import ImageSlider from "../../../../components/ImageSlider.svelte";

    const images = [
        '/TextComponentImage.png',
        '/TextComponentImageScriptFocus.png',
        '/TextComponentImageHTMLFocus.png',
        '/TextComponentImageStyleFocus.png',
    ];
</script>

<ImageSlider {images}/>
