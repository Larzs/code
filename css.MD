## CSS

### Loader

```markdown
<div class="spinner">
    <div class="spinner__slice"></div>
    <div class="spinner__slice"></div>
    <div class="spinner__slice"></div>
</div>
```

<style>
.spinner, .spinner * {
  box-sizing: border-box;
}
  
.spinner {
  height: 35px;
  width: 35px;
  border-radius: 50%;
  perspective: 800px;
}
</style>

<div class="spinner">
    <div class="spinner__slice"></div>
    <div class="spinner__slice"></div>
    <div class="spinner__slice"></div>
</div>
