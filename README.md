# ds-modal
A design system Vue.js modal with built-in slot to bind a vue component inside.

# Usage Example
```
<template>
  <div>
      <ds-modal :config="editModalConfig"
                @closeModal="toggleCloseModal">
                
           // Here you put all this components' template+data+props+methods used in this file(for example a some-form.vue compeonnt)
          <div class="title">Some Majestic Title!</div>
          <ds-input>...</ds-input>
          <ds-input>...</ds-input>
          <ds-input>...</ds-input>
          
          <div class="actions">
             <ds-btn>...</ds-btn>
             <ds-btn>...</ds-btn>
          </div>
          
          
      </ds-modal>
  </div>
</template>

<script>
    import dsModal from '../../../shared/components/ds-modal/ds-modal';
        export default {
            components: {
                dsModal
            },
            data() {
                return {
                    editModalConfig: {
      	                width: 800,
                        height: 550
                    }
                }
            }
            methods: {
                toggleCloseModal() {
                    this.$emit('toggleCloseModal');
                }
            }
        }
</script>

<style lang="scss">...</style>
```

## Supported Properties
- `width` type `number`
- `height` type `number`

### Notes
* The modal component does not have a `scoped` style attribute on prupose, to support custimzing the styling of passed template into the modal slot.

---
👨‍💻 Follow me on [Twitter](https://twitter.com/jodoron).

### Donation
If this project helped you reduce development time, you can buy me a cup of coffee :)

* Paypal - yonidn7@gmail.com
