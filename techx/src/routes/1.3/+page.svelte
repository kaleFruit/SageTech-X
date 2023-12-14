<script>
  import Archive from "../archiveTemplate.svelte";

  const photos = [
    "1.3/p1.jpg",
    "1.3/p20.jpg",
    "1.3/p2.jpg",
    "1.3/p3.jpg",
    "1.3/p4.jpg",
    "1.3/p5.jpg",
    "1.3/p6.jpg",
    "1.3/p7.jpg",
    "1.3/p8.jpg",
    "1.3/p9.jpg",
    "1.3/p10.jpg",
    "1.3/p11.jpg",
    "1.3/p12.jpg",
    "1.3/p13.jpg",
    "1.3/p14.jpg",
    "1.3/p15.jpg",
    "1.3/p16.jpg",
    "1.3/p17.jpg",
    "1.3/p18.jpg",
    "1.3/p19.jpg",
  ];
</script>

<Archive {photos} edition={"Volume 1 Issue 3"} />
