<script>
  import Youtube from 'svelte-youtube-embed'
  let videoIdRaw = 'https://www.youtube.com/watch?v=dQw4w9WgXcQ'
  $: videoIdSanitized = new URL(videoIdRaw).searchParams.get('v')

</script>

<p>Paste a YouTube URL into the input field and play the video through an embedded version that respects your ad-blocker.</p>
<input type="text" bind:value={videoIdRaw} style="height:30px; width:100%;">
{#if videoIdSanitized !== '' && videoIdSanitized !== null}
  <Youtube id="{videoIdSanitized}" />
{/if}
