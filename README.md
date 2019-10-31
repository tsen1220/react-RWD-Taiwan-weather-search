# 目錄

[啟動](#啟動)

[簡介](#簡介)

如果你喜歡，請給我一顆星，我會很感謝你。
If you like this, please give me a star. Thank you!!

# 啟動

React 開發。

請先安裝 Node 與 Npm。

並輸入下面的指令安裝 modules。

```
$ npm install
```

啟動開發伺服器

```
$ npm start
```

或是打包過後的檔案啟動伺服器

```
$ npm run build
$ serve -s build
```

# 簡介

這是可以查詢即時氣象資料的網頁，串接中央氣象局的 API，以求得到我們想要的資料，此外有製作 RWD，增加使用者的體驗。
API資料處理的部分就不贅述，在這裡使用component的props，只要資料更新了就可以呈現不一樣的地區氣象資訊。
而指定頁面使用了react-router-dom來設定路由。


```
component:
  const location = this.state.location.map((locate, index) => {
      return (
        <Box
          key={index}
          location={this.state.location[index]}
          start={this.state.startTime[index]}
          end={this.state.endTime[index]}
          temperature={this.state.temperature[index]}
          rain={this.state.rain[index]}
          condition={this.state.Condition[index]}
        />
      );
    });

    return <div className="detail1">{location}</div>;
  }

```

```
Router setting:
import React from "react";
import { Route } from "react-router-dom";

const BaseRouter = () => (
  <div>
    <Route exact path="/" component={yourcomponent} />
    <Route exact path="/:value" component={yourcomponent} />
  </div>
);

detail params: 
state={
 url:this.props.match.params.value
}

```

首頁:

<img src='https://raw.githubusercontent.com/tsen1220/ReactRWDTaiwanWeatherSearch/master/introimage/Home.jpg' alt=''>

RWD 頁面:

<img src='https://raw.githubusercontent.com/tsen1220/ReactRWDTaiwanWeatherSearch/master/introimage/RWDHome.jpg' alt=''>

可以藉由上方的選項選擇想看的城市資料。

<img src='https://raw.githubusercontent.com/tsen1220/ReactRWDTaiwanWeatherSearch/master/introimage/Detail.jpg' alt=''>

RWD 指定城市資料頁面:

<img src='https://raw.githubusercontent.com/tsen1220/ReactRWDTaiwanWeatherSearch/master/introimage/RWDDetail.jpg' alt=''>
