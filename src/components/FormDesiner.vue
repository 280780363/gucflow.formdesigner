<template>
    <div>
        <el-button type="primary" icon="el-icon-edit"></el-button>
        <el-button type="primary" icon="el-icon-share"></el-button>
        <el-button type="primary" icon="el-icon-delete"></el-button>
        <el-button type="primary" icon="el-icon-search">搜索</el-button>
        <el-button type="primary">上传<i class="el-icon-upload el-icon--right"></i></el-button>
        <HotTable :settings="settings"></HotTable>
    </div>
</template>
<script>
import {HotTable} from '@handsontable/vue';
import Handsontable from 'handsontable';
import 'handsontable/dist/handsontable.full.css';
import Vue from 'vue';

export default {
    data() {
        return {
            settings: {
                data: [
                    {
                        title:
                            "<a href='http://www.amazon.com/Professional-JavaScript-Developers-Nicholas-Zakas/dp/1118026691'>Professional JavaScript for Web Developers</a>",
                        description:
                            "This <a href='http://bit.ly/sM1bDf'>book</a> provides a developer-level introduction along with more advanced and useful features of <b>JavaScript</b>.",
                        comments:
                            'I would rate it &#x2605;&#x2605;&#x2605;&#x2605;&#x2606;',
                        cover:
                            'http://ecx.images-amazon.com/images/I/51bRhyVTVGL._SL50_.jpg',
                    },
                    {
                        title:
                            "<a href='http://shop.oreilly.com/product/9780596517748.do'>JavaScript: The Good Parts</a>",
                        description:
                            'This book provides a developer-level introduction along with <b>more advanced</b> and useful features of JavaScript.',
                        comments: 'This is the book about JavaScript',
                        cover:
                            'http://ecx.images-amazon.com/images/I/51gdVAEfPUL._SL50_.jpg',
                    },
                    {
                        title:
                            '<el-button type="primary" icon="el-icon-edit"></el-button>',
                        description:
                            '<em>JavaScript: The Definitive Guide</em> provides a thorough description of the core <b>JavaScript</b> language and both the legacy and standard DOMs implemented in web browsers.',
                        comments:
                            "I've never actually read it, but the <a href='http://shop.oreilly.com/product/9780596805531.do'>comments</a> are highly <strong>positive</strong>.",
                        cover:
                            'http://ecx.images-amazon.com/images/I/51VFNL4T7kL._SL50_.jpg',
                    },
                ],
                colWidths: [200, 200, 200, 80],
                colHeaders: ['Title', 'Description', 'Comments', 'Cover'],
                rowHeaders: true,
                columns: [
                    {data: 'title', renderer: 'html'},
                    {data: 'description', renderer: 'html'},
                    {data: 'comments', renderer: 'html'},
                    {
                        data: 'cover',
                        renderer: function(
                            instance,
                            td,
                            row,
                            col,
                            prop,
                            value,
                            cellProperties
                        ) {
                            debugger;
                        },
                    },
                ],
            },
        };
    },
    components: {
        HotTable,
    },
};
</script>
<style lang="less" scoped>
</style>


