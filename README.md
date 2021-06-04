# PieChart

## 函數
|Property        | Usage           | Default  | Required |
|:------------- |:-------------|:-----:|:-----:|
| data | Chart data | none | yes |
| selector | DOM selector to attach the chart to | body | no |

## 需要資源
* [d3.js](https://d3js.org/)
* jquery
* bootstrap

## 用法

1. 引入d3、jquery、bootstrap 和 sacPlot.js、sacPlot.css
```javascript
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" crossorigin="anonymous">
<script src="https://code.jquery.com/jquery-3.3.1.min.js" crossorigin="anonymous"></script>
<script src="https://d3js.org/d3.v6.min.js"></script>
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.bundle.min.js" crossorigin="anonymous"></script>
<link href="path/to/sacPlot.css" rel="stylesheet">
<script src="path/to/sacPlot.js"></script>
```
2. pieChart().data()裡面填入物件陣列,每個物件都當作一組pie圖（不同年份的圖要分開畫的時候）

```javascript
// chart data example
    var data = {
                "count": {
                    "CWBSN": 1032,
                    "MAGNET": 68,
                    "GNSS": 72,
                    "GW": 27,
                    "TSMIP": 228,
                    "total": 1427
                },
                "file_size": {
                    "CWBSN": "153.17 GB",
                    "MAGNET": "7.91 GB",
                    "GNSS": "39.85 GB",
                    "GW": "3.93 GB",
                    "TSMIP": "138.34 GB",
                    "total": "343.21 GB"
                }
            };
    var title = '全體下載量';
    var obj = { data: data, title: title };
    
    var Data = [obj, obj];

    var chart = pieChart()
        .data(Data)
        .selector('.container');
    chart();
