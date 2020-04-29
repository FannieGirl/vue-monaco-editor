<template>
	<div id="app">
		<MonacoEditor
				height="300"
				width="1200"
				class="vs"
				style="text-align: left;background-color: #fff"
				language="javascript"
				:code="code"
				:editorOptions="options"
				@mounted="onMounted"
				@codeChange="onCodeChange"
		>
		</MonacoEditor>
	</div>
</template>

<script>
	import MonacoEditor from 'vue-monaco-editor'

	export default {
		data() {
			return {
				code: '',
				editor:null,
				options: {
					theme: "vs",
					selectOnLineNumbers: true,
					roundedSelection: false,
					readOnly: false,
					automaticLayout: true,
					glyphMargin: true,
					showFoldingControls: "always",
					formatOnPaste: true,
					formatOnType: true,
					folding: true,
				}
			}
		},
		components: {
			MonacoEditor
		},
		methods:{
			onMounted (editor) {

				this.editor = editor;

			},

			onCodeChange(editor) {},
		}
	}
</script>
<style>
</style>
