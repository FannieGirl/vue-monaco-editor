<template>
	<div ref="container" style="width:800px;height:600px;border:1px solid grey;text-align: left"></div>
</template>

<script>
	import * as monaco from "monaco-editor"; // 包体很大了 但是demo可以跑起来

	export default{
		mounted() {
			var editor = monaco.editor.create(this.$refs.container, {
				value: [
					'function x() {',
					'\tconsole.log("Hello world!");',
					'}'
				].join('\n'),
				language: 'javascript',
				minimap:{
					enabled:false
				},
				selectOnLineNumbers: true,
				roundedSelection: false,
				cursorStyle: 'line', // 光标样式
				automaticLayout: false, // 自动布局
				glyphMargin: true, // 字形边缘
				useTabStops: false,
				fontSize: 16, // 字体大小
				autoIndent: false //自动布局
			});
		}
	}
</script>
