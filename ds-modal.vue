<template>
    <div class="ds-modal-overlay"
         :style="getComputedStyles">
       <div class="modal-background-click"
            @click="clickOutsideModal">
           <div class="modal-box" @click.stop>
               <slot></slot>
           </div>
       </div>
    </div>
</template>

<script>
    export default {
        name: 'dsModal',
		props: ['config'],
        components: {
        
        },
        data: function() {
        	return {
				width: 600,
				height: 300
            }
        },
		computed: {
			getComputedStyles() {
				return [
					{'--ds-modal-width': this.width + 'px'},
					{'--ds-modal-height': this.height + 'px'},
				];
			},
		},
        methods: {
			setStyles() {
				if (this.config) {
					if (this.config.width) {
						this.width = this.config.width;
					}
					if (this.config.height) {
						this.height = this.config.height;
					}
				}
			},
            clickOutsideModal() {
				this.$emit('closeModal');
            },
            escapeKeyListener(evt) {
				if (evt.key.toLowerCase() === 'escape') {
					this.clickOutsideModal();
                }
            },
            appendEscapeListener() {
				document.addEventListener('keyup', this.escapeKeyListener);
            },
            ditachEscapeListener() {
				document.removeEventListener('keyup', this.escapeKeyListener);
            }
            
        },
        created() {
        	this.appendEscapeListener();
			this.setStyles();
        },
        destroyed() {
        	this.ditachEscapeListener();
        }
    }
</script>

<style scoped
       lang="scss">
    @import "./ds-modal";
</style>
