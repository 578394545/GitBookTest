## 产品接口

### 1、获取板卡的型号列表

**接口调用请求说明**

	http请求方式: GET
	https://open.clife.cn/v1/web/open/product/module/list

**参数说明**

<table width="100%" style="border-spacing: 0;  border-collapse: collapse;">
	<tbody>
		<tr>
			<th width="16%">参数名称</th>
			<th width="11%">是否必须</th>
			<th width="11%">字段类型</th>
			<th width="62%">参数说明</th>
		</tr>
		<tr>
			<td>moduleId</td>
			<td>是</td>
			<td>int</td>
			<td>板卡标识</td>
		</tr>
	</tbody>
</table>

**返回结果**

正确的Json返回结果：

	{
	  data:[{
			  "moduleId":3,
              "moduleName":"汉枫" 
		   },
		   {
			   "moduleId":4,
               "moduleName":"庆科"
			}],
      code:0
	}

<table width="100%" style="border-spacing: 0;  border-collapse: collapse;">
	<tbody>
		<tr>
			<th width="16%">字段名称</th>
			<th width="11%">字段类型</th>
			<th width="74%">字段说明</th>
		</tr>
		<tr>
			<td>moduleId</td>
			<td>int</td>
			<td>板卡型号ID</td>
		</tr>
		<tr>
			<td>moduleName</td>
			<td>string</td>
			<td>板卡型号名称</td>
		</tr>
	</tbody>
</table>

----------

### 2、获取所有的大类

**接口调用请求说明**

	http请求方式: POST
	https://open.clife.cn/v1/web/open/product/type/list

**参数说明**

<table width="100%" style="border-spacing: 0;  border-collapse: collapse;">
	<tbody>
		<tr>
			<th width="16%">参数名称</th>
			<th width="11%">是否必须</th>
			<th width="11%">字段类型</th>
			<th width="62%">参数说明</th>
		</tr>
	</tbody>
</table>

**返回结果**

正确的Json返回结果：

	{
	  data:[{
			   "deviceTypeId":1,
			   "deviceTypeName":"冰箱"
			},
			{
				"deviceTypeId":2,
				"deviceTypeName":"电视"
			}],
	  code:0
	}


<table width="100%" style="border-spacing: 0;  border-collapse: collapse;">
	<tbody>
		<tr>
			<th width="16%">字段名称</th>
			<th width="11%">字段类型</th>
			<th width="74%">字段说明</th>
		</tr>
		<tr>
			<td>deviceTypeId</td>
			<td>int</td>
			<td>大类ID</td>
		</tr>
		<tr>
			<td>deviceTypeName</td>
			<td>string</td>
			<td>大类名称</td>
		</tr>
	</tbody>
</table>

### 3、获取开发者所有产品列表

**接口调用请求说明**

	http请求方式: GET
	https://open.clife.cn/v1/web/open/product/listAllProduct

**参数说明**

<table width="100%" style="border-spacing: 0;  border-collapse: collapse;">
	<tbody>
		<tr>
			<th width="16%">参数名称</th>
			<th width="11%">是否必须</th>
			<th width="11%">字段类型</th>
			<th width="62%">参数说明</th>
		</tr>
		<tr>
			<td>pageIndex</td>
			<td>否</td>
			<td>int</td>
			<td>显示的当前页（不传默认为第1页）</td>
		</tr>		
		<tr>
			<td>pageRows</td>
			<td>否</td>
			<td>int</td>
			<td>每页显示的数据条数（不传默认为20条）</td>
		</tr>
	</tbody>
</table>

**返回结果**

正确的Json返回结果：
	
	{
	   data:{
				"list":[{
							"createTime":1452278924000,
							"productId":2002,
							"productName":"低调",
							"deviceKey":"20160109-1-2002-0",
							"status":0,
							"bindType":1,
							"mode":1
						},
						{
							"createTime":1452206514000,
							"productId":1008,
							"productName":"冰箱",
							"deviceKey":"20160108-1-1008-0",
							"status":0,
							"bindType":1,
							"mode":1
						}]
			}
		code:0
	}

