# 安裝總攬
> 2024/2/23 更新 by [Harry](https://steamcommunity.com/profiles/76561198026784913)
- [安裝總攬](#安裝總攬)
	- [安裝Stripper](#安裝stripper)
	- [安裝l4dtoolz](#安裝l4dtoolz)
	- [安裝TickrateEnabler](#安裝tickrateenabler)
	- [安裝國家與城市的資料庫](#安裝國家與城市的資料庫)
	- [其他](#其他)

- - - -
## 安裝Stripper
* Stripper 用途是什麼?
* 修改地圖，可以在地圖上新增各種障礙物、道具、機關事件等等
	* [影片範例](https://www.youtube.com/watch?v=I_-QSn8F8Cs)
* 把地圖改造成迷宮都不是問題
	* [終極地圖](https://github.com/fbef0102/L4D2-Unlimited-Map)
	* [造物插件](https://github.com/fbef0102/L4D1_2-Plugins/tree/master/l4d2_spawn_props)

* 安裝步驟
	1. 到[Stripper:Source網站](https://forums.alliedmods.net/showthread.php?t=39439)點擊SNAPSHOTS
	<br/>![image](https://user-images.githubusercontent.com/12229810/206858893-688521a3-6f69-469b-8a80-92470ab13db6.jpg)

	2. 往下找最新的版本，依照各自的電腦系統下載對應的版本
	<br/>![image](https://user-images.githubusercontent.com/12229810/206859034-5e0c5e5e-fcbd-4329-9d27-5298025c4616.png)

	3. 解壓縮並移動檔案到伺服器相同的路徑上!最後addons資料夾內看起來如圖片所示，多一個 ```stripper``` 資料夾
	<br/>![image](https://user-images.githubusercontent.com/12229810/206859157-102eceeb-e5c7-4fbd-95b9-d01d2c82d963.png)

	4. 重啟伺服器，控制台輸入```stripper_version```確認安裝成功
		```php
		] stripper_version
		"stripper_version" = "1.2.2"
		notify singleplayer replicated
		- Stripper Version
		```

- - - -
## 安裝l4dtoolz
* l4dtoolz 用途是什麼?
* 解鎖伺服器人數上限，有八位以上的玩家可以進入伺服器遊玩
	<br/>![image](https://user-images.githubusercontent.com/12229810/206860045-582a79ea-8453-45a7-b73a-4ecfd051be6b.jpg)
* 最多只能有31位玩家同時在伺服器裡面 (不能超過31人，否則伺服器會崩潰)
	* [多人插件](https://github.com/fbef0102/L4D1_2-Plugins/tree/master/l4dmultislots)
	* [如何戰役模式開八人房](/Tutorial_%E6%95%99%E5%AD%B8%E5%8D%80/Chinese_%E7%B9%81%E9%AB%94%E4%B8%AD%E6%96%87/Game/L4D2/8%E4%BD%8D%E7%8E%A9%E5%AE%B6%E9%81%8A%E7%8E%A9%E6%88%B0%E5%BD%B9%E6%A8%A1%E5%BC%8F/)

* 安裝步驟
	1. 到[l4dtoolz](https://github.com/fbef0102/l4dtoolz/releases)，根據你的遊戲與系統選擇檔案下載
	<br/>![image](https://github.com/fbef0102/Game-Private_Plugin/assets/12229810/6151a17e-6915-4fa0-b18f-05c6ea642ef6)

	2. 解壓縮並移動檔案到伺服器相同的路徑上!最後addons資料夾內看起來如圖片所示，多一個 ```l4dtoolz``` 資料夾
	<br/>![image](https://user-images.githubusercontent.com/12229810/206860306-d0fead16-9997-410d-93cc-bca7109d5977.png)

	3. 到cfg/server.cfg寫上以下指令
		* 沒有server.cfg檔案則新建
			```php
			// 18位真人玩家可以加入伺服器，自行修改此數值 (範圍1~31)
			// 此數值為真人玩家的允許人數
			sv_maxplayers 18

			// 顯示給外面玩家看到的伺服器空位人數
			sv_visiblemaxplayers 18

			// 為1時，動態大廳匹配制度，可能無法直接透過IP連線伺服器，不能使用sv_cheats 1
			// 為0時，關閉動態大廳匹配制度，可以使用sv_cheats 1
			sv_allow_lobby_connect_only 0

			// 為1時，強制sv_allow_lobby_connect_only為0
			// 為1時，移除lobby reservation cookie
			sv_force_unreserved 1
			```

	4. 遊戲預設玩家上限只到18位，如果要改變玩家上限
		* 玩家上限 = 真人玩家 + AI Bot + AI 特感 + 旁觀者
		<br/>![image](https://github.com/fbef0102/Game-Private_Plugin/assets/12229810/1d18fe5a-cc3c-4c37-b567-81a9f69f3721)
		* 使用其他開服方式或者是linux系統，請輸入啟動參數```-maxplayers 31```
		* 不能超過31人，否則伺服器會崩潰
		<br/>![image](https://github.com/fbef0102/Game-Private_Plugin/assets/12229810/accc68ae-7d95-464e-b0b0-8d90a9a03d9f)

	5. 啟動伺服器，控制台輸入```meta list```確認安裝成功
		```php
		] meta list
		Listing 11 plugins:
		[04] L4DToolZ (1.1.0.2) by Accelerator, Ivailosp
		```

- - - -
## 安裝TickrateEnabler
* TickrateEnabler 用途是什麼?
* 解鎖伺服器Tickrate只有30的上限，可以突破到100tick
	* 不知道Tickrate是甚麼請自行Google
	* 簡單說，Tickrate越高越能夠帶來非常流暢的遊戲體驗，精準的射擊判定、連貫的動作，相當於伺服器端的fps
* 把Tickrate想成是一種更新伺服器狀態的頻率，一秒內更新次數越多，越消耗更多電腦資源，所以高Tickrate很吃電腦的cpu，自行斟酌安裝

* 安裝步驟
	1. 到[Tickrate-Enabler](https://github.com/fbef0102/Tickrate-Enabler/releases)，根據你的遊戲與系統選擇檔案下載
	<br/>![image](https://github.com/fbef0102/Game-Private_Plugin/assets/12229810/44f26cc8-25b0-4308-a52d-1e7496b57596)

	2. 解壓縮並移動檔案到伺服器相同的路徑上!最後addons資料夾內看起來如圖片所示，多一個 ```tickrate_enabler``` 資料夾
	<br/>![image](https://user-images.githubusercontent.com/12229810/206860975-1bc616cc-5e1c-4bfb-88b4-af699e302287.png)

	3. 到cfg/server.cfg寫上以下指令
		* 沒有server.cfg檔案則新建
			```php
			// 這是100 Tick的設定，可以自由修改數值
			sm_cvar sv_minrate 				"100000" 	// tickrate * 1000
			sm_cvar sv_maxrate 				"100000" 	// tickrate * 1000
			sm_cvar sv_minupdaterate 		"101"	 	// tickrate +1
			sm_cvar sv_maxupdaterate 		"101"		// tickrate +1
			sm_cvar sv_mincmdrate 			"101"		// tickrate +1
			sm_cvar sv_maxcmdrate 			"101"		// tickrate +1
			sm_cvar rate					"100000" 	// tickrate * 1000
			sm_cvar net_splitpacket_maxrate "50000" 	// (tickrate÷2) * 1000
			sm_cvar fps_max					"0"
			```
	
	4. 伺服器啟動選項輸入參數
		* ```-tickrate 100```
		
	5. 重啟伺服器，控制台輸入```plugin_print```確認安裝成功
		```php
		] plugin_print
		1:　"Tickrate_Enabler 1.5, ProdigySim"
		```

	6. 進入遊戲後，打開遊戲控制台輸入```net_graph 4```，會看到有一堆網路數據出現在你的螢幕上，確認Tickrate 為 100
	<br/>![image](https://user-images.githubusercontent.com/12229810/206861890-a37cf9d9-f5cc-4ec2-b3d3-07991cd89e1f.jpg)

	> __Warning__ 
	> * 高Tickrate很吃電腦的cpu，可以自行降低成60 tick、45 tick
	> * 調整tickate必須一起修改server.cfg與啟動選項

* <details><summary>問題1: 為什麼windows系統下伺服器的Tickrate只能跑到64?</b></summary>

![image](https://user-images.githubusercontent.com/12229810/206862598-8f36433c-bcce-4edf-b8b9-7843d0f8534a.jpg)

* 原因: windows 10 的問體，windows系統對遊戲伺服器不怎麼友善，
* 解決方式: 
	* 法一：去跟微軟抱怨
	* 法二：windows降級到windows 7
	* 法三：租一台linux系統
	* 法四：[從大廳匹配到專屬伺服器](/Tutorial_%E6%95%99%E5%AD%B8%E5%8D%80/Chinese_%E7%B9%81%E9%AB%94%E4%B8%AD%E6%96%87/Server/%E5%AE%89%E8%A3%9D%E4%BC%BA%E6%9C%8D%E5%99%A8%E8%88%87%E6%8F%92%E4%BB%B6/README.md#如何從大廳匹配到專屬伺服器)，可以將tickrate變回100，至於為何會這樣，我也不知道
</details>

* <details><summary>問題2: 為什麼我的tickrate網路數據沒有到100?</b></summary>

![image](https://user-images.githubusercontent.com/12229810/207044622-5c0145a3-85be-4eef-b3ec-59ec6fcaba01.png)

* 原因: 受限於你的遊戲內fps影響，只會影響你這位玩家，你的遊戲內fps超過100以上才能享有100 tickrate
<br/>![image](https://user-images.githubusercontent.com/12229810/207044800-04d8cbcb-610a-4ede-8896-d8cf992b8719.png)
* 解決方式: 
	* 法一：調高遊戲的fps，到選項->視訊->進階設定->等待垂直同步改成"已停用"，這選項能夠解鎖遊戲的fps
	<br/>![image](https://user-images.githubusercontent.com/12229810/207045656-764b59f4-94d9-4af8-aebb-1872c631a111.png)
	* 法二：法一沒有用那就去升級你的顯卡
</details>

- - - -
## 安裝國家與城市的資料庫
* 何時需要用到?
* 有插件需要抓取玩家的IP、國家、城市、地區等等
	* 像是 [cannounce](https://github.com/fbef0102/L4D1_2-Plugins/tree/master/cannounce)
* 有安裝geoipcity.ext, geoip2.ext等等
	* 已經過時，請移除這些檔案並升級sourcemod v1.11以上

* 安裝步驟
	1. 註冊 [maxmind.com](https://www.maxmind.com/en/geolite2/signup)

	2. [到個人帳戶](https://www.maxmind.com/en/account/) -> My License Keys -> Create new license key

	3. 到這個網頁: https://www.maxmind.com/en/accounts/XXXXXX/geoip/downloads
		* XXXXXX 是你的帳戶ID
		<br/>![ID](https://user-images.githubusercontent.com/12229810/205027221-05798d84-08ab-40c3-8d54-ef66a892c295.jpg)

	4. 搜尋 "GeoLite2 Country" 和 "GeoLite2 City" -> 下載資料庫
	<br/>![GeoLite2 Country](https://user-images.githubusercontent.com/12229810/204966692-ac339bc6-4760-4acc-b320-b776d46e7064.jpg)
	<br/>![GeoLite2 City](https://user-images.githubusercontent.com/12229810/204966795-a57a5949-abcf-4127-9325-90b9fdb8124f.jpg)

	5. 放 GeoLite2-City.mmdb 與 GeoLite2-Country.mmdb 到路徑 addons/sourcemod/configs/geoip/ 資料夾
	<br/>![image](https://user-images.githubusercontent.com/12229810/222086453-ee59e6c3-e61c-4a16-9aa7-8eb9d39a4d37.png)
	
	6. 重新編譯有使用 geoip.inc 的插件，大功告成

- - - -
## 其他
* [安裝伺服器與插件](/Tutorial_教學區/Chinese_繁體中文/Server/安裝伺服器與插件)
* [安裝區域房與插件](/Tutorial_教學區/Chinese_繁體中文/Server/安裝區域房與插件)
* [Questions_問題區](/Questions_問題區/Chinese_繁體中文/伺服器)
