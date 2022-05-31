<script>
  import SvelteTable from "svelte-table"
import TableCell from "./TableCell.svelte";

  const rows = [
    { id: 1, first_name: "Marilyn", last_name: "Monroe", pet: "dog" },
    { id: 2, first_name: "Abraham", last_name: "Lincoln", pet: "dog" },
    { id: 3, first_name: "Mother", last_name: "Teresa", pet: "" },
    { id: 4, first_name: "John F.", last_name: "Kennedy", pet: "dog" },
    { id: 5, first_name: "Martin Luther", last_name: "King", pet: "dog" },
    { id: 6, first_name: "Nelson", last_name: "Mandela", pet: "cat" },
    { id: 7, first_name: "Winston", last_name: "Churchill", pet: "cat" },
    { id: 8, first_name: "George", last_name: "Soros", pet: "bird" },
    { id: 9, first_name: "Bill", last_name: "Gates", pet: "cat" },
    { id: 10, first_name: "Muhammad", last_name: "Ali", pet: "dog" },
    { id: 11, first_name: "Mahatma", last_name: "Gandhi", pet: "bird" },
    { id: 12, first_name: "Margaret", last_name: "Thatcher", pet: "cat" },
    { id: 13, first_name: "Christopher", last_name: "Columbus", pet: "dog" },
    { id: 14, first_name: "Charles", last_name: "Darwin", pet: "dog" },
    { id: 15, first_name: "Elvis", last_name: "Presley", pet: "dog" },
    { id: 16, first_name: "Albert", last_name: "Einstein", pet: "dog" },
    { id: 17, first_name: "Paul", last_name: "McCartney", pet: "cat" },
    { id: 18, first_name: "Queen", last_name: "Victoria", pet: "dog" },
    { id: 19, first_name: "Pope", last_name: "Francis", pet: "cat" },
  ];

  const columnTitles = {
    id: "ID",
    first_name: "First name",
    last_name: "Last name",
    pet: "Pet",
  }

  const columns = [];

  for (const key in rows[0]) {
    columns.push({
      key: key,
      title: columnTitles[key],
      value: v => v[key],
      headerClass: "header",
      class: "cell",
      renderComponent: TableCell,
      sortable: true,
    })
  };
</script>

<div>
  <SvelteTable classNameTable={["table table-striped"]} classNameRow={"table-row"} columns="{columns}" rows="{rows}" />
</div>

<style>
  div {
    max-height: 640px;
    overflow-y: scroll;
  }

  div::-webkit-scrollbar-thumb {
    background-color: #d9dcde;
    border-radius: 4px;
    border: 1px solid #fafafa;
  }

  div::-webkit-scrollbar {
    height: 8px;
    width: 8px;
  }

  div::-webkit-scrollbar-track {
    margin-block: 1px;
    background-color: #fafafa;
  }

  :global(.table) {
    border-spacing: 0;
  }

  :global(.table tr) {
    display: grid;
    grid-template-columns: 8ch 1fr 1fr 1fr;
  }
  
  :global(.table > thead) {
    top: 0;
    position: sticky;
  }

  :global(.table-striped > tbody > tr:nth-of-type(even)) {
    background-color: #fafafa;
  }

  :global(.table > tbody > tr:hover) {
    background-color: #ebf7ff;
    cursor: pointer;
  }

  :global(.cell) {
    padding: 16px 8px;
    vertical-align: middle;
    color: #0071bd;
    font-size: 14px;
  }

  :global(.header) {
    padding: 16px 8px;
    border-bottom: 1px dashed #d9dcde;
    background-color: #fff;
    vertical-align: middle;
    text-align: left;
    font-size: 14px;
    font-weight: 600;
    color: #6a6c6d;
    user-select: none;
  }
</style>