<table width="100%" style="border-spacing: 0;  border-collapse: collapse;">
	<tbody>
		<tr>
			<th width="16%">字段名称</th>
			<th width="11%">字段类型</th>
			<th width="74%">字段说明</th>
		</tr>
		<tr>
			<td>productId</td>
			<td>int</td>
			<td>产品 ID</td>
		</tr>
		<tr>
			<td>productName</td>
			<td>string</td>
			<td>产品名称</td>
		</tr>
		<tr>
			<td>deviceKey</td>
			<td>string</td>
			<td>设备接入秘钥</td>
		</tr>
		<tr>
			<td>mode</td>
			<td>int</td>
			<td>模式(0开发模式(未上线)  1生产模式（已上线）)</td>
		</tr>
		<tr>
			<td>bindType</td>
			<td>int</td>
			<td>通讯方式(1:wifi)</td>
		</tr>
		<tr>
			<td>status</td>
			<td>int</td>
			<td>状态（0正常状态，1删除状态）</td>
		</tr>
		<tr>
			<td>createTime</td>
			<td>string</td>
			<td>创建时间</td>
		</tr>
	</tbody>
</table>

### 4、添加产品

**接口调用请求说明**

	http请求方式: GET
	https://open.clife.cn/v1/web/open/product/addProduct

**参数说明**

<table width="100%" style="border-spacing: 0;  border-collapse: collapse;">
	<tbody>
		<tr>
			<th width="16%">参数名称</th>
			<th width="11%">是否必须</th>
			<th width="11%">字段类型</th>
			<th width="62%">参数说明</th>
		</tr>
		<tr>
			<td>productName</td>
			<td>是</td>
			<td>string</td>
			<td>产品名称</td>
		</tr>		
		<tr>
			<td>icon</td>
			<td>是</td>
			<td></td>
			<td>产品图标</td>
		</tr>
		<tr>
			<td>remark</td>
			<td>否</td>
			<td>string</td>
			<td>产品描述</td>
		</tr>
		<tr>
			<td>deviceTypeId</td>
			<td>是</td>
			<td>int</td>
			<td>设备大类ID</td>
		</tr>		
		<tr>
			<td>devSubKeyId</td>
			<td>是</td>
			<td>int</td>
			<td>设备小类主键</td>
		</tr>
		<tr>
			<td>deviceSubtypeId</td>
			<td>是</td>
			<td>int</td>
			<td>设备小类ID</td>
		</tr>
		<tr>
			<td>bindType</td>
			<td>是</td>
			<td>int</td>
			<td>绑定类型（1-WiFi，2-蓝牙 3-红外）</td>
		</tr>		
		<tr>
			<td>moduleId</td>
			<td>是</td>
			<td>int</td>
			<td>模块id</td>
		</tr>
		<tr>
			<td>productCode</td>
			<td>否</td>
			<td>string</td>
			<td>产品型号</td>
		</tr>
		<tr>
			<td>brandId</td>
			<td>是</td>
			<td>int</td>
			<td>品牌ID</td>
		</tr>
		<tr>
			<td>barCode</td>
			<td>否</td>
			<td>string</td>
			<td>条形码<font color=#c00>【2016-11-14 新增参数】</font></td>
		</tr>
	</tbody>
</table>

**返回结果**

正确的Json返回结果：
	
	{
		bindType: 1
		bindTypeName: "WIFI"
		brandId: 0
		devSubKeyId: 10
		deviceKey: null
		deviceSubTypeName: "空调"
		deviceSubtypeId: 1
		deviceTypeId: 3
		deviceTypeName: "空调"
		mode: 0
		moduleId: 3
		moduleName: "汉枫V3"
		productCode: "CC-1001"
		productIcon: "http://200.200.200.50/v1/device/icon"
		productId: 9
		productName: "空调"
		productVersion: 1
		status: 0
		barCode：“”
	}

