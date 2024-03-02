---
layout: posts
title:  "在minimal-mistakes的框架裡使網頁使用者可以任意切換主題"
categories: tutorial
date:   2024-03-02 00:44:13 +0800
excerpt: 本篇文會教你如何讓minimal-mistakes主題的網頁可以使網頁使用者自由切換主題，像是白天與黑夜主題
words_per_minute: 30
---

## 前言

> 深夜來臨，多少碼農還坐在電腦面前努力coding，就因為那誘人的薪水；多少年輕人還苦撐著在被窩中划手機，就因為他們手機成癮以及另一端在等待他們回訊息的戀人。此時，黑夜模式是他們的救星，如果沒有這個，他們不知道會換多少副眼鏡...  

架好minimal-mistakes網站後，看著網站那多達10種的主題，很想每個都用過，但是minimal-mistakes預設一次只能部屬一種主題，真是太無趣了，並且，現在許多網站都新增了深夜模式好可以保護眼睛，順著這個思維，我有了一個想法：何不試試能否讓使用者自訂主題呢？這樣一切事情都解決了。

## 正文開始

### 1. 增加主題

到_config.yml新增主題，這裡我們以原本是aqua主題但想加dark主題作為第二主題來當範例。
{% highlight ruby %}
minimal_mistakes_skin: "aqua"
minimal_mistakes_skin_dark: "dark"
{% endhighlight %}

### 2. 增加預先讀取scss檔
在`_assets/css/`的檔案夾新增一個檔案名叫`theme2.scss`，並將裡面內容替換成以下程式碼，只要讀main.scss或是theme2.scss就會得到不同的主題。
{% highlight css %}
---
# Only the main Sass file needs front matter (the dashes are enough)
---

@charset "utf-8";

@import "minimal-mistakes/skins/ { { site.minimal_mistakes_skin_dark | default: 'default' } } "; // skin
@import "minimal-mistakes"; // main partials
{% endhighlight %}

### 3. 增加html link元素至meta區

在`_include/head.html`檔案裡找到下面這一行：
{% highlight html %}
<link rel="stylesheet" href="{{ '/assets/css/main.css' | relative_url }}">
{% endhighlight %}

將其內容更改成為
{% highlight html %}
<link rel="stylesheet" href="{{ '/assets/css/main.css' | relative_url }}" id="theme_source">
<link rel="stylesheet alternate" href="{{ '/assets/css/theme2.css' | relative_url }}" id="theme_source_2">
{% endhighlight %}
這樣雖然html檔會link到下面的theme2.cscc檔，但因為後面加了alternate導致無法連成功

### 4. 增加script檔

在同一個檔案下加入以下內容：
{% highlight html %}
<script>
    let theme = sessionStorage.getItem('theme');
    if(theme === "dark")
    {
      sessionStorage.setItem('theme', 'dark');
      node1 = document.getElementById('theme_source');
      node2 = document.getElementById('theme_source_2');
      node1.setAttribute('rel', 'stylesheet alternate'); 
      node2.setAttribute('rel', 'stylesheet');
    }
    else
    {
      sessionStorage.setItem('theme', 'aqua');
    }
</script>
{% endhighlight %}
這個script檔主要會在更新網頁時維持選定的主題，使網頁主題不會隨著更換頁面而跑掉。

### 5. 加入切換按鍵

在想要加入按鍵的地方加入以下內容（我是單獨創一個頁面出來）
{% highlight html %}
<button type="button" class="btn btn--primary" onclick="node1=document.getElementById('theme_source');node2=document.getElementById('theme_source_2');if(node1.getAttribute('rel')=='stylesheet'){node1.setAttribute('rel', 'stylesheet alternate'); node2.setAttribute('rel', 'stylesheet');sessionStorage.setItem('theme', 'dark');}else{node2.setAttribute('rel', 'stylesheet alternate'); node1.setAttribute('rel', 'stylesheet');sessionStorage.setItem('theme', 'aqua');} return false;">切換白天/黑夜模式</button>
{% endhighlight %}
這個按鍵主要就是在按下去的時候會觸發按鍵裡面一長串動作，這個動作會偵測兩個link目前的ref標籤，然後來選擇要切換到白天還是黑夜主題。至此，我們的主題切換按鍵就完成了。

## 結語

這次我們成功做出一個可以切換白天/黑夜模式的按鍵，如果前面的思維都理解並且對前端有一些基礎的話，應該可以試著跟我一樣新增五個主題的按鍵試試，你可能會問要這麼多主題做什麼，我只能說自己的網站可以隨時切換超多不同主題就是爽！

## reference

1. [Allow user to toggle between themes](https://github.com/mmistakes/minimal-mistakes/discussions/2033)