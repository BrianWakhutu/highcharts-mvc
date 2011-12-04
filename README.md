# ASP.NET MVC Helpers for Highcharts

Write:

```console
@(
    Html.Highchart("myChart")
        .Title("Tickets per month")
        .AxisX("Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec")
        .AxisY("Products")
        .Series(
            new Serie("iPad", new int?[] { 0, 0, 0, 0, 0, 0, 16, 20, 40, 61, 100, 120 }),
            new Serie("MacBook", new int?[] { 616, 713, 641, 543, 145, 641, 134, 673, 467, 859, 456, 120 }),
            new Serie("iPhone", new int?[] { 10, 45, 75, 100, null, 546, 753, 785, 967, 135, 765, 245 })
        ).ToHtmlString()
)
```

Instead of:

```console
<div id="myChart"></div><script type="text/javascript">    var myChart;    $(document).ready(function () {        myChart = new Highcharts.Chart({				chart: {					renderTo: 'myChart'				}, title: {					text: 'Tickets per month'				}, xAxis: {					categories: ['Jan','Feb','Mar','Apr','May','Jun','Jul','Aug','Sep','Oct','Nov','Dec']				}, yAxis: {					title: { 						text: 'Products'					}				}, series: [					{ name:'iPad', data: [0,0,0,0,0,0,16,20,40,61,100,120] },					{ name:'MacBook', data: [616,713,641,543,145,641,134,673,467,859,456,120] },					{ name:'iPhone', data: [10,45,75,100,null,546,753,785,967,135,765,245] }				]        });    });</script>
```