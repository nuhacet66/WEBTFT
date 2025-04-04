<script>
  let data = [
    { name: "John", age: 30 },
    { name: "Jane", age: 25 },
    { name: "Jake", age: 35 },
  ];
</script>

<div class="p-8 space-y-6">
  <h1 class="text-3xl font-bold text-center text-blue-500">Dashboard</h1>
  <table class="min-w-full table-auto border-collapse">
    <thead>
      <tr class="bg-gray-200">
        <th class="px-4 py-2 text-left font-semibold text-gray-700">Name</th>
        <th class="px-4 py-2 text-left font-semibold text-gray-700">Age</th>
      </tr>
    </thead>
    <tbody>
      {#each data as { name, age }}
        <tr class="border-b">
          <td class="px-4 py-2 text-gray-800">{name}</td>
          <td class="px-4 py-2 text-gray-800">{age}</td>
        </tr>
      {/each}
    </tbody>
  </table>
</div>
