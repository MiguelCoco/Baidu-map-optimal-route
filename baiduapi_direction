import json
import requests
"""基于百度地图API，规划从家到单位的最优路线"""
url = 'http://api.map.baidu.com/direction/v2/transit?'

#参照百度WEB服务API生成请求参数字典
required_patameters = {
	'origin':'39.930844,116.47778',#北京朝阳区水锥子小区
	'destination':'40.047865,116.447482',#北京朝阳区中国铁建广场
	'coord_type':'bd09ll',
	'tactics_incity':4,
	'page_size':3,
	'output':'json',
	'ak':'G4rOuo6mHVvNtSU7PpRLTsWdz51oT4ho',
	}
#使用requests模块、方法get（）爬取文件
request = requests.get(url,required_patameters)
#json解析
return_patameters = request.json()
best_routes = return_patameters['result']['routes'][0]

#最优出行路线概览（距离、时间、交通费用）
total_br_distance = best_routes['distance']
total_br_time = best_routes['duration']
total_br_price = best_routes['price']

#具体步骤
steps = best_routes['steps']
steps_0 = steps[0][0]['instructions']
steps_1 = steps[1][0]['instructions']
steps_2 = steps[2][0]['instructions']
steps_3 = steps[3][0]['instructions']
steps_4 = steps[4][0]['instructions']

#打印路线概览及详细步骤
print("The best routes: " + "\n\tThe total distance is " + str(total_br_distance) + " meter,"
	+ "may be you will spend " + str(total_br_time) + " second and the price is " + str(total_br_price)
	+ " yuan!")

print("Specific steps: " + "\n\tFirst step is " + steps_0 + "\n\tSecond step is " + steps_1
	+ "\n\tThird step is " + steps_2 + "\n\tFourth step is " + steps_3 + "\n\tLast step is "
	+ steps_4)
