---
layout: post
title:  " Node :: Json to CSV "
date:   2017-10-22
excerpt: " Json to CSV "
cate : "post"
tag:
- Node.js
---


## Code
{% highlight JavaScript %}

const fs = require('fs');
const json2csv = require('json2csv');

let field2 = ['title', 'singer'];
let music = [
	{
		"title" : "너를 찾아서",
		"singer" : "윤종신"
	},
	{
		"title" : "선물",
		"singer" : "멜로망스"
	},
	{
		"title" : "썸탈거야",
		"singer" : "볼빨간사춘기"
	}
];

let object = json2csv({
	data : music,
	fields : field2 // field2를 fields로 해도 Don't Care !
});
fs.writeFile('./music.csv', object, function(err){
	if(err){
		console.log("write csv error : "+ err);
	} else{
		console.log("successful write csv");
	}
})

{% endhighlight %}

---

## File

[Json2Csv.js](https://github.com/goodGid/Node.js/blob/master/Source/Json2Csv.js)


---
## Review

* Excel형식의 'music.csv' 파일이 생성 된다.