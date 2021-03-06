첫번째로 header 분석.

<br>

<img width="1276" alt="header,visual" src="https://user-images.githubusercontent.com/48181483/96807789-663bc900-1452-11eb-8eae-c636f727dcbf.png">

사진에서 검정색 배경을 갖지 않는 컨텐츠들이 header이며, 로고와 네비게이션로 구성되어있다.

<br>

배치는 position을 사용할 것이며, 네비게이션안의 컨텐츠들은 float로 배치할 것이다.

<br>

배치에 position을 사용한 이유는 3가지의 컨텐츠가 접근성상 로고 > gnb > utill로 마크업될 예정이나

<br>

화면상으로는 gnb보다 util이 먼저 보이기 때문이다. tab키를 사용하면 gnb로 먼저 포커스가 갈예정이며

<br>

gnb에는 hover이벤트로 색상을 변경해 사용자에게 구분점을 줄 예정이다.

<br>

```html
...
<body>
    <header>
        <div>
            <h1><a href="#">DECODELAB</a></h1>
            <ul>
                <li><a href="#">DEPARTMENT</a></li>
                <li><a href="#">GALLERY</a></li>
                <li><a href="#">YOUTUBE</a></li>
                <li><a href="#">COMMUNITY</a></li>
                <li><a href="#">LOCATION</a></li>
            </ul>
    
            <ul>
                <li><a href="#">Contact</a></li>
                <li><a href="#">Help</a></li>
                <li><a href="#">Login</a></li>
                <li><a href="#">Join</a></li>
                <li><a href="#">Sitemap</a></li>
            </ul>
        </div>
    </header>
</body>
...
```

hedaer의 마크업을 완료하였다. header 태그안에 3개의 컨텐츠가 존재하며 레이아웃을 잡기위한 div를

하나 생성하였다.

<br>

```css
...
header div.inner{
    width:1180px;
    height:120px;
    margin: 0px auto;
    position: relative;
}

div.inner h1.logo{
    position: absolute;
    bottom:15px;
    left:0px;
}

h1.logo a{
    font:bold 24px/1 "arial";
    color: #444;
}

div.inner ul.gnb{
    position: absolute;
    bottom:0px;
    right:0px;
}

ul.gnb li{
    float:left;
}

ul.gnb li a{
    display: block;
    font: bold 15px/1 "arial";
    color: #555;
    padding: 20px 40px;
    transition: 0.5s;
}

ul.gnb li a:hover{
    background: #555;
    color:#fff;
}



div.inner ul.util{
    position: absolute;
    top:20px;
    right:0px;
}

ul.util li{
    float:left;
}

ul.util li a{
    display: block;
    font: 12px/1 "arial";
    color: #999;
    border-right:1px solid #aaa;
    padding:0px 10px;
}

ul.util li:last-child a{
    border-right:none;
}
...
```

css로 디자인을 입혔다 최대한 class로 작성하였으며 디자인을 위한 html 요소에 선택자를 사용하지 않았다. 좋은지는 모르겠다.

<br>

```html
<header class="header">
```

에 대하여 고찰해보았다, header태그에 class를 준다면 어떠한 이름으로 주어야하며

다양하게 커질 수 있는 프로젝트라고 가정한다면 header라고 클래스명을 짓는게 맞을까?

기업형 사이트이기때문에 class라고 줘도 괜찮다고 보지만, 상품으로 친다면 다양한 환경을 고려해서

클래스명을 지어야할 것 같다.

<br>

header 완성 이미지

<img width="1276" alt="header finish" src="https://user-images.githubusercontent.com/48181483/96825594-782a6580-146c-11eb-9bd4-c169bf097ab9.png">

두번째, visual 영역 분석



visual 영역은 전체 크기를 차지하면서 배경동영상을 세팅하고, 그안에 inner영역을 width고정값을 줘서 자식들을 배치하고

전체 100%를 차지한다고 판단, 안에 컨텐츠들은 패딩으로 레이아웃을 배치하고

컨텐츠들사이에 공백은 margin을 사용하고, 버튼에 사용되는 속성은

text-align 및 hover, text-align을 사용해야하니까, 컨텐츠의 부모는 블록속성이여야겠다. 혁신이라는 소제목은 h2로 가야할까? 소제목과 버튼을 제외한 컨텐츠는 p태그로 판단된다.

<br>

```html
...
    <section class="visual">
        <video src="./img/visual.mp4" autoplay muted loop></video>
        <div class="container">
            <h1>INNOVATION</h1>
            <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. <br>
                Id praesentium molestias similique quaerat magni facere in a? Adipisci, possimus reprehenderit!</p>
            <a href="#">view detail</a>
        </div>
    </section>
...
```

video 태그와 레이아웃용 div를 활용해 마크업을 사용하였다 video태그들의 속성을 활용하였다