<table width="100%" style="border-spacing: 0;  border-collapse: collapse;">
	<tbody>
		<tr>
			<th width="16%">字段名称</th>
			<th width="11%">字段类型</th>
			<th width="74%">字段说明</th>
		</tr>
		<tr>
			<td>bindType</td>
			<td>int</td>
			<td>绑定类型</td>
		</tr>
		<tr>
			<td>bindTypeName</td>
			<td>string</td>
			<td>绑定类型名称</td>
		</tr>
		<tr>
			<td>brandId</td>
			<td>int</td>
			<td>品牌ID</td>
		</tr>
		<tr>
			<td>devSubKeyId</td>
			<td>int</td>
			<td>设备子分类主键</td>
		</tr>
		<tr>
			<td>deviceSubtypeId</td>
			<td>int</td>
			<td>设备子分类ID</td>
		</tr>
		<tr>
			<td>deviceSubTypeName</td>
			<td>string</td>
			<td>设备子分类名称</td>
		</tr>
		<tr>
			<td>deviceTypeId</td>
			<td>int</td>
			<td>设备分类ID</td>
		</tr>
		<tr>
			<td>deviceTypeName</td>
			<td>string</td>
			<td>设备分类名称</td>
		</tr>
		<tr>
			<td>mode</td>
			<td>int</td>
			<td>模式(0开发模式(未上线)  1生产模式（已上线）)</td>
		</tr>
		<tr>
			<td>deviceKey</td>
			<td>string</td>
			<td>设备接入秘钥</td>
		</tr>
		<tr>
			<td>status</td>
			<td>int</td>
			<td>状态（0正常状态，1删除状态）</td>
		</tr>
		<tr>
			<td>moduleId</td>
			<td>int</td>
			<td>芯片模块ID</td>
		</tr>
		<tr>
			<td>moduleName</td>
			<td>string</td>
			<td>芯片模块名称</td>
		</tr>
		<tr>
			<td>productCode</td>
			<td>string</td>
			<td>产品型号</td>
		</tr>
		<tr>
			<td>productIcon</td>
			<td>string</td>
			<td>产品LOGO</td>
		</tr>
		<tr>
			<td>productId</td>
			<td>int</td>
			<td>产品ID</td>
		</tr>
		<tr>
			<td>productName</td>
			<td>string</td>
			<td>设备接入秘钥</td>
		</tr>
		<tr>
			<td>productVersion</td>
			<td>int</td>
			<td>产品名称</td>
		</tr>
		<tr>
			<td>status</td>
			<td>int</td>
			<td>状态(0正常状态，1废除状态)</td>
		</tr>
		<tr>
			<td>barCode</td>
			<td>string</td>
			<td>条形码</td>
		</tr>
	</tbody>
</table>

### 5、删除产品 

**接口调用请求说明**

	http请求方式: GET
	https://open.clife.cn/v1/web/open/product/deleteProduct

**参数说明**

<table width="100%" style="border-spacing: 0;  border-collapse: collapse;">
	<tbody>
		<tr>
			<th width="16%">参数名称</th>
			<th width="11%">是否必须</th>
			<th width="11%">字段类型</th>
			<th width="62%">参数说明</th>
		</tr>
		<tr>
			<td>productId</td>
			<td>是</td>
			<td>int</td>
			<td>产品ID</td>
		</tr>
	</tbody>
</table>

**返回结果**

正确的Json返回结果：
	
	{
		"data": {},
		"code": 0
	}


### 6、获取产品的详细信息

**接口调用请求说明**

	http请求方式: GET
	https://open.clife.cn/v1/web/open/product/getProduct

**参数说明**

<table width="100%" style="border-spacing: 0;  border-collapse: collapse;">
	<tbody>
		<tr>
			<th width="16%">参数名称</th>
			<th width="11%">是否必须</th>
			<th width="11%">字段类型</th>
			<th width="62%">参数说明</th>
		</tr>
		<tr>
			<td>productId</td>
			<td>是</td>
			<td>int</td>
			<td>产品ID</td>
		</tr>
	</tbody>
</table>

**返回结果**

正确的Json返回结果：(moduleId=70即为AP模式)
	
	{
		data:{
				bindType: 1,
				bindTypeName: "WIFI",
				brandId: 0,
				devSubKeyId: 10,
				deviceKey: null,
				deviceSubTypeName: "空调",
				deviceSubtypeId: 1,
				deviceTypeId: 3,
				deviceTypeName: "空调",
				mode: 0,
				moduleId: 3,
				moduleName: "汉枫V3",
				productCode: "CC-1001",
				productIcon: "http://200.200.200.50/v1/device/icon",
				productId: 9,
				productName: "空调",
				productVersion: 1,
				status: 0,
				barCode：“”,
				"ssid":null,
				"ssidPassword":null,
				"publishStatus":0(2017-6-22新增),
				"moduleBrandId":2(2017-9-28新增)
			},
		code:0
	}

