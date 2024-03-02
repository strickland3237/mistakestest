---
layout: posts
title:  "客製化自己的minimal-mistake網頁(持續更新中)"
categories: tutorial
date:   2024-03-02 00:44:13 +0800
excerpt: 本篇文會教你更改一些minimal-mistakes的一些type(持續更新中)
words_per_minute: 30
---

我這裡應該也會記錄我改了哪些，畢竟這篇文有一半就是寫給自己看的。

### 萬用的_config.yml

### _variable.scss 環境變數設定
- $xlarge: 由於我的電腦螢幕較寬，因此將此參數從1280px調到1440px比較舒服

### 加上計算各國來訪人數計數器

#### 1. 創建計數器
到[flagcounter網站](https://flagcounter.com/)客製化自己的計數器並取得圖片網址
#### 2. 連結網站
打開_config.yml並在defaults的地方加上以下程式碼
{% highlight ruby %}
defaults:
  - scope:
      path: ""
    values:
      sidebar:
        - text: <\html copy from previous>
{% endhighlight %}

#### 3. 設定手機閱讀樣式
![](/assets/images/uglyflagcounter.png){: .align-center}
雖然我們設定好了，但是在手機模式下仍然會變得相當醜，如上圖，因此我們要手動將這個計數器在手機模式時關掉。
首先把原本網站copy的html裡面加上一個類別：
{% highlight html %}
<a class='author__flagcounter'></a>
{% endhighlight %}
這個類別的名稱是我自訂的。接著打開_sidebar.scss檔，在最下面加上
{% highlight css %}
/*
    flag__counter
    ========================== */

.author__flagcounter{
  display:none;
  @include breakpoint($large){
    display:block
  }
}
{% endhighlight %}
這樣就可以讓計數器在手機模式時消失了。
### 加上favicon
到[這個網站](https://realfavicongenerator.net/)將想做的圖片丟進去，之後按照上面的步驟應該會有一個favicon包與一串html程式碼。
將這些程式碼丟到`_includes/head/custom.html`並將圖片放在合適的位置即可。

