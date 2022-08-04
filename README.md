<!doctype html>
<html lang="en">

<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>tods list</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.0/dist/css/bootstrap.min.css" rel="stylesheet"
    integrity="sha384-gH2yIJqKdNHPEq0n4Mqa/HGKIhSkIHeL5AyhkYV8i59U5AR6csBvApHHNl/vI1Bx" crossorigin="anonymous">
</head>

<body>
  <nav class="navbar navbar-expand-lg bg-dark">
    <div class="container-fluid">
      <ul class="nav">
        <li class="nav-item">
          <a class="nav-link active" href="#">TODOs List</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Home</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">About</a>
        </li>
        <li class="nav-item">
          <a class="nav-link active" href="#">contect</a>
        </li>
      </ul>
      <a class="navbar-brand" href="#">todos list</a>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
          <li class="nav-item">
            <a class="nav-link active" aria-current="page" href="#">Home</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">about</a>
          </li>
          <li class="nav-item dropdown">
            <a class="nav-link dropdown-toggle" href="#" role="button" data-bs-toggle="dropdown" aria-expanded="false">
              Dropdown
            </a>
            <ul class="dropdown-menu">
              <li><a class="dropdown-item" href="#">Action</a></li>
              <li><a class="dropdown-item" href="#">Another action</a></li>
              <li>
                <hr class="dropdown-divider">
              </li>
              <li><a class="dropdown-item" href="#">Something else here</a></li>
            </ul>
          </li>
          <li class="nav-item">
            <a class="nav-link concact">concact</a>
          </li>
        </ul>
        <form class="d-flex" role="search">
          <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
          <button class="btn btn-outline-success" type="submit">Search</button>
        </form>
      </div>
    </div>
    </div>
  </nav>

  <div class="container my-4">
    <h2 class="text-center">TODOs List</h2>

    <div class="mb-3">
      <label for="title" class="form-label">title</label>
      <input type="text" class="form-control" id="title" aria-describedby="emailHelp">
      <div id="emailHelp" class="form-text">add a item to the list.</div>
    </div>
    <div class="form-group">
      <label for="description">Description</label>
      <textarea class="form-control" id="description" rows="3"></textarea>
    </div>
    <button type="submit" id="add" class="btn btn-primary my-2">add to list</button>
    <div id="items">
      <h2 class="my-1">Your Items</h2>
      <table class="table">
        <thead>
          <tr>
            <th scope="col">#</th>
            <th scope="col">Item Title</th>
            <th scope="col">Item Description</th>
            <th scope="col">Actions</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <th scope="row">1</th>
            <td>get some coffee</td>
            <td>you need coffee as you are a coder</td>
            <td><button class="btn btn-sn btn-primary">delete</button></td>
          </tr>
        </tbody>
      </table>

    </div>
  </div>

  <!-- optional savascripy -->
  <script>
      function update(){
        console.log("updating list......");
      tit = document.getElementById('title').value;
      desc = document.getElementById('description').value;
      if (localStorage.getItem('itemsJson') == null) {
        itemJsonArray = [];
        itemJsonArray.push([tit, desc]);
        localStorage.setItem('itemsJson', JSON.stringify(itemJsonArray))
      }
      else {
        itemJsinArrayStr = localStorage.getItem('itemsJson')
        itemJsonArray = JSON.parse(itemJsinArrayStr);
        itemJsonArray.push([tit, desc]);
        localStorage.setItem('itemsjson', JSON.stringify(itemJsonArray))
      }
      // populate the table
      let tablebody = document.getElementById("tablebody");
      let str = "";
      itemJsonArray.forEach((element, index) => {
       str += `
              <tr>
              <th scope="row">${index + 1}</th>
              <td>${element[0]}</td>
              <td>${element[1]}</td>
              <td><button class="btn btn-sm btn-primary">delete</button></td>
            </tr> `;

      });
            tablebody(foo !==null).innerHTML = str;

      }
    add = document.getElementById("add");
    add.addEventListener("click",update)
    update();
  </script>







</body>

</html>
