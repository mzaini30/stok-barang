<script>
  import Router from "svelte-spa-router";
  import Gerbang from "./kunci/src/Gerbang.svelte";
  import data from "../android.json";
  import alasql from "alasql";
  import Beranda from "./Beranda.svelte";

  alasql(/* sql */ `
  create localStorage database if not exists data;
  attach localStorage database data;
  create table if not exists data.barang (id text, nama text, harga_beli number, harga_jual number, banyak number);
  `);

  const routes = {
    "/": Beranda,
  };
</script>

<Gerbang namaAplikasi={data.title}>
  <Router {routes} />
</Gerbang>
