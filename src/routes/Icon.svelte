<script>
  export let params;
  import Icon from 'svelte-awesome';
  import * as icons from 'svelte-awesome/icons';

  $: name = params.name;
  $: style = params.style;
  $: iconData = icons[name];

  let extraProps;
  $: if (style) {
    extraProps = [];
    extraProps[style] = true;
  } else {
    extraProps = [];
  }

  $: console.log("X", params, name, style)


</script>

<style>
  * {
    text-align: center;
  }
</style>

<header>
  Icon: {name} {style || ""}
</header>

<div>
  <Icon data={iconData} {...extraProps}/>
</div>
