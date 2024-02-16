<script>
  import {
    Button,
    Table,
    TableBody,
    TableBodyCell,
    TableBodyRow,
    TableHead,
    TableHeadCell,
    Modal,
  } from "flowbite-svelte";
  import Plus from "./icon/Plus.svelte";

  let defaultModal = true;
</script>

<div class="p-4">
  <Table hoverable={true}>
    <TableHead>
      <TableHeadCell>Nama Barang</TableHeadCell>
      <TableHeadCell>Harga Jual</TableHeadCell>
      <TableHeadCell>Banyak</TableHeadCell>
    </TableHead>
    <TableBody>
      <TableBodyRow>
        <TableBodyCell>Apple MacBook Pro 17"</TableBodyCell>
        <TableBodyCell>Sliver</TableBodyCell>
        <TableBodyCell>Laptop</TableBodyCell>
      </TableBodyRow>
    </TableBody>
  </Table>
</div>

<Modal title="Tambah Data" bind:open={defaultModal}>
  <svelte:fragment slot="footer">
    <Button>Simpan</Button>
  </svelte:fragment>
</Modal>

<Button
  pill={true}
  class="!p-2 fixed bottom-5 right-5"
  on:click={() => (defaultModal = true)}
>
  <Plus></Plus>
</Button>
