# DescribeDomainRegionData

Queries the geographic distribution of users. The data is collected at an interval of one day. You can query data collected within the last 90 days.

**When you call this operation, note that:**

-   If you do not set **StartTime** or **EndTime**, data collected within the last **24** hours is queried. If you set both **StartTime** and **EndTime**, data collected within the specified time range is queried.
-   The maximum number of times that each user can call this operation per second is 100.

**Note:** You may fail to query the latest data. If you need to query data collected within the last day, we recommend that you query the data on the next day.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Cdn&api=DescribeDomainRegionData&type=RPC&version=2018-05-10)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeDomainRegionData|The operation that you want to perform. Set the value to **DescribeDomainRegionData**. |
|DomainName|String|No|test.test.com|The accelerated domain names. Separate multiple domain names with commas \(,\).

By default, this operation queries the geographic distribution of users for all accelerated domain names. |
|StartTime|String|No|2015-12-05T12:00:00Z|The start of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|EndTime|String|No|2015-12-07T12:00:00Z|The end of the time range to query. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC.

The end time must be later than the start time. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|DataInterval|String|86400|The time interval between the data entries. Unit: seconds. |
|DomainName|String|test.test.com|The accelerated domain name. |
|EndTime|String|2015-12-07T12:00:00Z|The end of the time range that was queried. |
|RequestId|String|2E5AD83F-BD7B-462E-8319-2E30E305519A|The ID of the request. |
|StartTime|String|2015-12-05T12:00:00Z|The beginning of the time range that was queried. |
|Value|Array of RegionProportionData| |The proportions of requests initiated from each area. |
|RegionProportionData| | | |
|AvgObjectSize|String|800019.0|The average response size. Unit: bytes. |
|AvgResponseRate|String|154.3345765545624|The average response rate. Unit: byte/s. |
|AvgResponseTime|String|5183.666666666667|The average response time. Unit: milliseconds. |
|Bps|String|380.9614285714286|The bandwidth value. |
|BytesProportion|String|0.003544181046236794|The proportion of bytes transferred from each area. For example, a value of 90 indicates that 90% of the bytes are transferred from the specified area. |
|Proportion|String|0.01155980271270037|The proportion of visits from each area. For example, a value of 90 indicates that 90% of the visits are from the specified area. |
|Qps|String|5.9523809523809524E-5|The number of queries per second. |
|Region|String|Japan|The area. |
|RegionEname|String|japan|The name of the area. |
|ReqErrRate|String|0.0|The request error rate. A value of 90 indicates that 90% of the requests encountered errors. |
|TotalBytes|String|2400057|The total amount of network traffic. |
|TotalQuery|String|3|The total number of queries. |

## Examples

Sample requests

