# customize-needs
擁抱react community開發者提供的component，提升開發速度

同時能夠根據ＰＭ提出的需求高度客製！

from this:

![1627392844102](https://user-images.githubusercontent.com/66729413/127165738-d6b5c2fb-4043-46c3-9891-8d00fb2ccb5c.jpg)


to this:
![1627393752073](https://user-images.githubusercontent.com/66729413/127165762-56a0e172-9444-4830-8642-f1592bd6eba5.jpg)

-------------------------------------------------------------------------------------------------------------------------------------------------

# download-file-by-sheetJs

專案需要將查詢後的資料輸出ods的功能
用sheet.js 將後端回傳的json資料
輸出成ods

![1627395987539](https://user-images.githubusercontent.com/66729413/127171660-629a4473-5a5d-4c2a-9f95-929c4cc8dedf.jpg)

```
var XLSX = require('xlsx');
const tableHead = ["項目一", "項目二", "項目三", "項目四", "項目五",  "項目六", "項目七"]
//輸出不需要Guid欄位-從陣列中刪除
   result.resultObject.blogs.forEach(function (v) { delete v.guid });
   if (result.isSucess) {
   if (typeof XLSX == 'undefined') XLSX = require('xlsx');
   var ws = XLSX.utils.json_to_sheet(result.resultObject.blogs);

   const wb = XLSX.WorkBook = XLSX.utils.book_new();
   //表格中項目名稱
   ws.A1.v = tableHead[0]
   ws.B1.v = tableHead[1]
   ws.C1.v = tableHead[2]
   ws.D1.v = tableHead[3]
   ws.E1.v = tableHead[4]
   ws.F1.v = tableHead[5]
   ws.G1.v = tableHead[6]


   XLSX.utils.book_append_sheet(wb, ws, "Table Export2");
   XLSX.writeFile(wb, `下載檔名_共${totalCount}筆.ods`);
 }
```
