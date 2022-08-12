<script setup lang="ts">
import { NButton, NUpload, NDataTable, type UploadFileInfo } from 'naive-ui'
import { ref } from 'vue'
import * as XLSX from 'xlsx' // vue3可用此引入

const tableData = ref([])
const columns = ref([
	{
		title: '姓名',
		key: '姓名',
	},
	{
		title: '部门',
		key: '基本信息',
	},
	{
		title: '星期',
		key: '__EMPTY',
	},
	{
		title: '日期',
		key: '班次信息',
	},
	{
		title: '上班时间',
		key: '第一次上班',
	},
	{
		title: '下班时间',
		key: '第一次下班',
	},
	{
		title: '上班状态',
		key: '__EMPTY_1',
	},
	{
		title: '下班状态',
		key: '__EMPTY_4',
	},
])
const pagination = ref()

function beforeUpload(data: { file: UploadFileInfo; fileList: UploadFileInfo[] }) {
	console.log(data.file)

	const fileReader = new FileReader()

	fileReader.onload = (e) => {
		const workbook = XLSX.read(e?.target?.result, {
			type: 'binary',
		})
		const wsname = workbook.SheetNames[0]
		const ws: any = XLSX.utils.sheet_to_json(workbook.Sheets[wsname])

		console.log(ws, 'ws')

		tableData.value = ws.filter((item: any) => item.姓名)
	}
	fileReader.readAsBinaryString(data.file.file as File)

	return false
}
</script>

<template>
	<main>
		<n-upload @before-upload="beforeUpload">
			<n-button>上传文件</n-button>
		</n-upload>
		<section>
			<n-data-table :columns="columns" :data="tableData" :pagination="pagination" :bordered="false" />
		</section>
	</main>
</template>

<style lang="less" scoped>
main {
	span {
		color: red;
	}
	p {
		color: blue;
	}
}
</style>
