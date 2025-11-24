<script>
	let editor = $state({
		theme: 'dark',
		content: '<h1>Svelte</h1>',
	})
	function saveEditorState() {
		console.log(editor);
		const editorState = structuredClone($state.snapshot(editor));
		console.log(editorState);
	}
	saveEditorState();
</script>

<textarea class="editor"
	value={editor.content}
	oninput={(e) => {
		// this wont work - state.raw is being used
		editor.content = e.target.value	
	}}
	spellcheck="false"
	></textarea>

{@html editor.content}