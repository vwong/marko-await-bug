# Marko await bug

This repo demonstrates a bug with Marko `<await>` when the fragment being awaited is inside a `<table>`.

The expected result is:
```
<div>
  <div>div contents</div>
</div>

<table>
  <tbody>
    <tr>
      <td>table contents</td>
    </tr>
  </tbody>
</table>
```

But when using `<await>`, the result is:
```
<div>
  <div>div contents</div>
</div>
row contents
<table>
  <tbody>
    <tr>
      <td>table placeholder</td>
    </tr>
  </tbody>
</table>
```

It looks like the substitution fails.
