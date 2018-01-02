# vue-quiz
简单的选项题页面，基于vue2.0
## Demo
[https://ciming.github.io/vue-quiz/](https://ciming.github.io/vue-quiz/)
## Json

```json
{
  "questions": [
    {
      "title": "工笔是哪种绘画形式的技法",
      "answers": {
        "A": "水彩画",
        "B": "油画",
        "C": "水粉画",
        "D": "国画"
      },
      "correctAnswer": "D"
    },
    {
      "title": "冰激凌”是从哪国传进的外来语",
      "answers": {
        "A": "英国",
        "B": "法国",
        "C": "美国",
        "D": "俄国"
      },
      "correctAnswer": "A"
    },
    {
      "title": "谬种流传”最早是宋朝人批评当时的",
      "answers": {
        "A": "官场黑暗",
        "B": "科举制度",
        "C": "社会风气",
        "D": "诗词风格"
      },
      "correctAnswer": "B"
    }
  ]
}
```

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For detailed explanation on how things work, checkout the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