```
http://cdn.aliyuncs.com/?Action=DescribeDomainRegionData
&DomainName=example.com
&StartTime=2015-12-05T12:00:00Z
&EndTime=2015-12-07T12:00:00Z
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeDomainRegionDataResponse>
      <Value>
            <RegionProportionData>
                  <Bps>380.9614285714286</Bps>
                  <Proportion>0.01155980271270037</Proportion>
                  <ReqHitRate>100.0</ReqHitRate>
                  <TotalBytes>2400057</TotalBytes>
                  <BytesProportion>0.003544181046236794</BytesProportion>
                  <ByteHitRate>100.0</ByteHitRate>
                  <TotalQuery>3</TotalQuery>
                  <RegionEname></RegionEname>
                  <Region>Japan</Region>
                  <AvgResponseRate>154.3345765545624</AvgResponseRate>
                  <AvgObjectSize>800019.0</AvgObjectSize>
                  <ReqErrRate>0.0</ReqErrRate>
                  <Qps>5.9523809523809524E-5</Qps>
                  <AvgResponseTime>5183.666666666667</AvgResponseTime>
            </RegionProportionData>
            <RegionProportionData>
                  <Bps>25110.431412698414</Bps>
                  <Proportion>0.31211467324291</Proportion>
                  <ReqHitRate>100.0</ReqHitRate>
                  <TotalBytes>158195717</TotalBytes>
                  <BytesProportion>0.23360872886644055</BytesProportion>
                  <ByteHitRate>100.0</ByteHitRate>
                  <TotalQuery>81</TotalQuery>
                  <RegionEname>xizang</RegionEname>
                  <Region>Tibet Autonomous Region</Region>
                  <AvgResponseRate>1397.1430909315718</AvgResponseRate>
                  <AvgObjectSize>1953033.5543209878</AvgObjectSize>
                  <ReqErrRate>0.0</ReqErrRate>
                  <Qps>0.0016071428571428571</Qps>
                  <AvgResponseTime>1397.8765432098764</AvgResponseTime>
            </RegionProportionData>
            <RegionProportionData>
                  <Bps>40343.86242857143</Bps>
                  <Proportion>0.33908754623921084</Proportion>
                  <ReqHitRate>100.0</ReqHitRate>
                  <TotalBytes>254166333</TotalBytes>
                  <BytesProportion>0.37532921137846464</BytesProportion>
                  <ByteHitRate>100.0</ByteHitRate>
                  <TotalQuery>88</TotalQuery>
                  <RegionEname>zhongqing</RegionEname>
                  <Region>Chongqing</Region>
                  <AvgResponseRate>787.8073097249128</AvgResponseRate>
                  <AvgObjectSize>2888253.7875</AvgObjectSize>
                  <ReqErrRate>0.0</ReqErrRate>
                  <Qps>0.001746031746031746</Qps>
                  <AvgResponseTime>3666.193181818182</AvgResponseTime>
            </RegionProportionData>
            <RegionProportionData>
                  <Bps>38835.2834920635</Bps>
                  <Proportion>0.37376695437731194</Proportion>
                  <ReqHitRate>100.0</ReqHitRate>
                  <TotalBytes>244662286</TotalBytes>
                  <BytesProportion>0.3612945179094354</BytesProportion>
                  <ByteHitRate>100.0</ByteHitRate>
                  <TotalQuery>97</TotalQuery>
                  <RegionEname>tianjin</RegionEname>
                  <Region>Tianjin</Region>
                  <AvgResponseRate>1711.4277340197823</AvgResponseRate>
                  <AvgObjectSize>2522291.608247423</AvgObjectSize>
                  <ReqErrRate>0.0</ReqErrRate>
                  <Qps>0.0019246031746031746</Qps>
                  <AvgResponseTime>1473.7938144329896</AvgResponseTime>
            </RegionProportionData>
            <RegionProportionData>
                  <Bps>69358.64117460318</Bps>
                  <Proportion>0.5895499383477188</Proportion>
                  <ReqHitRate>99.34640522875817</ReqHitRate>
                  <TotalBytes>436959439</TotalBytes>
                  <BytesProportion>0.6452610763393265</BytesProportion>
                  <ByteHitRate>99.99291705425965</ByteHitRate>
                  <TotalQuery>153</TotalQuery>
                  <RegionEname>qinghai</RegionEname>
                  <Region>Qinghai</Region>
                  <AvgResponseRate>1210.9708048576356</AvgResponseRate>
                  <AvgObjectSize>2855944.0483660134</AvgObjectSize>
                  <ReqErrRate>0.0</ReqErrRate>
                  <Qps>0.0030357142857142857</Qps>
                  <AvgResponseTime>2358.392156862745</AvgResponseTime>
            </RegionProportionData>
            <RegionProportionData>
                  <Bps>66239.68633333335</Bps>
                  <Proportion>0.6473489519112207</Proportion>
                  <ReqHitRate>100.0</ReqHitRate>
                  <TotalBytes>417310023</TotalBytes>
                  <BytesProportion>0.6162446463192347</BytesProportion>
                  <ByteHitRate>99.99999999999999</ByteHitRate>
                  <TotalQuery>168</TotalQuery>
                  <RegionEname>Hainan</RegionEname>
                  <Region>Hainan</Region>
                  <AvgResponseRate>324.9427676080411</AvgResponseRate>
                  <AvgObjectSize>2483988.2375000003</AvgObjectSize>
                  <ReqErrRate>0.0</ReqErrRate>
                  <Qps>0.0033333333333333335</Qps>
                  <AvgResponseTime>7644.386904761905</AvgResponseTime>
            </RegionProportionData>
            <RegionProportionData>
                  <Bps>62071.644380952384</Bps>
                  <Proportion>0.7745067817509248</Proportion>
                  <ReqHitRate>99.50248756218906</ReqHitRate>
                  <TotalBytes>391051359</TotalBytes>
                  <BytesProportion>0.5774682921278322</BytesProportion>
                  <ByteHitRate>99.99983347455928</ByteHitRate>
                  <TotalQuery>201</TotalQuery>
                  <RegionEname>shanghai</RegionEname>
                  <Region>Shanghai</Region>
                  <AvgResponseRate>1319.43005273653</AvgResponseRate>
                  <AvgObjectSize>1945529.152238806</AvgObjectSize>
                  <ReqErrRate>0.0</ReqErrRate>
                  <Qps>0.0039880952380952385</Qps>
                  <AvgResponseTime>1474.5223880597016</AvgResponseTime>
            </RegionProportionData>
            <RegionProportionData>
                  <Bps>86967.5461111111</Bps>
                  <Proportion>0.9286374845869297</Proportion>
                  <ReqHitRate>96.2655601659751</ReqHitRate>
                  <TotalBytes>547895540</TotalBytes>
                  <BytesProportion>0.8090811968039774</BytesProportion>
                  <ByteHitRate>98.60251863101267</ByteHitRate>
                  <TotalQuery>241</TotalQuery>
                  <RegionEname>beijing</RegionEname>
                  <Region>Beijing</Region>
                  <AvgResponseRate>1223.3552235839977</AvgResponseRate>
                  <AvgObjectSize>2273425.479253112</AvgObjectSize>
                  <ReqErrRate>0.0</ReqErrRate>
                  <Qps>0.004781746031746032</Qps>
                  <AvgResponseTime>1858.3526970954356</AvgResponseTime>
            </RegionProportionData>
            <RegionProportionData>
                  <Bps>228242.86641269844</Bps>
                  <Proportion>1.9690197287299631</Proportion>
                  <ReqHitRate>100.0</ReqHitRate>
                  <TotalBytes>1437930058</TotalBytes>
                  <BytesProportion>2.1234014270475434</BytesProportion>
                  <ByteHitRate>100.0</ByteHitRate>
                  <TotalQuery>511</TotalQuery>
                  <RegionEname>ningxia</RegionEname>
                  <Region>Ningxia</Region>
                  <AvgResponseRate>512.8134924297486</AvgResponseRate>
                  <AvgObjectSize>2813953.1475538164</AvgObjectSize>
                  <ReqErrRate>0.0</ReqErrRate>
                  <Qps>0.010138888888888888</Qps>
                  <AvgResponseTime>5487.283757338552</AvgResponseTime>
            </RegionProportionData>
            <RegionProportionData>
                  <Bps>219378.5598888889</Bps>
                  <Proportion>2.250308261405672</Proportion>
                  <ReqHitRate>100.0</ReqHitRate>
                  <TotalBytes>1382084927</TotalBytes>
                  <BytesProportion>2.040934529315853</BytesProportion>
                  <ByteHitRate>100.00000000000001</ByteHitRate>
                  <TotalQuery>584</TotalQuery>
                  <RegionEname>Jilin</RegionEname>
                  <Region>Jilin</Region>
                  <AvgResponseRate>1152.4327405034373</AvgResponseRate>
                  <AvgObjectSize>2366583.779623288</AvgObjectSize>
                  <ReqErrRate>0.0</ReqErrRate>
                  <Qps>0.011587301587301587</Qps>
                  <AvgResponseTime>2053.554794520548</AvgResponseTime>
            </RegionProportionData>
            <RegionProportionData>
                  <Bps>181938.64595238096</Bps>
                  <Proportion>2.3273736128236746</Proportion>
                  <ReqHitRate>100.0</ReqHitRate>
                  <TotalBytes>1146213469</TotalBytes>
                  <BytesProportion>1.6926214892159708</BytesProportion>
                  <ByteHitRate>100.0</ByteHitRate>
                  <TotalQuery>604</TotalQuery>
                  <RegionEname>Gansu</RegionEname>
                  <Region>Gansu</Region>
                  <AvgResponseRate>476.60455862620415</AvgResponseRate>
                  <AvgObjectSize>1897704.4197019867</AvgObjectSize>
                  <ReqErrRate>0.0</ReqErrRate>
                  <Qps>0.011984126984126984</Qps>
                  <AvgResponseTime>3981.7168874172185</AvgResponseTime>
            </RegionProportionData>
            <RegionProportionData>
                  <Bps>302711.6698571429</Bps>
                  <Proportion>2.8013255240443895</Proportion>
                  <ReqHitRate>99.8624484181568</ReqHitRate>
                  <TotalBytes>1907083520</TotalBytes>
                  <BytesProportion>2.816203642467227</BytesProportion>
                  <ByteHitRate>99.99996931440107</ByteHitRate>
                  <TotalQuery>727</TotalQuery>
                  <RegionEname>xinjiang</RegionEname>
                  <Region>Xinjiang</Region>
                  <AvgResponseRate>786.5196031941114</AvgResponseRate>
                  <AvgObjectSize>2623223.5489683636</AvgObjectSize>
                  <ReqErrRate>0.0</ReqErrRate>
                  <Qps>0.014424603174603175</Qps>
                  <AvgResponseTime>3335.2297111416783</AvgResponseTime>
            </RegionProportionData>
            <RegionProportionData>
                  <Bps>330366.9671587302</Bps>
                  <Proportion>2.847564734895191</Proportion>
                  <ReqHitRate>99.86468200270636</ReqHitRate>
                  <TotalBytes>2081311893</TotalBytes>
                  <BytesProportion>3.0734879058423363</BytesProportion>
                  <ByteHitRate>99.99996955766207</ByteHitRate>
                  <TotalQuery>739</TotalQuery>
                  <RegionEname>neimenggu</RegionEname>
                  <Region>Inner Mongolia</Region>
                  <AvgResponseRate>537.274830290738</AvgResponseRate>
                  <AvgObjectSize>2816389.5711772665</AvgObjectSize>
                  <ReqErrRate>0.0</ReqErrRate>
                  <Qps>0.014662698412698412</Qps>
                  <AvgResponseTime>5241.9905277401895</AvgResponseTime>
            </RegionProportionData>
            <RegionProportionData>
                  <Bps>296377.9758412699</Bps>
                  <Proportion>2.8552712700369915</Proportion>
                  <ReqHitRate>100.0</ReqHitRate>
                  <TotalBytes>1867181247</TotalBytes>
                  <BytesProportion>2.7572796764166547</BytesProportion>
                  <ByteHitRate>100.0</ByteHitRate>
                  <TotalQuery>741</TotalQuery>
                  <RegionEname>Guizhou</RegionEname>
                  <Region>Guizhou</Region>
                  <AvgResponseRate>784.3618585093111</AvgResponseRate>
                  <AvgObjectSize>2519812.7500674766</AvgObjectSize>
                  <ReqErrRate>0.0</ReqErrRate>
                  <Qps>0.014702380952380953</Qps>
                  <AvgResponseTime>3212.5641025641025</AvgResponseTime>
            </RegionProportionData>
            <RegionProportionData>
                  <Bps>359904.2652857143</Bps>
                  <Proportion>3.0749075215782984</Proportion>
                  <ReqHitRate>100.0</ReqHitRate>
                  <TotalBytes>2267396871</TotalBytes>
                  <BytesProportion>3.348280901477785</BytesProportion>
                  <ByteHitRate>100.0</ByteHitRate>
                  <TotalQuery>798</TotalQuery>
                  <RegionEname>shanxixian</RegionEname>
                  <Region>Shaanxi</Region>
                  <AvgResponseRate>936.6710791561273</AvgResponseRate>
                  <AvgObjectSize>2841349.462781955</AvgObjectSize>
                  <ReqErrRate>0.0</ReqErrRate>
                  <Qps>0.015833333333333335</Qps>
                  <AvgResponseTime>3033.4548872180453</AvgResponseTime>
            </RegionProportionData>
            <RegionProportionData>
                  <Bps>351643.65639682545</Bps>
                  <Proportion>3.101880394574599</Proportion>
                  <ReqHitRate>98.88198757763975</ReqHitRate>
                  <TotalBytes>2215355035</TotalBytes>
                  <BytesProportion>3.2714303563604967</BytesProportion>
                  <ByteHitRate>99.8809108401154</ByteHitRate>
                  <TotalQuery>805</TotalQuery>
                  <RegionEname>Jiangxi</RegionEname>
                  <Region>Jiangxi</Region>
                  <AvgResponseRate>1809.5402913913995</AvgResponseRate>
                  <AvgObjectSize>2751993.832670808</AvgObjectSize>
                  <ReqErrRate>0.0</ReqErrRate>
                  <Qps>0.01597222222222222</Qps>
                  <AvgResponseTime>1520.824844720497</AvgResponseTime>
            </RegionProportionData>
            <RegionProportionData>
                  <Bps>337654.18080952385</Bps>
                  <Proportion>3.313810110974106</Proportion>
                  <ReqHitRate>99.4186046511628</ReqHitRate>
                  <TotalBytes>2127221339</TotalBytes>
                  <BytesProportion>3.141282707530976</BytesProportion>
                  <ByteHitRate>99.99985277977696</ByteHitRate>
                  <TotalQuery>860</TotalQuery>
                  <RegionEname>Fujian</RegionEname>
                  <Region>Fujian</Region>
                  <AvgResponseRate>1154.391434785841</AvgResponseRate>
                  <AvgObjectSize>2473513.185</AvgObjectSize>
                  <ReqErrRate>0.0</ReqErrRate>
                  <Qps>0.017063492063492062</Qps>
                  <AvgResponseTime>2142.6988372093024</AvgResponseTime>
            </RegionProportionData>
            <RegionProportionData>
                  <Bps>359782.1130793651</Bps>
                  <Proportion>3.4525277435265105</Proportion>
                  <ReqHitRate>99.55357142857143</ReqHitRate>
                  <TotalBytes>2266627312</TotalBytes>
                  <BytesProportion>3.3471444884395347</BytesProportion>
                  <ByteHitRate>99.88374126237764</ByteHitRate>
                  <TotalQuery>896</TotalQuery>
                  <RegionEname>shanxi</RegionEname>
                  <Region>Shanxi</Region>
                  <AvgResponseRate>1235.7418245535987</AvgResponseRate>
                  <AvgObjectSize>2529717.982589286</AvgObjectSize>
                  <ReqErrRate>0.0</ReqErrRate>
                  <Qps>0.017777777777777778</Qps>
                  <AvgResponseTime>2047.125</AvgResponseTime>
            </RegionProportionData>
            <RegionProportionData>
                  <Bps>400389.1932857143</Bps>
                  <Proportion>3.5103267570900125</Proportion>
                  <ReqHitRate>100.0</ReqHitRate>
                  <TotalBytes>2522451917</TotalBytes>
                  <BytesProportion>3.7249224817393896</BytesProportion>
                  <ByteHitRate>100.0</ByteHitRate>
                  <TotalQuery>911</TotalQuery>
                  <RegionEname>yunnan</RegionEname>
                  <Region>Yunnan</Region>
                  <AvgResponseRate>1662.686634908582</AvgResponseRate>
                  <AvgObjectSize>2768882.4563117456</AvgObjectSize>
                  <ReqErrRate>0.0</ReqErrRate>
                  <Qps>0.018075396825396824</Qps>
                  <AvgResponseTime>1665.3062568605928</AvgResponseTime>
            </RegionProportionData>
            <RegionProportionData>
                  <Bps>396200.5617777778</Bps>
                  <Proportion>3.695283600493218</Proportion>
                  <ReqHitRate>100.0</ReqHitRate>
                  <TotalBytes>2496063539</TotalBytes>
                  <BytesProportion>3.685954577676852</BytesProportion>
                  <ByteHitRate>100.0</ByteHitRate>
                  <TotalQuery>959</TotalQuery>
                  <RegionEname>Hebei</RegionEname>
                  <Region>Hebei</Region>
                  <AvgResponseRate>1028.303387588414</AvgResponseRate>
                  <AvgObjectSize>2602777.413138686</AvgObjectSize>
                  <ReqErrRate>0.0</ReqErrRate>
                  <Qps>0.01902777777777778</Qps>
                  <AvgResponseTime>2531.1376433785194</AvgResponseTime>
            </RegionProportionData>
            <RegionProportionData>
                  <Bps>487959.9617619048</Bps>
                  <Proportion>4.188501849568434</Proportion>
                  <ReqHitRate>99.72401103955842</ReqHitRate>
                  <TotalBytes>3074147759</TotalBytes>
                  <BytesProportion>4.5396156096015785</BytesProportion>
                  <ByteHitRate>99.99993802509998</ByteHitRate>
                  <TotalQuery>1087</TotalQuery>
                  <RegionEname>Hubei</RegionEname>
                  <Region>Hubei</Region>
                  <AvgResponseRate>884.3783424312907</AvgResponseRate>
                  <AvgObjectSize>2828102.81425943</AvgObjectSize>
                  <ReqErrRate>0.0</ReqErrRate>
                  <Qps>0.02156746031746032</Qps>
                  <AvgResponseTime>3197.8426862925485</AvgResponseTime>
            </RegionProportionData>
            <RegionProportionData>
                  <Bps>451918.7006190476</Bps>
                  <Proportion>4.296393341553637</Proportion>
                  <ReqHitRate>99.64125560538116</ReqHitRate>
                  <TotalBytes>2847087813</TotalBytes>
                  <BytesProportion>4.2043145921101575</BytesProportion>
                  <ByteHitRate>99.91296907710742</ByteHitRate>
                  <TotalQuery>1115</TotalQuery>
                  <RegionEname>zhejiang</RegionEname>
                  <Region>Zhejiang</Region>
                  <AvgResponseRate>1127.3220113227628</AvgResponseRate>
                  <AvgObjectSize>2553441.9855605382</AvgObjectSize>
                  <ReqErrRate>0.0</ReqErrRate>
                  <Qps>0.022123015873015874</Qps>
                  <AvgResponseTime>2265.0511210762334</AvgResponseTime>
            </RegionProportionData>
            <RegionProportionData>
                  <Bps>508989.9772222223</Bps>
                  <Proportion>4.37345869297164</Proportion>
                  <ReqHitRate>99.64757709251101</ReqHitRate>
                  <TotalBytes>3206636856</TotalBytes>
                  <BytesProportion>4.73526319123739</BytesProportion>
                  <ByteHitRate>99.7790833225895</ByteHitRate>
                  <TotalQuery>1135</TotalQuery>
                  <RegionEname>Jiangsu</RegionEname>
                  <Region>Jiangsu</Region>
                  <AvgResponseRate>1330.4354698914951</AvgResponseRate>
                  <AvgObjectSize>2825230.7105726874</AvgObjectSize>
                  <ReqErrRate>0.0</ReqErrRate>
                  <Qps>0.02251984126984127</Qps>
                  <AvgResponseTime>2123.5383259911896</AvgResponseTime>
            </RegionProportionData>
            <RegionProportionData>
                  <Bps>488243.6136984127</Bps>
                  <Proportion>4.37731196054254</Proportion>
                  <ReqHitRate>99.03169014084507</ReqHitRate>
                  <TotalBytes>3075934766</TotalBytes>
                  <BytesProportion>4.54225449569792</BytesProportion>
                  <ByteHitRate>99.99857147165532</ByteHitRate>
                  <TotalQuery>1136</TotalQuery>
                  <RegionEname>Hunan</RegionEname>
                  <Region>Hunan</Region>
                  <AvgResponseRate>1339.8235569585188</AvgResponseRate>
                  <AvgObjectSize>2707689.0548415496</AvgObjectSize>
                  <ReqErrRate>0.0</ReqErrRate>
                  <Qps>0.02253968253968254</Qps>
                  <AvgResponseTime>2020.9295774647887</AvgResponseTime>
            </RegionProportionData>
            <RegionProportionData>
                  <Bps>508313.40790476196</Bps>
                  <Proportion>4.465937114673243</Proportion>
                  <ReqHitRate>100.0</ReqHitRate>
                  <TotalBytes>3202374469</TotalBytes>
                  <BytesProportion>4.728968894829482</BytesProportion>
                  <ByteHitRate>100.0</ByteHitRate>
                  <TotalQuery>1159</TotalQuery>
                  <RegionEname>Heilongjiang</RegionEname>
                  <Region>Heilongjiang</Region>
                  <AvgResponseRate>1397.6178986771317</AvgResponseRate>
                  <AvgObjectSize>2763049.585677308</AvgObjectSize>
                  <ReqErrRate>0.0</ReqErrRate>
                  <Qps>0.022996031746031747</Qps>
                  <AvgResponseTime>1976.9706643658326</AvgResponseTime>
            </RegionProportionData>
            <RegionProportionData>
                  <Bps>490651.66979365086</Bps>
                  <Proportion>4.519882860665844</Proportion>
                  <ReqHitRate>100.0</ReqHitRate>
                  <TotalBytes>3091105519</TotalBytes>
                  <BytesProportion>4.564657253906334</BytesProportion>
                  <ByteHitRate>99.99999999999999</ByteHitRate>
                  <TotalQuery>1173</TotalQuery>
                  <RegionEname>Liaoning</RegionEname>
                  <Region>Liaoning</Region>
                  <AvgResponseRate>1452.8561771775414</AvgResponseRate>
                  <AvgObjectSize>2635213.5717817564</AvgObjectSize>
                  <ReqErrRate>0.0</ReqErrRate>
                  <Qps>0.023273809523809523</Qps>
                  <AvgResponseTime>1813.8158567774935</AvgResponseTime>
            </RegionProportionData>
            <RegionProportionData>
                  <Bps>493617.2470952381</Bps>
                  <Proportion>4.519882860665844</Proportion>
                  <ReqHitRate>99.65899403239557</ReqHitRate>
                  <TotalBytes>3109788656</TotalBytes>
                  <BytesProportion>4.592246773671759</BytesProportion>
                  <ByteHitRate>99.962662755313</ByteHitRate>
                  <TotalQuery>1173</TotalQuery>
                  <RegionEname>anhui</RegionEname>
                  <Region>Anhui</Region>
                  <AvgResponseRate>1502.2255494727121</AvgResponseRate>
                  <AvgObjectSize>2651141.2248081844</AvgObjectSize>
                  <ReqErrRate>0.0</ReqErrRate>
                  <Qps>0.023273809523809523</Qps>
                  <AvgResponseTime>1764.8090366581416</AvgResponseTime>
            </RegionProportionData>
            <RegionProportionData>
                  <Bps>544321.7694444446</Bps>
                  <Proportion>4.778051787916153</Proportion>
                  <ReqHitRate>98.79032258064517</ReqHitRate>
                  <TotalBytes>3429227147</TotalBytes>
                  <BytesProportion>5.063963838946395</BytesProportion>
                  <ByteHitRate>99.3034652219695</ByteHitRate>
                  <TotalQuery>1240</TotalQuery>
                  <RegionEname>Guangxi</RegionEname>
                  <Region>Guangxi</Region>
                  <AvgResponseRate>469.5304824766785</AvgResponseRate>
                  <AvgObjectSize>2765505.7641129037</AvgObjectSize>
                  <ReqErrRate>0.0</ReqErrRate>
                  <Qps>0.024603174603174603</Qps>
                  <AvgResponseTime>5889.938709677419</AvgResponseTime>
            </RegionProportionData>
            <RegionProportionData>
                  <Bps>518272.7902698413</Bps>
                  <Proportion>5.725955610357583</Proportion>
                  <ReqHitRate>99.93270524899057</ReqHitRate>
                  <TotalBytes>3265118578</TotalBytes>
                  <BytesProportion>4.821623561583812</BytesProportion>
                  <ByteHitRate>99.99678589314689</ByteHitRate>
                  <TotalQuery>1486</TotalQuery>
                  <RegionEname>sichuan</RegionEname>
                  <Region>Sichuan</Region>
                  <AvgResponseRate>720.671411528823</AvgResponseRate>
                  <AvgObjectSize>2197253.41769852</AvgObjectSize>
                  <ReqErrRate>0.0</ReqErrRate>
                  <Qps>0.029484126984126984</Qps>
                  <AvgResponseTime>3048.897711978466</AvgResponseTime>
            </RegionProportionData>
            <RegionProportionData>
                  <Bps>688129.0886031748</Bps>
                  <Proportion>6.022657213316893</Proportion>
                  <ReqHitRate>100.0</ReqHitRate>
                  <TotalBytes>4335213258</TotalBytes>
                  <BytesProportion>6.4018398984302864</BytesProportion>
                  <ByteHitRate>100.0</ByteHitRate>
                  <TotalQuery>1563</TotalQuery>
                  <RegionEname>shandong</RegionEname>
                  <Region>Shandong</Region>
                  <AvgResponseRate>2216.86197693452</AvgResponseRate>
                  <AvgObjectSize>2773648.9175943704</AvgObjectSize>
                  <ReqErrRate>0.0</ReqErrRate>
                  <Qps>0.03101190476190476</Qps>
                  <AvgResponseTime>1251.1599488163788</AvgResponseTime>
            </RegionProportionData>
            <RegionProportionData>
                  <Bps>650147.539904762</Bps>
                  <Proportion>6.149815043156597</Proportion>
                  <ReqHitRate>99.93734335839599</ReqHitRate>
                  <TotalBytes>4095929501</TotalBytes>
                  <BytesProportion>6.048487892405889</BytesProportion>
                  <ByteHitRate>99.99998447727191</ByteHitRate>
                  <TotalQuery>1596</TotalQuery>
                  <RegionEname>Henan</RegionEname>
                  <Region>Henan</Region>
                  <AvgResponseRate>1091.8003744598548</AvgResponseRate>
                  <AvgObjectSize>2566371.868045113</AvgObjectSize>
                  <ReqErrRate>0.0</ReqErrRate>
                  <Qps>0.03166666666666667</Qps>
                  <AvgResponseTime>2350.5870927318297</AvgResponseTime>
            </RegionProportionData>
            <RegionProportionData>
                  <Bps>764462.3847142858</Bps>
                  <Proportion>7.405980271270037</Proportion>
                  <ReqHitRate>99.37565036420395</ReqHitRate>
                  <TotalBytes>4816113023</TotalBytes>
                  <BytesProportion>7.111987963257421</BytesProportion>
                  <ByteHitRate>99.82548062184921</ByteHitRate>
                  <TotalQuery>1922</TotalQuery>
                  <RegionEname>Guangdong</RegionEname>
                  <Region>Guangdong</Region>
                  <AvgResponseRate>1040.446859646019</AvgResponseRate>
                  <AvgObjectSize>2505782.0102497404</AvgObjectSize>
                  <ReqErrRate>0.0</ReqErrRate>
                  <Qps>0.03813492063492063</Qps>
                  <AvgResponseTime>2408.3709677419356</AvgResponseTime>
            </RegionProportionData>
      </Value>
      <DataInterval>86400</DataInterval>
      <RequestId>2E5AD83F-BD7B-462E-8319-2E30E305519A</RequestId>
      <DomainName>downtest.cdnpe.com</DomainName>
      <EndTime>2015-12-07T12:00:00Z</EndTime>
      <StartTime>2015-12-05T12:00:00Z</StartTime>
</DescribeDomainRegionDataResponse>
```

