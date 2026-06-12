
# 周易排盘算法 API 文档
## Yi-Jing Divination Algorithm API Documentation

本文档描述周易排盘系统中各术数模块的算法接口和数据结构。所有模块均为纯前端 JavaScript 实现，可在浏览器中直接调用。

---

## 目录 | Table of Contents

1. [通用规范](#通用规范)
2. [四柱八字模块](#四柱八字模块)
3. [紫微斗数模块](#紫微斗数模块)
4. [奇门遁甲模块](#奇门遁甲模块)
5. [大六壬模块](#大六壬模块)
6. [七政四余模块](#七政四余模块)
7. [神煞模块](#神煞模块)
8. [工具函数](#工具函数)

---

## 通用规范

### 日期输入格式

所有涉及公历日期的输入，统一使用以下格式：

| 格式 | 示例 | 说明 |
| :--- | :--- | :--- |
| `YYYY-MM-DD` | `2026-06-12` | 年月日 |
| `YYYY-MM-DD HH:MM:SS` | `2026-06-12 14:30:00` | 完整时间 |

### 时区

默认使用 **UTC+8（北京时间）**，不自动转换时区。

### 返回数据格式

所有算法函数返回的数据格式为 JSON 对象：


{
  "success": true,           // 是否成功
  "code": 0,                 // 错误码（0=成功）
  "message": "排盘成功",      // 提示信息
  "data": { ... }            // 排盘结果数据
}
错误码表
code	说明
0	成功
1001	日期格式错误
1002	日期超出有效范围
1003	时区参数无效
2001	出生时间无效
2002	性别参数无效
四柱八字模块
文件位置
wujibazi 目录 / index.js 中的八字相关函数

核心函数
getBaZi(birthDate, birthTime, gender, isLeap)
计算四柱八字（年柱、月柱、日柱、时柱）。

参数：

参数名	类型	必填	说明
birthDate	string	是	出生日期，格式 YYYY-MM-DD
birthTime	string	是	出生时间，格式 HH:MM:SS
gender	string	是	性别：'M' 男，'F' 女
isLeap	boolean	否	是否为闰月，默认 false
返回示例：

javascript
{
  "success": true,
  "data": {
    "yearPillar": {
      "stem": "丙",
      "branch": "午",
      "stemBranch": "丙午",
      "element": "火"
    },
    "monthPillar": {
      "stem": "甲",
      "branch": "午",
      "stemBranch": "甲午",
      "element": "木"
    },
    "dayPillar": {
      "stem": "壬",
      "branch": "子",
      "stemBranch": "壬子",
      "element": "水"
    },
    "hourPillar": {
      "stem": "庚",
      "branch": "子",
      "stemBranch": "庚子",
      "element": "金"
    },
    "fullBaZi": "丙午 甲午 壬子 庚子",
    "hiddenStems": { ... },   // 藏干
    "tenGods": { ... }        // 十神
  }
}
getDaYun(bazi, gender, birthDate)
计算大运。

参数：

参数名	类型	必填	说明
bazi	object	是	getBaZi 返回的八字对象
gender	string	是	性别
birthDate	string	是	出生日期
返回示例：

javascript
{
  "success": true,
  "data": {
    "startAge": 3,           // 起运年龄
    "startDate": "2029-03-15", // 起运日期
    "dayuns": [
      { "range": "3-13", "pillar": "癸巳", "heaven": "癸", "earth": "巳" },
      { "range": "13-23", "pillar": "壬辰", "heaven": "壬", "earth": "辰" }
    ]
  }
}
getLiuNian(year, dayunPillar)
计算流年运势。

参数：

参数名	类型	必填	说明
year	number	是	公历年份
dayunPillar	string	是	当前大运干支，如 "癸巳"
紫微斗数模块
文件位置
index.js 中的紫微相关函数

核心函数
getZiWeiDouShu(birthDate, birthTime, gender)
计算紫微斗数命盘。

参数：同八字模块

返回示例：


{
  "success": true,
  "data": {
    "mingPalace": {          // 命宫
      "palaceIndex": 3,      // 宫位序号（1-12）
      "palaceName": "申",
      "stars": ["紫微", "天府"],
      "hua": "禄"            // 四化
    },
    "palaces": [             // 十二宫
      { "name": "命宫", "index": 3, "stars": ["紫微"], "hua": "禄" },
      { "name": "兄弟宫", "index": 4, "stars": ["天机"], "hua": null },
      { "name": "夫妻宫", "index": 5, "stars": ["太阳"], "hua": "权" }
      // ... 共12宫
    ],
    "earthlyBranches": ["子","丑","寅","卯","辰","巳","午","未","申","酉","戌","亥"],
    "heavenlyStems": ["甲","乙","丙","丁","戊","己","庚","辛","壬","癸"],
    "fourTransformations": {  // 四化
      "禄": "廉贞",
      "权": "破军",
      "科": "武曲",
      "忌": "太阳"
    }
  }
}
getZhiWeiByPalace(palaceName, starsMap)
根据宫位名称获取该宫的星曜分布。

参数：

参数名	类型	必填	说明
palaceName	string	是	宫位名称，如 "命宫"、"财帛宫"
starsMap	object	是	getZiWeiDouShu 返回的完整数据
奇门遁甲模块
文件位置
index.js 中的奇门相关函数

核心函数
getQiMenDunJia(date, time, jieQi)
计算奇门遁甲时盘。

参数：

参数名	类型	必填	说明
date	string	是	日期，格式 YYYY-MM-DD
time	string	是	时辰，格式 HH:MM:SS
jieQi	string	否	节气名称，自动计算时可留空
返回示例：

javascript
{
  "success": true,
  "data": {
    "juNumber": 3,                    // 局数（阳遁/阴遁）
    "juType": "阳遁",                 // 阳遁/阴遁
    "solarTerm": "夏至",              // 当前节气
    "nineStars": [                   // 九星
      { "star": "天蓬星", "palace": "坎", "status": "值符" },
      { "star": "天芮星", "palace": "坤", "status": "虚" }
    ],
    "eightGates": [                  // 八门
      { "gate": "休门", "palace": "坎", "status": "值使" },
      { "gate": "生门", "palace": "艮", "status": "虚" }
    ],
    "eightGods": [                   // 八神
      { "god": "值符", "palace": "坎" },
      { "god": "螣蛇", "palace": "坤" }
    ],
    "palaces": {                     // 九宫信息
      "坎": { "earth": "水", "number": 1, "goodBad": "吉" }
      // ...
    }
  }
}
getGoodDirection(qiMenData, purpose)
根据奇门盘求吉方。

参数：

参数名	类型	必填	说明
qiMenData	object	是	getQiMenDunJia 返回的数据
purpose	string	否	目的：'business'、'love'、'health'
大六壬模块
文件位置
index.js 中的六壬相关函数

核心函数
getDaLiuRen(date, time, isDay)
计算大六壬课式。

参数：

参数名	类型	必填	说明
date	string	是	日期
time	string	是	时辰
isDay	boolean	否	是否为白天（用于贵人顺逆）
返回示例：

javascript
{
  "success": true,
  "data": {
    "fourLessons": [                 // 四课
      { "top": "甲", "bottom": "子", "relationship": "上克下" },
      { "top": "寅", "bottom": "辰", "relationship": "下贼上" }
    ],
    "threeTransmissions": [          // 三传
      { "level": "初传", "pillar": "申", "type": "贼克" },
      { "level": "中传", "pillar": "午", "type": "比用" },
      { "level": "末传", "pillar": "辰", "type": "涉害" }
    ],
    "yearGeneral": "午",             // 年将（太岁）
    "monthGeneral": "未",            // 月将
    "dayGeneral": "青龙",            // 日将（贵人）
    "hourGeneral": "白虎"            // 时将
  }
}
七政四余模块
文件位置
七政四余技术文档.doc（完整文档），index.js 中的相关函数

核心函数
getQiZhengSiYu(date, time, location)
计算七政四余星曜排盘。

参数：

参数名	类型	必填	说明
date	string	是	日期
time	string	是	时间
location	object	否	地理位置 { longitude, latitude }
返回示例：

javascript
{
  "success": true,
  "data": {
    "sevenStars": [                  // 七政（日月五星）
      { "name": "日", "position": "午宫5度", "speed": "顺行" },
      { "name": "月", "position": "子宫20度", "speed": "顺行" },
      { "name": "木星", "position": "寅宫15度", "speed": "顺行" }
    ],
    "fourRemainders": [              // 四余
      { "name": "紫炁", "position": "亥宫8度" },
      { "name": "月孛", "position": "巳宫12度" },
      { "name": "罗睺", "position": "丑宫0度" },
      { "name": "计都", "position": "未宫0度" }
    ],
    "twelvePalaces": {               // 十二宫
      "命宫": { "start": "寅宫0度", "end": "卯宫30度", "stars": ["日"] }
    }
  }
}
📌 注意：七政四余算法较为复杂，完整实现请参考 七政四余技术文档.doc。

神煞模块
文件位置
shensha.js

核心函数
getShenSha(year, month, day, hour, dayPillar)
计算各种神煞。

参数：

参数名	类型	必填	说明
year	number	是	年份
month	number	是	月份
day	number	是	日期
hour	number	是	时辰（0-23）
dayPillar	string	是	日柱干支，如 "壬子"
返回示例：

javascript
{
  "success": true,
  "data": {
    "tianYiNoble": "酉",           // 天乙贵人
    "taoHua": "午",               // 桃花
    "wenChang": "巳",             // 文昌
    "wenQu": "申",                // 文曲
    "yiMa": "寅",                 // 驿马
    "jiangXing": "子",            // 将星
    "guChen": "戌",               // 孤辰
    "guaSu": "辰"                 // 寡宿
  }
}
工具函数
convertToLunar(solarDate)
公历转农历。

javascript
convertToLunar("2026-06-12");
// 返回: { year: 2026, month: 5, day: 27, isLeap: false, yearZodiac: "马" }
getSolarTerm(year, month, day)
获取节气。

javascript
getSolarTerm(2026, 6, 6);
// 返回: { name: "芒种", time: "2026-06-06 03:45:00" }
getGanZhiByYear(year)
获取年干支。

javascript
getGanZhiByYear(2026);
// 返回: { stem: "丙", branch: "午", full: "丙午" }
getTimePillar(dayPillar, hour)
根据日干和时辰计算时柱。

javascript
getTimePillar("壬子", 14);  // 14:00-15:00 属未时
// 返回: { stem: "丁", branch: "未", full: "丁未" }
调用示例（完整前端集成）
html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>周易排盘调用示例</title>
</head>
<body>
    <script src="index.js"></script>
    <script>
        // 排八字示例
        var bazi = getBaZi("1990-05-15", "08:30:00", "M", false);
        if (bazi.success) {
            console.log("八字:", bazi.data.fullBaZi);
            console.log("日柱:", bazi.data.dayPillar.stemBranch);
        }
        
        // 排紫微斗数示例
        var ziwei = getZiWeiDouShu("1990-05-15", "08:30:00", "M");
        if (ziwei.success) {
            console.log("命宫主星:", ziwei.data.mingPalace.stars);
        }
        
        // 排奇门遁甲示例
        var qimen = getQiMenDunJia("2026-06-12", "14:30:00");
        if (qimen.success) {
            console.log("当前局数:", qimen.data.juNumber + qimen.data.juType);
        }
    </script>
</body>
</html>
联系支持
如 API 对接中遇到问题，可通过以下方式联系我们：

联系方式	账号
 - **Telegram**: @fox_lovemyself
- **Email**: zyue02561@gmail.com
*最后更新：2026-06-12 | 版本：v1.0*
