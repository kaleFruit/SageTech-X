<script>
  import Archive from "../archiveTemplate.svelte";

  const photos = [
    "2.1/p1.jpg",
    "2.1/p20.jpg",
    "2.1/p2.jpg",
    "2.1/p3.jpg",
    "2.1/p4.jpg",
    "2.1/p5.jpg",
    "2.1/p6.jpg",
    "2.1/p7.jpg",
    "2.1/p8.jpg",
    "2.1/p9.jpg",
    "2.1/p10.jpg",
    "2.1/p11.jpg",
    "2.1/p12.jpg",
    "2.1/p13.jpg",
    "2.1/p14.jpg",
    "2.1/p15.jpg",
    "2.1/p16.jpg",
    "2.1/p17.jpg",
    "2.1/p18.jpg",
    "2.1/p19.jpg",
  ];
</script>

<Archive {photos} edition={"Volume 2 Issue 1"} />