`JSON` format

```
{
    "Value": {
        "RegionProportionData": [{
            "Bps": "380.9614285714286",
            "Proportion": "0.01155980271270037",
            "ReqHitRate": "100.0",
            "TotalBytes": "2400057",
            "BytesProportion": "0.003544181046236794",
            "ByteHitRate": "100.0",
            "TotalQuery": "3",
            "RegionEname": "",
            "Region": "Japan",
            "AvgResponseRate": "154.3345765545624",
            "AvgObjectSize": "800019.0",
            "ReqErrRate": "0.0",
            "Qps": "5.9523809523809524E-5",
            "AvgResponseTime": "5183.666666666667"
        }, {
            "Bps": "25110.431412698414",
            "Proportion": "0.31211467324291",
            "ReqHitRate": "100.0",
            "TotalBytes": "158195717",
            "BytesProportion": "0.23360872886644055",
            "ByteHitRate": "100.0",
            "TotalQuery": "81",
            "RegionEname": "xizang",
            "Region":"Tibet Autonomous Region",
            "AvgResponseRate": "1397.1430909315718",
            "AvgObjectSize": "1953033.5543209878",
            "ReqErrRate": "0.0",
            "Qps": "0.0016071428571428571",
            "AvgResponseTime": "1397.8765432098764"
        }, {
            "Bps": "40343.86242857143",
            "Proportion": "0.33908754623921084",
            "ReqHitRate": "100.0",
            "TotalBytes": "254166333",
            "BytesProportion": "0.37532921137846464",
            "ByteHitRate": "100.0",
            "TotalQuery": "88",
            "RegionEname": "zhongqing",
            "Region":"Chongqing",
            "AvgResponseRate": "787.8073097249128",
            "AvgObjectSize": "2888253.7875",
            "ReqErrRate": "0.0",
            "Qps": "0.001746031746031746",
            "AvgResponseTime": "3666.193181818182"
        }, {
            "Bps": "38835.2834920635",
            "Proportion": "0.37376695437731194",
            "ReqHitRate": "100.0",
            "TotalBytes": "244662286",
            "BytesProportion": "0.3612945179094354",
            "ByteHitRate": "100.0",
            "TotalQuery": "97",
            "RegionEname": "tianjin",
            "Region":"Tianjin",
            "AvgResponseRate": "1711.4277340197823",
            "AvgObjectSize": "2522291.608247423",
            "ReqErrRate": "0.0",
            "Qps": "0.0019246031746031746",
            "AvgResponseTime": "1473.7938144329896"
        }, {
            "Bps": "69358.64117460318",
            "Proportion": "0.5895499383477188",
            "ReqHitRate": "99.34640522875817",
            "TotalBytes": "436959439",
            "BytesProportion": "0.6452610763393265",
            "ByteHitRate": "99.99291705425965",
            "TotalQuery": "153",
            "RegionEname": "qinghai",
            "Region": "Qinghai",
            "AvgResponseRate": "1210.9708048576356",
            "AvgObjectSize": "2855944.0483660134",
            "ReqErrRate": "0.0",
            "Qps": "0.0030357142857142857",
            "AvgResponseTime": "2358.392156862745"
        }, {
            "Bps": "66239.68633333335",
            "Proportion": "0.6473489519112207",
            "ReqHitRate": "100.0",
            "TotalBytes": "417310023",
            "BytesProportion": "0.6162446463192347",
            "ByteHitRate": "99.99999999999999",
            "TotalQuery": "168",
            "RegionEname": "Hainan",
            "Region": "Hainan",
            "AvgResponseRate": "324.9427676080411",
            "AvgObjectSize": "2483988.2375000003",
            "ReqErrRate": "0.0",
            "Qps": "0.0033333333333333335",
            "AvgResponseTime": "7644.386904761905"
        }, {
            "Bps": "62071.644380952384",
            "Proportion": "0.7745067817509248",
            "ReqHitRate": "99.50248756218906",
            "TotalBytes": "391051359",
            "BytesProportion": "0.5774682921278322",
            "ByteHitRate": "99.99983347455928",
            "TotalQuery": "201",
            "RegionEname": "shanghai",
            "Region":"Shanghai",
            "AvgResponseRate": "1319.43005273653",
            "AvgObjectSize": "1945529.152238806",
            "ReqErrRate": "0.0",
            "Qps": "0.0039880952380952385",
            "AvgResponseTime": "1474.5223880597016"
        }, {
            "Bps": "86967.5461111111",
            "Proportion": "0.9286374845869297",
            "ReqHitRate": "96.2655601659751",
            "TotalBytes": "547895540",
            "BytesProportion": "0.8090811968039774",
            "ByteHitRate": "98.60251863101267",
            "TotalQuery": "241",
            "RegionEname": "beijing",
            "Region":"Beijing",
            "AvgResponseRate": "1223.3552235839977",
            "AvgObjectSize": "2273425.479253112",
            "ReqErrRate": "0.0",
            "Qps": "0.004781746031746032",
            "AvgResponseTime": "1858.3526970954356"
        }, {
            "Bps": "228242.86641269844",
            "Proportion": "1.9690197287299631",
            "ReqHitRate": "100.0",
            "TotalBytes": "1437930058",
            "BytesProportion": "2.1234014270475434",
            "ByteHitRate": "100.0",
            "TotalQuery": "511",
            "RegionEname": "ningxia",
            "Region":"Ningxia",
            "AvgResponseRate": "512.8134924297486",
            "AvgObjectSize": "2813953.1475538164",
            "ReqErrRate": "0.0",
            "Qps": "0.010138888888888888",
            "AvgResponseTime": "5487.283757338552"
        }, {
            "Bps": "219378.5598888889",
            "Proportion": "2.250308261405672",
            "ReqHitRate": "100.0",
            "TotalBytes": "1382084927",
            "BytesProportion": "2.040934529315853",
            "ByteHitRate": "100.00000000000001",
            "TotalQuery": "584",
            "RegionEname": "Jilin",
            "Region": "Jilin",
            "AvgResponseRate": "1152.4327405034373",
            "AvgObjectSize": "2366583.779623288",
            "ReqErrRate": "0.0",
            "Qps": "0.011587301587301587",
            "AvgResponseTime": "2053.554794520548"
        }, {
            "Bps": "181938.64595238096",
            "Proportion": "2.3273736128236746",
            "ReqHitRate": "100.0",
            "TotalBytes": "1146213469",
            "BytesProportion": "1.6926214892159708",
            "ByteHitRate": "100.0",
            "TotalQuery": "604",
            "RegionEname": "Gansu",
            "Region": "Gansu",
            "AvgResponseRate": "476.60455862620415",
            "AvgObjectSize": "1897704.4197019867",
            "ReqErrRate": "0.0",
            "Qps": "0.011984126984126984",
            "AvgResponseTime": "3981.7168874172185"
        }, {
            "Bps": "302711.6698571429",
            "Proportion": "2.8013255240443895",
            "ReqHitRate": "99.8624484181568",
            "TotalBytes": "1907083520",
            "BytesProportion": "2.816203642467227",
            "ByteHitRate": "99.99996931440107",
            "TotalQuery": "727",
            "RegionEname": "xinjiang",
            "Region":"Xinjiang",
            "AvgResponseRate": "786.5196031941114",
            "AvgObjectSize": "2623223.5489683636",
            "ReqErrRate": "0.0",
            "Qps": "0.014424603174603175",
            "AvgResponseTime": "3335.2297111416783"
        }, {
            "Bps": "330366.9671587302",
            "Proportion": "2.847564734895191",
            "ReqHitRate": "99.86468200270636",
            "TotalBytes": "2081311893",
            "BytesProportion": "3.0734879058423363",
            "ByteHitRate": "99.99996955766207",
            "TotalQuery": "739",
            "RegionEname": "neimenggu",
            "Region":"Inner Mongolia",
            "AvgResponseRate": "537.274830290738",
            "AvgObjectSize": "2816389.5711772665",
            "ReqErrRate": "0.0",
            "Qps": "0.014662698412698412",
            "AvgResponseTime": "5241.9905277401895"
        }, {
            "Bps": "296377.9758412699",
            "Proportion": "2.8552712700369915",
            "ReqHitRate": "100.0",
            "TotalBytes": "1867181247",
            "BytesProportion": "2.7572796764166547",
            "ByteHitRate": "100.0",
            "TotalQuery": "741",
            "RegionEname": "Guizhou",
            "Region": "Guizhou",
            "AvgResponseRate": "784.3618585093111",
            "AvgObjectSize": "2519812.7500674766",
            "ReqErrRate": "0.0",
            "Qps": "0.014702380952380953",
            "AvgResponseTime": "3212.5641025641025"
        }, {
            "Bps": "359904.2652857143",
            "Proportion": "3.0749075215782984",
            "ReqHitRate": "100.0",
            "TotalBytes": "2267396871",
            "BytesProportion": "3.348280901477785",
            "ByteHitRate": "100.0",
            "TotalQuery": "798",
            "RegionEname": "shanxixian",
            "Region": "Shaanxi",
            "AvgResponseRate": "936.6710791561273",
            "AvgObjectSize": "2841349.462781955",
            "ReqErrRate": "0.0",
            "Qps": "0.015833333333333335",
            "AvgResponseTime": "3033.4548872180453"
        }, {
            "Bps": "351643.65639682545",
            "Proportion": "3.101880394574599",
            "ReqHitRate": "98.88198757763975",
            "TotalBytes": "2215355035",
            "BytesProportion": "3.2714303563604967",
            "ByteHitRate": "99.8809108401154",
            "TotalQuery": "805",
            "RegionEname": "Jiangxi",
            "Region": "Jiangxi",
            "AvgResponseRate": "1809.5402913913995",
            "AvgObjectSize": "2751993.832670808",
            "ReqErrRate": "0.0",
            "Qps": "0.01597222222222222",
            "AvgResponseTime": "1520.824844720497"
        }, {
            "Bps": "337654.18080952385",
            "Proportion": "3.313810110974106",
            "ReqHitRate": "99.4186046511628",
            "TotalBytes": "2127221339",
            "BytesProportion": "3.141282707530976",
            "ByteHitRate": "99.99985277977696",
            "TotalQuery": "860",
            "RegionEname": "Fujian",
            "Region": "Fujian",
            "AvgResponseRate": "1154.391434785841",
            "AvgObjectSize": "2473513.185",
            "ReqErrRate": "0.0",
            "Qps": "0.017063492063492062",
            "AvgResponseTime": "2142.6988372093024"
        }, {
            "Bps": "359782.1130793651",
            "Proportion": "3.4525277435265105",
            "ReqHitRate": "99.55357142857143",
            "TotalBytes": "2266627312",
            "BytesProportion": "3.3471444884395347",
            "ByteHitRate": "99.88374126237764",
            "TotalQuery": "896",
            "RegionEname": "shanxi",
            "Region": "Shanxi",
            "AvgResponseRate": "1235.7418245535987",
            "AvgObjectSize": "2529717.982589286",
            "ReqErrRate": "0.0",
            "Qps": "0.017777777777777778",
            "AvgResponseTime": "2047.125"
        }, {
            "Bps": "400389.1932857143",
            "Proportion": "3.5103267570900125",
            "ReqHitRate": "100.0",
            "TotalBytes": "2522451917",
            "BytesProportion": "3.7249224817393896",
            "ByteHitRate": "100.0",
            "TotalQuery": "911",
            "RegionEname": "yunnan",
            "Region": "Yunnan",
            "AvgResponseRate": "1662.686634908582",
            "AvgObjectSize": "2768882.4563117456",
            "ReqErrRate": "0.0",
            "Qps": "0.018075396825396824",
            "AvgResponseTime": "1665.3062568605928"
        }, {
            "Bps": "396200.5617777778",
            "Proportion": "3.695283600493218",
            "ReqHitRate": "100.0",
            "TotalBytes": "2496063539",
            "BytesProportion": "3.685954577676852",
            "ByteHitRate": "100.0",
            "TotalQuery": "959",
            "RegionEname": "Hebei",
            "Region": "Hebei",
            "AvgResponseRate": "1028.303387588414",
            "AvgObjectSize": "2602777.413138686",
            "ReqErrRate": "0.0",
            "Qps": "0.01902777777777778",
            "AvgResponseTime": "2531.1376433785194"
        }, {
            "Bps": "487959.9617619048",
            "Proportion": "4.188501849568434",
            "ReqHitRate": "99.72401103955842",
            "TotalBytes": "3074147759",
            "BytesProportion": "4.5396156096015785",
            "ByteHitRate": "99.99993802509998",
            "TotalQuery": "1087",
            "RegionEname": "Hubei",
            "Region": "Hubei",
            "AvgResponseRate": "884.3783424312907",
            "AvgObjectSize": "2828102.81425943",
            "ReqErrRate": "0.0",
            "Qps": "0.02156746031746032",
            "AvgResponseTime": "3197.8426862925485"
        }, {
            "Bps": "451918.7006190476",
            "Proportion": "4.296393341553637",
            "ReqHitRate": "99.64125560538116",
            "TotalBytes": "2847087813",
            "BytesProportion": "4.2043145921101575",
            "ByteHitRate": "99.91296907710742",
            "TotalQuery": "1115",
            "RegionEname": "zhejiang",
            "region" : "Zhejiang",
            "AvgResponseRate": "1127.3220113227628",
            "AvgObjectSize": "2553441.9855605382",
            "ReqErrRate": "0.0",
            "Qps": "0.022123015873015874",
            "AvgResponseTime": "2265.0511210762334"
        }, {
            "Bps": "508989.9772222223",
            "Proportion": "4.37345869297164",
            "ReqHitRate": "99.64757709251101",
            "TotalBytes": "3206636856",
            "BytesProportion": "4.73526319123739",
            "ByteHitRate": "99.7790833225895",
            "TotalQuery": "1135",
            "RegionEname": "Jiangsu",
            "Region": "Jiangsu",
            "AvgResponseRate": "1330.4354698914951",
            "AvgObjectSize": "2825230.7105726874",
            "ReqErrRate": "0.0",
            "Qps": "0.02251984126984127",
            "AvgResponseTime": "2123.5383259911896"
        }, {
            "Bps": "488243.6136984127",
            "Proportion": "4.37731196054254",
            "ReqHitRate": "99.03169014084507",
            "TotalBytes": "3075934766",
            "BytesProportion": "4.54225449569792",
            "ByteHitRate": "99.99857147165532",
            "TotalQuery": "1136",
            "RegionEname": "Hunan",
            "Region": "Hunan",
            "AvgResponseRate": "1339.8235569585188",
            "AvgObjectSize": "2707689.0548415496",
            "ReqErrRate": "0.0",
            "Qps": "0.02253968253968254",
            "AvgResponseTime": "2020.9295774647887"
        }, {
            "Bps": "508313.40790476196",
            "Proportion": "4.465937114673243",
            "ReqHitRate": "100.0",
            "TotalBytes": "3202374469",
            "BytesProportion": "4.728968894829482",
            "ByteHitRate": "100.0",
            "TotalQuery": "1159",
            "RegionEname": "Heilongjiang",
            "Region": "Heilongjiang",
            "AvgResponseRate": "1397.6178986771317",
            "AvgObjectSize": "2763049.585677308",
            "ReqErrRate": "0.0",
            "Qps": "0.022996031746031747",
            "AvgResponseTime": "1976.9706643658326"
        }, {
            "Bps": "490651.66979365086",
            "Proportion": "4.519882860665844",
            "ReqHitRate": "100.0",
            "TotalBytes": "3091105519",
            "BytesProportion": "4.564657253906334",
            "ByteHitRate": "99.99999999999999",
            "TotalQuery": "1173",
            "RegionEname": "Liaoning",
            "Region": "Liaoning",
            "AvgResponseRate": "1452.8561771775414",
            "AvgObjectSize": "2635213.5717817564",
            "ReqErrRate": "0.0",
            "Qps": "0.023273809523809523",
            "AvgResponseTime": "1813.8158567774935"
        }, {
            "Bps": "493617.2470952381",
            "Proportion": "4.519882860665844",
            "ReqHitRate": "99.65899403239557",
            "TotalBytes": "3109788656",
            "BytesProportion": "4.592246773671759",
            "ByteHitRate": "99.962662755313",
            "TotalQuery": "1173",
            "RegionEname": "anhui",
            "Region": "Anhui",
            "AvgResponseRate": "1502.2255494727121",
            "AvgObjectSize": "2651141.2248081844",
            "ReqErrRate": "0.0",
            "Qps": "0.023273809523809523",
            "AvgResponseTime": "1764.8090366581416"
        }, {
            "Bps": "544321.7694444446",
            "Proportion": "4.778051787916153",
            "ReqHitRate": "98.79032258064517",
            "TotalBytes": "3429227147",
            "BytesProportion": "5.063963838946395",
            "ByteHitRate": "99.3034652219695",
            "TotalQuery": "1240",
            "RegionEname": "Guangxi",
            "Region":"Guangxi",
            "AvgResponseRate": "469.5304824766785",
            "AvgObjectSize": "2765505.7641129037",
            "ReqErrRate": "0.0",
            "Qps": "0.024603174603174603",
            "AvgResponseTime": "5889.938709677419"
        }, {
            "Bps": "518272.7902698413",
            "Proportion": "5.725955610357583",
            "ReqHitRate": "99.93270524899057",
            "TotalBytes": "3265118578",
            "BytesProportion": "4.821623561583812",
            "ByteHitRate": "99.99678589314689",
            "TotalQuery": "1486",
            "RegionEname": "sichuan",
            "Region": "Sichuan",
            "AvgResponseRate": "720.671411528823",
            "AvgObjectSize": "2197253.41769852",
            "ReqErrRate": "0.0",
            "Qps": "0.029484126984126984",
            "AvgResponseTime": "3048.897711978466"
        }, {
            "Bps": "688129.0886031748",
            "Proportion": "6.022657213316893",
            "ReqHitRate": "100.0",
            "TotalBytes": "4335213258",
            "BytesProportion": "6.4018398984302864",
            "ByteHitRate": "100.0",
            "TotalQuery": "1563",
            "RegionEname": "shandong",
            "Region": "Shandong",
            "AvgResponseRate": "2216.86197693452",
            "AvgObjectSize": "2773648.9175943704",
            "ReqErrRate": "0.0",
            "Qps": "0.03101190476190476",
            "AvgResponseTime": "1251.1599488163788"
        }, {
            "Bps": "650147.539904762",
            "Proportion": "6.149815043156597",
            "ReqHitRate": "99.93734335839599",
            "TotalBytes": "4095929501",
            "BytesProportion": "6.048487892405889",
            "ByteHitRate": "99.99998447727191",
            "TotalQuery": "1596",
            "RegionEname": "Henan",
            "Region": "Henan",
            "AvgResponseRate": "1091.8003744598548",
            "AvgObjectSize": "2566371.868045113",
            "ReqErrRate": "0.0",
            "Qps": "0.03166666666666667",
            "AvgResponseTime": "2350.5870927318297"
        }, {
            "Bps": "764462.3847142858",
            "Proportion": "7.405980271270037",
            "ReqHitRate": "99.37565036420395",
            "TotalBytes": "4816113023",
            "BytesProportion": "7.111987963257421",
            "ByteHitRate": "99.82548062184921",
            "TotalQuery": "1922",
            "RegionEname": "Guangdong",
            "Region": "Guangdong",
            "AvgResponseRate": "1040.446859646019",
            "AvgObjectSize": "2505782.0102497404",
            "ReqErrRate": "0.0",
            "Qps": "0.03813492063492063",
            "AvgResponseTime": "2408.3709677419356"
        }]
    },
    "DataInterval": "86400",
    "RequestId": "2E5AD83F-BD7B-462E-8319-2E30E305519A",
    "DomainName": "test.test.com",
    "EndTime": "2015-12-07T12:00:00Z",
    "StartTime": "2015-12-05T12:00:00Z"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|InvalidStartTime.Malformed|Specified StartTime is malformed.|The error message returned because the format of the specified start time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidEndTime.Malformed|Specified EndTime is malformed.|The error message returned because the format of the end time is invalid. For more information about the time format, see the Request parameters section.|
|400|InvalidStartTime.ValueNotSupported|The specified value of parameter StartTime is not supported.|The error message returned because the specified start time is not supported.|
|404|InvalidDomain.NotFound|The domain provided does not exist in our records.|The error message returned because the specified domain name does not exist or does not belong to the current Alibaba Cloud account. Check whether the domain name is correctly specified, whether the domain name is under the current Alibaba Cloud account, and whether the domain name is expired.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Cdn).
