# @author mycherubs
# 作者仓库:https://github.com/mycherubs/QinglongScript.git
# 觉得不错麻烦点个star谢谢
# 自行修改10行的api，为必填.
# 需要在天行注册获取api(https://www.tianapi.com/console/,数据管理-我的密钥key)并申请相应接口才能使用，https://www.tianapi.com/list/
import requests
import json
import notify

api = "" # 自行填写申请的API
count = 2 # 相同类型推文的数量，默认是两条

xwurl = f'https://apis.tianapi.com/everyday/index?key={api}' #英语
sjurl = f'https://apis.tianapi.com/moodpoetry/index?key={api}' #情绪诗句

urls = [xwurl,sjurl] # 按照格式填写你要推送的内容对应的url，默认是朋友圈文案、舔狗日志和毒鸡汤

contents = ""
for url in urls:
	for i in range(count):
  		response = requests.get(url)
  		data = json.loads(response.text)
  		contents += data['result']['content'] + "\n" + "\n"
notify.send("今日语录", contents)
