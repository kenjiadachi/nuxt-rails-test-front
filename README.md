# README

QueryBuilder周りでエラーが出たときは以下を参考にしてください。
https://github.com/nuxt/content/issues/31

`node_modules/@nuxt/content/lib/templates/query-builder.js`の最終行を以下のように変更

```
module.exports = QueryBuilder
↓
export default QueryBuilder
```