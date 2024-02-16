<script>
  import Router from "svelte-spa-router";
  import Gerbang from "./kunci/src/Gerbang.svelte";
  import data from "../android.json";
  import alasql from "alasql";

  alasql(/* sql */ `
  create localStorage database if not exists data;
  attach localStorage database data;
  
CREATE TABLE if not exists data.barang
(
  id         text     NOT NULL,
  nama       TEXT    NULL    ,
  harga_beli DECIMAL NULL    ,
  harga_jual DECIMAL NULL    ,
  banyak     INT     NULL    ,
  PRIMARY KEY (id)
);
  `);

  const routes = {};
</script>

<Gerbang namaAplikasi={data.title}>
  <Router {routes} />
</Gerbang>
