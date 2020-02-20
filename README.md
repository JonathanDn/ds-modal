# ds-modal
A design system Vue.js modal with built-in slot to bind a vue component inside

# Usage Example
```
<template>
  <div>
      <cd-modal :config="editModalConfig"
                @closeModal="toggleCloseModal">
          <div class="title">Some Majestic Title!</div>
          <ds-input>...</ds-input>
          <ds-input>...</ds-input>
          <ds-input>...</ds-input>
          
          <div class="actions">
             <ds-btn>...</ds-btn>
             <ds-btn>...</ds-btn>
          </div>
      </cd-modal>
  </div>
</template>

<script>
    import cdModal from '../../../shared/components/cd-modal/cd-modal';
        export default {
            components: {
                cdModal
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

<style scoped lang="scss">...</style>
```
