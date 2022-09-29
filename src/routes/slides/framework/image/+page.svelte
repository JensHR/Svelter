<script lang="ts">
    import ImageSlider from "../../../../components/ImageSlider.svelte";

    const images = [
        '/FolderStructure.png',
        '/FolderStructureComponents.png',
        '/FolderStructureRoutes.png'
    ];
</script>

<ImageSlider {images}/>