<table width="100%" style="border-spacing: 0;  border-collapse: collapse;">
	<tbody>
		<tr>
			<th width="16%">字段名称</th>
			<th width="11%">字段类型</th>
			<th width="74%">字段说明</th>
		</tr>
		<tr>
			<td>bindType</td>
			<td>int</td>
			<td>绑定类型</td>
		</tr>
		<tr>
			<td>bindTypeName</td>
			<td>string</td>
			<td>绑定类型名称</td>
		</tr>
		<tr>
			<td>brandId</td>
			<td>int</td>
			<td>品牌ID</td>
		</tr>
		<tr>
			<td>devSubKeyId</td>
			<td>int</td>
			<td>设备子分类主键</td>
		</tr>
		<tr>
			<td>deviceSubtypeId</td>
			<td>int</td>
			<td>设备子分类ID</td>
		</tr>
		<tr>
			<td>deviceSubTypeName</td>
			<td>string</td>
			<td>设备子分类名称</td>
		</tr>
		<tr>
			<td>deviceTypeId</td>
			<td>int</td>
			<td>设备分类ID</td>
		</tr>
		<tr>
			<td>deviceTypeName</td>
			<td>string</td>
			<td>设备分类名称</td>
		</tr>
		<tr>
			<td>mode</td>
			<td>int</td>
			<td>模式(0开发模式(未上线)  1生产模式（已上线）)</td>
		</tr>
		<tr>
			<td>deviceKey</td>
			<td>string</td>
			<td>设备接入秘钥</td>
		</tr>
		<tr>
			<td>status</td>
			<td>int</td>
			<td>状态（0正常状态，1删除状态）</td>
		</tr>
		<tr>
			<td>moduleId</td>
			<td>int</td>
			<td>芯片模块ID</td>
		</tr>
		<tr>
			<td>moduleName</td>
			<td>string</td>
			<td>芯片模块名称</td>
		</tr>
		<tr>
			<td>productCode</td>
			<td>string</td>
			<td>产品型号</td>
		</tr>
		<tr>
			<td>productIcon</td>
			<td>string</td>
			<td>产品LOGO</td>
		</tr>
		<tr>
			<td>productId</td>
			<td>int</td>
			<td>产品ID</td>
		</tr>
		<tr>
			<td>productName</td>
			<td>string</td>
			<td>设备接入秘钥</td>
		</tr>
		<tr>
			<td>productVersion</td>
			<td>int</td>
			<td>产品名称</td>
		</tr>
		<tr>
			<td>status</td>
			<td>int</td>
			<td>状态(0正常状态，1废除状态)</td>
		</tr>
        <tr>
			<td>barCode</td>
			<td>string</td>
			<td>条形码</td>
		</tr>
		<tr>
			<td>publishStatus</td>
			<td>number</td>
			<td>发布状态（null-未发布，0-审核中 1-审核通过，2-审核不通过）(2017-6-22新增)</td>
		</tr>
		<tr>
			<td>ssid</td>
			<td>string</td>
			<td><font color=#c00>【2017-08-17新增】</font>ssid</td>
		</tr>
		<tr>
			<td>ssidPassword</td>
			<td>string</td>
			<td><font color=#c00>【2017-08-17新增】</font>ssid密码</td>
		</tr>
		<tr>
			<td>moduleBrandId</td>
			<td>int</td>
			<td><font color=#c00>【2017-09-28新增】</font>模组厂家ID</td>
		</tr>
	</tbody>
</table>

----------

### 7、获取设备大类下的所有小类

**接口调用请求说明**

	http请求方式: POST
	https://open.clife.cn/v1/web/open/product/subtype/list

**参数说明**

<table width="100%" style="border-spacing: 0;  border-collapse: collapse;">
	<tbody>
		<tr>
			<th width="16%">参数名称</th>
			<th width="11%">是否必须</th>
			<th width="11%">字段类型</th>
			<th width="62%">参数说明</th>
		</tr>
		<tr>
			<td>deviceTypeId</td>
			<td>是</td>
			<td>int</td>
			<td>大类ID</td>
		</tr>
	</tbody>
</table>

**返回结果**

正确的Json返回结果：

	{
	  data:[{
			   "devSubKeyId":1,
			   "subtypeId":1,
			   "subtypeName":"冰箱"
			},
			{
				"devSubKeyId":2,
				"subtypeId":1,
				"subtypeName":"电视"
			}],
	  code:0
	}


