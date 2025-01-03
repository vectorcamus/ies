---
{"dg-publish":true,"permalink":"/Untitled 1/"}
---

<table id="sortableTable" class="sortable">
  <thead>
    <tr>
      <th>Name</th>
      <th>Age</th>
      <th>Occupation</th>
    </tr>
  </thead>
<script>
  document.addEventListener("DOMContentLoaded", function() {
    const table = document.getElementById('sortableTable');
    const headers = table.querySelectorAll('th');
    
    headers.forEach((header, index) => {
      header.addEventListener('click', () => {
        const rows = Array.from(table.querySelectorAll('tbody tr'));
        const isAscending = header.classList.contains('asc');
        
        rows.sort((rowA, rowB) => {
          const cellA = rowA.children[index].innerText;
          const cellB = rowB.children[index].innerText;
          
          if (isAscending) {
            return cellA > cellB ? -1 : 1;
          } else {
            return cellA > cellB ? 1 : -1;
          }
        });
        
        rows.forEach(row => table.querySelector('tbody').appendChild(row));
        
        headers.forEach(h => h.classList.remove('asc', 'desc'));
        header.classList.toggle('asc', !isAscending);
        header.classList.toggle('desc', isAscending);
      });
    });
  });
</script>

  <tbody>
    <tr>
      <td>Alice</td>
      <td>28</td>
      <td>Engineer</td>
    </tr>
    <tr>
      <td>Bob</td>
      <td>35</td>
      <td>Designer</td>
    </tr>
    <tr>
      <td>Charlie</td>
      <td>22</td>
      <td>Developer</td>
    </tr>
    <tr>
      <td>Diana</td>
      <td>30</td>
      <td>Architect</td>
    </tr>
  </tbody>
</table>
