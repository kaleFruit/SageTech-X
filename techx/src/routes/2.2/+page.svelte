<script>
  import Archive from "../archiveTemplate.svelte";

  const photos = [
    "2.2/p1.jpg",
    "2.2/p20.jpg",
    "2.2/p2.jpg",
    "2.2/p3.jpg",
    "2.2/p4.jpg",
    "2.2/p5.jpg",
    "2.2/p6.jpg",
    "2.2/p7.jpg",
    "2.2/p8.jpg",
    "2.2/p9.jpg",
    "2.2/p10.jpg",
    "2.2/p11.jpg",
    "2.2/p12.jpg",
    "2.2/p13.jpg",
    "2.2/p14.jpg",
    "2.2/p15.jpg",
    "2.2/p16.jpg",
    "2.2/p17.jpg",
    "2.2/p18.jpg",
    "2.2/p19.jpg",
  ];
</script>

<Archive {photos} edition={"Volume 2 Issue 2"} />