<table width="100%" style="border-spacing: 0;  border-collapse: collapse;">
	<tbody>
		<tr>
			<th width="16%">字段名称</th>
			<th width="11%">字段类型</th>
			<th width="74%">字段说明</th>
		</tr>
		<tr>
			<td>devSubKeyId</td>
			<td>int</td>
			<td>设备小类主键</td>
		</tr>
		<tr>
			<td>subtypeId</td>
			<td>int</td>
			<td>小类ID</td>
		</tr>
		<tr>
			<td>subtypeName</td>
			<td>string</td>
			<td>小类名称</td>
		</tr>
	</tbody>
</table>

### 5、修改产品

**接口调用请求说明**

	http请求方式: GET
	https://open.clife.cn/v1/web/open/product/update

**参数说明**

<table width="100%" style="border-spacing: 0;  border-collapse: collapse;">
	<tbody>
		<tr>
			<th width="16%">参数名称</th>
			<th width="11%">是否必须</th>
			<th width="11%">字段类型</th>
			<th width="62%">参数说明</th>
		</tr>
		<tr>
			<td>productId</td>
			<td>是</td>
			<td>int</td>
			<td>产品ID</td>
		</tr>	
		<tr>
			<td>productName</td>
			<td>否</td>
			<td>string</td>
			<td>产品名称</td>
		</tr>		
		<tr>
			<td>fileIcon</td>
			<td>否</td>
			<td></td>
			<td>产品图标</td>
		</tr>
		<tr>
			<td>remark</td>
			<td>否</td>
			<td>string</td>
			<td>产品描述</td>
		</tr>
		<tr>
			<td>bindType</td>
			<td>否</td>
			<td>int</td>
			<td>绑定类型</td>
		</tr>		
		<tr>
			<td>moduleId</td>
			<td>否</td>
			<td>int</td>
			<td>模块id</td>
		</tr>
		<tr>
			<td>productCode</td>
			<td>否</td>
			<td>string</td>
			<td>产品型号</td>
		</tr>
		<tr>
			<td>brandId</td>
			<td>否</td>
			<td>int</td>
			<td>品牌ID</td>
		</tr>
		<tr>
			<td>barCode</td>
			<td>否</td>
			<td>string</td>
			<td>条形码</td>
		</tr>
		<tr>
			<td>ssid</td>
			<td>否</td>
			<td>string</td>
			<td>ssid—AP模式显示</td>
		</tr>
		<tr>
			<td>ssidPassword</td>
			<td>否</td>
			<td>string</td>
			<td>ssid密码—AP模式显示</td>
		</tr>
</table>

**返回结果**

正确的Json返回结果：
	
	
	{
		"data": {},
		"code": 0
	}


### 5、复制产品

**接口调用请求说明**

	http请求方式: GET
	https://open.clife.cn/v1/web/open/product/copy

**参数说明**

<table width="100%" style="border-spacing: 0;  border-collapse: collapse;">
	<tbody>
		<tr>
			<th width="16%">参数名称</th>
			<th width="11%">是否必须</th>
			<th width="11%">字段类型</th>
			<th width="62%">参数说明</th>
		</tr>
		<tr>
			<td>productId</td>
			<td>是</td>
			<td>int</td>
			<td>产品ID</td>
		</tr>
	</tbody>
</table>

**返回结果**

正确的Json返回结果：
	
	
	{
		"data": {},
		"code": 0
	}

### 6、获取通讯方式列表

**接口调用请求说明**

	http请求方式: GET
	https://open.clife.cn/v1/web/open/product/bindtype/list

**参数说明**

<table width="100%" style="border-spacing: 0;  border-collapse: collapse;">
	<tbody>
		<tr>
			<th width="16%">参数名称</th>
			<th width="11%">是否必须</th>
			<th width="11%">字段类型</th>
			<th width="62%">参数说明</th>
		</tr>
	</tbody>
</table>

**返回结果**