```css
...
section.visual{
	width:100%;
	position: relative;
	background:#000;
	overflow:hidden;
	height:calc(100vh - 120px);
	padding-top:250px;
}

section video{
	width:2000px;
	height:1125px;
	position: absolute;
	opacity:0.3;
	/* 가운데정렬 */
	top:50%;
	left:50%;
	margin-top:calc(-1125px / 2);
	margin-left:-1000px;
}

section.visual div.container{
	width:1180px;
	margin:0px auto;
	position: relative;
	/* 여기에 relative가 없으면 인식을못하나?? */
}

div.container h1{
	font: normal 120px/1 "arial";
	color: #fff;
	margin-bottom: 20px;
}

div.container p{
	font: 16px/1.4 "arial";
	color: #888;
	margin-bottom: 60px;
}

div.container a{
	display: block;
	border: 1px solid #bbb;
	font: bold 11px/30px "arial";
	color: #fff;
	text-align: center;
	width:400px;
	height:30px;
	transition:all 0.5s;
	letter-spacing: auto;
}

div.container a:hover{
	background: #555;
	color:#fff;
}
...
```

css작업을 하며 고정값이 필요한부분이 있어서 작성하였고, 문제점도 발생하였다. 이유를 찾아가는중

<br>

![visual](https://user-images.githubusercontent.com/48181483/96946920-a23b6080-151c-11eb-84e9-5c7f5c8a636e.png)

visual 까지 작성하고보니 markup에 수정해야된다고 생각하는게 몇군데가 있었다

```html
...
    <section class="visual">
        <video src="./img/visual.mp4" autoplay muted loop></video>
        <div class="container">
            <h1>INNOVATION</h1>
            <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. <br>
                Id praesentium molestias similique quaerat magni facere in a? Adipisci, possimus reprehenderit!</p>
            <a href="#">view detail</a>
        </div>
    </section>
...
```

첫째 클래스 visual을 가지고 있는 태그는 section으로 해야하는가?

둘째 제목용 INNOVATION이 h1태그가 맞을까?

셋째, 레이아웃용 중앙 가운데 정렬을 위해 container라는 클래스를 사용하였는데 재사용이 가능하겠다.

<br>

검색을 활용하며 적합한 태그를 찾아나갔고, section 태그보다는 figure태그가 적합한게 아닌가 의문을 가졌다

(figure는 이미지 라는 느낌이 강하게 느껴졌다 변경하지 않겠다.)

(이유: 사이트 흐름과 독립된 컨텐츠이며 순서가 중요하지 않음)

그리고 video 태그에 자동재생에 대해 필수속성이 몇가지 있다는것을 알게되었다

<br>

autoplay,muted, playsinline속성이다. 크롬정책상 autoplay속성에 muted가 존재하여야 하며, 아이폰10버전 이후는 playsinline속성이 필요하다고 한다. playsinline속성 추가.

<br>

section안에 h1이 있는것이 적합한가? 라는것에 대한 의문이 생겼다. section안에 h1~h6태그들을 필수로 사용하라고 하지만

주관적인 생각으로 html문서에서 h1태그는 로고급으로 한개만 있어야되는 '가장중요한'것이 아닐까 생각해보았다

그래서 h2태그로 변경하였다.

<br>

header section에 inner라는 부분을 container로 변경하기로 하였다. 이 프로젝트내에서 레이아웃 배치용은 container라고 이름지을것이며 공통으로 사용할 것 이다. 다만 header부분의 container는 다른부분과는 조금 달라서 직접적인 코드의 줄임은 발생하지 않았다.

<br>

```html
...
<!-- 변경된 코드  -->
 <header>
        <div class="container">
		...
 </header>
 <section class="visual">
     <video src="./img/visual.mp4" autoplay muted loop playsinline></video>
     <div class="container">
         <h2>INNOVATION</h2>
         <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. <br>
             Id praesentium molestias similique quaerat magni facere in a?                      Adipisci,possimusreprehenderit</p>
         <a href="#">view detail</a>
     </div>
     </section>
...
```

<br>

세번째 뉴스영역 분석

뉴스는 크게 new section 자식요소로 container, 다시 자식으로 h2태그와 ul태그를 갖고 ul에는 같은 형식으로 h3,p,div(img)를 4개

갖고있다 초기 마크업작업은



```html
...
<section class="news">
    <div class="container">
        <h2>RECENT NEWS</h2>
        <ul>
            <li>
                <h3>Lorem ipsum dolor sit.</h3>
                <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolore, incidunt.</p>
                <div></div>
            </li>
            <li>
                <h3>Lorem ipsum dolor sit.</h3>
                <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolore, incidunt.</p>
                <div></div>
            </li>
            <li>
                <h3>Lorem ipsum dolor sit.</h3>
                <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolore, incidunt.</p>
                <div></div>
            </li>
            <li>
                <h3>Lorem ipsum dolor sit.</h3>
                <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolore, incidunt.</p>
                <div></div>
            </li>
        </ul>
    </div>
</section>
...
```

구성하였다 css스타일링을 하되 구조에 변화를 주지않도록 노력해야겠다

<br>

css스타일링도중 속상했던 순간이있다

```css
margin:0px;
margin:none;
```

두개의 차이를 몰랐기 때문이다. margin none이라는게 존재하나? 속성에대한 값이 정확하지 않아 레이아웃 구성이 안되서 속상했다.

<br>

최종적으로 구성한 news section

![screenshot-127 0 0 1_5500-2020 10 24-14_25_07](https://user-images.githubusercontent.com/48181483/97068680-ca9e8a00-1604-11eb-9a3b-026f6551e497.png)

markup을 조금 바꿨다 배치상으론 div > h3 > p태그순이지만 h3>p>div순으로 markup하였다 div는 단순히 그림이라고 판단했기 때문이다

---

brand section 분석

가장 최상단에 section 자식으로 contatiner를 가지며 h2로 섹션의 제목존재하며

float 배치를 하는데, 높이와 너비를 고정값을 사용해야 할 것 같고

좌측부터 우측으로 위에서부터 아래로 div1~div4를 사용

고정형 레이아웃의 너비값인 1180의 3분할시점인 div1은 380 div2,3역시 380

div의너비는 780

div1의 높이는 620 px이며, div2~4는 300px

```html
<!--초기 마크업-->
<section class="brand">
    <div class="container">
        <h2>BRAND IDENTITY</h2>

        <div></div>
        <div></div>
        <div></div>
        <div></div>
    </div>
</section>
```

정말 필요하다고 생각하는것만 만든후, 변경예정



![brand](https://user-images.githubusercontent.com/48181483/97123601-f25e3100-176f-11eb-9ce5-97b4c46b420e.png)

완성본

---



banner section 분석



![banner](https://user-images.githubusercontent.com/48181483/97241220-cad09c80-1833-11eb-8343-b93e859b9732.png)



컨텐츠자는 화면에 꽉차게  배경과 글씨, 마우스 스크롤링에 따라 화면이 움직이는 듯한 모션을 어떻게 구성하는가가 관건이라고 생각한다.



```html
...
<section class="banner">
    <div class="container">
        <h2 class="bannerTilte">Lorem ipsum dolor sit amet consectetur.</h2>
        <p class="bannerContent">Lorem ipsum dolor sit amet consectetur
            adipisicing elit. Soluta, temporibus saepe facilis omnis ad totam est
            a odio vero eum.</p>
    </div>
</section>
...
```

```css
.banner{
	width:100%;
	padding:150px 0px;
	background: url(../img/banner.jpg) no-repeat center/cover fixed;
}

.banner .bannerTilte{
	font: bold 30px/1 "arial";
    color: #fff;
    text-align: center;
    margin-bottom: 30px;
}

.banner .container .bannerContent{
	font: 16px/1.3 "arial";
    color: #bbb;
    text-align: center;
}
```



banner 섹션에서는 background를 섹션에 속성으로 주고 fixed를 값을 주면되는  쉬운 섹션이였다.

---

comments 섹션

마크업 컨텐츠들의 중요성이나 레이아웃으로 봤을때, 순서대로 배치하면 크게 문제 없는듯 하다.



```html
...
<section class="comments">
    <div class="container">
        <h2>RECENT COMMENTS</h2>
        <ul>
            <li>
                <a href="#">Lorem ipsum dolor sit amet consectetur adipisicing elit.</a>
                <span>2020.10.16</span>
            </li>
            <li>
                <a href="#">Lorem ipsum dolor sit amet consectetur adipisicing elit.</a>
                <span>2020.10.16</span>
            </li>
            <li>
                <a href="#">Lorem ipsum dolor sit amet consectetur adipisicing elit.</a>
                <span>2020.10.16</span>
            </li>
        </ul>
    </div>
</section>
...
```

<br>

```css
...
.comments{
	width: 100%;
    padding: 150px 0px;
    background: #ddd;
}

.comments .container h2{
	font: bold 20px/1 "arial";
    color: #555;
    text-align: center;
	margin-bottom: 30px;
}

.comments .container li{
	border: 1px solid #111;
    margin-bottom: 20px;
	padding: 20px;
}

.comments .container li::after {
    content: "";
    display: block;
    clear: both;
}

.comments .container li:hover{
	background: #444;
}

.comments .container li a{
	float: left;
	color: #555;
}

.comments li span{
	float: right;
    color: #888;
}

.comments .container li:hover a,
.comments li:hover span{
	color:#fff;
}
...
```

<br>

![Comments section](https://user-images.githubusercontent.com/48181483/97373641-c373c680-18f9-11eb-8fce-141100975a4e.png)

최종제작본

li 자식요소로 a와 span을 사용하였는데, 이를 float 배치하다보니 높이를 잃어버리는 현상이 발생한 것 외에는 예상대로 해결되었다.

---

footer

![footer](https://user-images.githubusercontent.com/48181483/98188814-13d0d100-1f57-11eb-8a29-717dd58744a6.png)