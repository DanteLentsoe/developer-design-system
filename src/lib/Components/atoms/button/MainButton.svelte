<script>
  import './button.css'
  import { createEventDispatcher } from 'svelte'
  /**
   * Is this the principal call to action on the page?
   */
  export let primary = false

  /**
   * What background color to use
   */
  export let backgroundColor
  /**
   * How large should the button be?
   */
  export let size = 'medium'
  /**
   * Button contents
   */
  export let label = ''

    let mode = primary
      ? 'primary'
      : 'secondary'

  let style = backgroundColor ? `background-color: ${backgroundColor}` : ''

  const dispatch = createEventDispatcher()

  /**
	 * Optional click handler
	 * @param {any} event
	 */
  function onClick(event) {
    dispatch('click', event)
  }
</script>

<button
  type="button"
  class={['neumorphic', `${mode}`, `variation2${size}`].join(' ')}
  {style}
  on:click={onClick}>
  {label}
</button>