正确的Json返回结果：
	
	
	{
		"code": 0,
		"data": [
					{
						"bindTypeId": 1,
						"bindTypeName": "WIFI"
					},
					{
						"bindTypeId": 2,
						"bindTypeName": "蓝牙"
					},
					{
						"bindTypeId": 3,
						"bindTypeName": "音频"
					},
					{
						"bindTypeId": 4,
						"bindTypeName": "GSM"
					},
					{
						"bindTypeId": 5,
						"bindTypeName": "红外"
					},
					{
						"bindTypeId": 6,
						"bindTypeName": "内置Android系统"
					},
					{
						"bindTypeId": 8,
						"bindTypeName": "Zigbee"
					}
			]
	}

<table width="100%" style="border-spacing: 0;  border-collapse: collapse;">
	<tbody>
		<tr>
			<th width="16%">字段名称</th>
			<th width="11%">字段类型</th>
			<th width="74%">字段说明</th>
		</tr>
		<tr>
			<td>bindTypeId</td>
			<td>int</td>
			<td>通讯方式ID</td>
		</tr>
		<tr>
			<td>bindTypeName</td>
			<td>string</td>
			<td>通讯方式名称</td>
		</tr>
	</tbody>
</table>

### 7、获取所有模组厂家列表

**接口调用请求说明**

	http请求方式: GET
	https://open.clife.cn/v1/web/open/product/moduleBrand/list

**参数说明**

<table width="100%" style="border-spacing: 0;  border-collapse: collapse;">
	<tbody>
		<tr>
			<th width="16%">参数名称</th>
			<th width="11%">是否必须</th>
			<th width="11%">字段类型</th>
			<th width="62%">参数说明</th>
		</tr>
		<tr>
			<td>moduleId</td>
			<td>是</td>
			<td>Integer</td>
			<td>通信模块类型: 1-WiFi，2-蓝牙，3-音频，4-GSM，5-红外，6-设备直连</td>
		</tr>
	</tbody>
</table>

**返回结果**

正确的Json返回结果：
	
	{
    "code": 0,
    "data": [
        {
            "moduleBrandId": 1,
            "brandCode": null,
            "brandName": "和而泰",
            "createTime": null
        },
        {
            "moduleBrandId": 2,
            "brandCode": null,
            "brandName": "汉枫",
            "createTime": null
        }
    ]
	}

<table width="100%" style="border-spacing: 0;  border-collapse: collapse;">
	<tbody>
		<tr>
			<th width="16%">字段名称</th>
			<th width="11%">字段类型</th>
			<th width="74%">字段说明</th>
		</tr>
		<tr>
			<td>moduleBrandId</td>
			<td>Integer</td>
			<td>模组厂家ID</td>
		</tr>
		<tr>
			<td>brandName</td>
			<td>string</td>
			<td>模组厂家</td>
		</tr>
	</tbody>
</table>

### 8、获取一个模组厂家对应的基本通信模块信息

**接口调用请求说明**

	http请求方式: GET
	https://open.clife.cn/v1/web/open/product/moduleType/list

**参数说明**

<table width="100%" style="border-spacing: 0;  border-collapse: collapse;">
	<tbody>
		<tr>
			<th width="16%">参数名称</th>
			<th width="11%">是否必须</th>
			<th width="11%">字段类型</th>
			<th width="62%">参数说明</th>
		</tr>
		<tr>
			<td>moduleId</td>
			<td>是</td>
			<td>Integer</td>
			<td>通信模块类型: 1-WiFi，2-蓝牙，3-音频，4-GSM，5-红外，6-设备直连</td>
		</tr>
		<tr>
			<td>moduleBrandId</td>
			<td>是</td>
			<td>Integer</td>
			<td>模组厂家ID</td>
		</tr>
	</tbody>
</table>

**返回结果**

正确的Json返回结果：
	
	
	{
    "code": 0,
    "data": [
        {
            "moduleId": 63,
            "moduleName": "QCA4531 / AP / Clife+HTTP"
        }
    ]
	}

<table width="100%" style="border-spacing: 0;  border-collapse: collapse;">
	<tbody>
		<tr>
			<th width="16%">字段名称</th>
			<th width="11%">字段类型</th>
			<th width="74%">字段说明</th>
		</tr>
		<tr>
			<td>moduleId</td>
			<td>Integer</td>
			<td>板卡标识</td>
		</tr>
		<tr>
			<td>moduleName</td>
			<td>string</td>
			<td>IC型号/smarklink方式/协议类型</td>
		</tr>
	</tbody>
</table>

