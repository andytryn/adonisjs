## 🪔 Adding sweetalert2

Install sweetalert2

```bash
npm i sweetalert2
```

Add types to TypeScript project

```bash
{
  //...tsconfig.json
  "types": [
    "sweetalert2"
  ],
}
```

Add to View index.svelte

```bash
<script>
  // ES6 Modules or TypeScript
  import Swal from "sweetalert2";

  Swal.fire({
    title: "Error!",
    text: "Do you want to continue",
    icon: "error",
    confirmButtonText: "Cool",
  });
</script>
```
