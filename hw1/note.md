# 胡立課程心得-[FE210] 從新手到中手：前端工程加強班 week 1

###### tags:`程式筆記` `Lidemy` `前端工程加強班`

## 基本 HTML/CSS 練習：以 Twitch 為例

### homework 碰到的問題/技巧

#### 圓形照片

* `border-radius: 50%;`

#### 背景圖片遮罩

* pseudo-element
  * [CSS-Trick](https://css-tricks.com/almanac/selectors/a/after-and-before/)
  * [How to change background-image opacity in CSS without affecting text](https://coder-coder.com/background-image-opacity/)

```[css]
.bg {
    position: relative;
    height: 100%;
    width: 100%;
    background-image: url(https://lolstatic-a.akamaihd.net/lolkit/1.1.6/resources/images/bg-default.jpg);
    background-attachment: fixed;
}

.bg::before {
    content: "";
    position: absolute;
    top: 0px;
    right: 0px;
    bottom: 0px;
    left: 0px;
    background-color: rgba(0, 0, 0, 0.5);
}
```

#### Collapsing margins

* [W3c](https://www.w3.org/TR/CSS2/box.html#collapsing-margins)
* [CSS 失控的 Margin top](https://wcc723.github.io/css/2016/06/08/css-margin-collapsing/)

### 自我練習

* 請問 CSS 的屬性position有哪幾種值？
  * static
  * fixed
  * relative
  * absolute
* 承上，請問那幾種值有哪些區別？請講出適合應用的地方
  * static: default
  * fixed: 相對於上層元素定位，如果上層是 static 就再往上層找，用 top, bottom, left, right 去定位，不會佔用元素原本的位置，**會髓著頁面滾動**
  * relative: 相對於上層元素定位，如果上層是 static 就再往上層找，用 top, bottom, left, right 去定位，**會佔用元素原本的位置，不會髓著頁面滾動**
  * absolute : 相對於上層元素定位，如果上層是 static 就再往上層找，用 top, bottom, left, right 去定位，**不會佔用元素原本的位置，不會髓著頁面滾動**
  * [codepen](https://codepen.io/mitour/pen/qBrRwKa?editors=1100)
* display的三個值inline, block, inline-block有什麼異同？可以試著舉出幾個例子嗎？
  * inline: 元素會排在同一行，長寬取決於元素內容多大，不可以定義 width, height
  * block: 寬度預設為螢幕寬度，可以定義 width, height
  * inline-block: 元素會排在同一行，可以定義 width, height
* 有哪些 HTML 元素是 inline, 哪些是 block？
  * inline: `<span>`, `<a>`
  * block: `<div>`, `<p>`
* 當我設定一個元素的width為300px，並且padding設成10px之後，這個元素的寬度應該會是多少？
  * 320px
* 這次實作的畫面當頻道名稱字太多的時候，會超出一格的大小或者會直接被卡掉，有沒有辦法讓字太多的時候在尾巴顯示...？例如原本名稱叫做：「1234567」，顯示的時候變成：「12345...」？
  * ~~我忘記了XDD~~
  * `text-overflow: ellipsis;`
  * [codepen](https://codepen.io/mitour/pen/GRWrVjE?editors=1100)
  * [CSS-Trick](https://css-tricks.com/almanac/properties/t/text-overflow/)

### 老師影片講解

* row>col*9
* 更改頭像大小，用 position 會跑版
  * display: flex
* 變成8格置中會跑掉
  * 多加一格沒有內容的col
  * 嘗試用 display: flex 看看
    * [flexboxfroggy](https://flexboxfroggy.com/)
  * 嘗試用 grid 排看看
    * [grid-garden](https://codepip.com/games/grid-garden/)
* box-sizing 不用算數
