# cashir-system 
<script>
  const validUsername = "danyal";
  const validPassword = "danyal12345";

  function login() {
    const user = document.getElementById("username").value;
    const pass = document.getElementById("password").value;
    if (user === validUsername && pass === validPassword) {
      document.getElementById("login").classList.add("hidden");
      document.getElementById("app").classList.remove("hidden");
    } else {
      document.getElementById("loginError").innerText = "ناوی بەکارهێنەر یان پاسۆرد هەڵەیە";
    }
  }

  let total = 0;

  function addItem() {
    const code = document.getElementById("code").value;
    const name = document.getElementById("name").value;
    const price = parseInt(document.getElementById("price").value);
    const quantity = parseInt(document.getElementById("quantity").value);
    const subtotal = price * quantity;

    total += subtotal;

    const row = `<tr><td>${code}</td><td>${name}</td><td>${price}</td><td>${quantity}</td><td>${subtotal}</td></tr>`;
    document.querySelector("#items tbody").insertAdjacentHTML("beforeend", row);
    document.getElementById("total").innerText = `نرخی گشتی: ${total} دینار`;

    document.getElementById("code").value = "";
    document.getElementById("name").value = "";
    document.getElementById("price").value = "";
    document.getElementById("quantity").value = "";
  }
</script>
