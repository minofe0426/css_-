# CSS

## font-size
> 수치와 단위를 지정해 **글자의 크기**를 정의한다. 

|단위|의미|
|:--|:--|
|px|모니터 상의 화소 하나의 크기에 대응하는 절대적인 크기|
|rem|`<html>`태그의 font-size에 대응하는 상대적인 크기|
|em|부모태그(상위태그)의 font-size에 대응하는 상대적인 크기|

```css
span{ font-size: 16px; }
span{ font-size: 2rem; }
span{ font-size: 1.5rem; }
```
   
```css
*h1의 기본: 32px   
*p의 기본 16px  

html{ font-size: 18px; }
h1{ font-size: 2rem; } //18*2 32px html에 폰트 사이즈 기준으로 곱하기
p{ font-size: 1rem; } //18*1 18px

html <p><span></span></p>
p{ font-size: 10px; } //em의 기준이 되는 상위요소
span{ font-size: 2em; } //상위요소의 크기 기준 * 자신의 값으로 10*2 = 20px이 된다.

```

## text-align
> **블록 내에서 텍스트**의 정렬 방식을 정의한다. 미리 정의된 키워드 값을 지정한다.

|속성값|의미|
|:--:|:--|
|left/ right|왼쪽 또는 오른쪽 정렬한다.|
|center|가운데 정렬한다.|
|justify|양끝 정렬한다(마지막 줄 제외)|   
    
## color
>텍스트의 **색상**을 정의한다. 다양한 방법으로 색상을 지정할 수 있다.

|속성값 유형|방법|
|:--:|:--|
|키워드|미리 정의된 색상별 키워드를 사용한다 (ex. red, blue)|
|RGB 색상 코드|# + 여섯자리 16진수 값 형태로 지정한다. (ex. 흰색은 #fff, 검은색은 #000 동일하게 6번 반복되는 색상코드는 3개로 생략가능)|
|RGB 함수|Red, Green, blue의 수준을 각각 정의해 지정한다. (ex. `rgb(100%, 0%,0%)`)|

```css
*적용 시켰을 때 모두 빨강색

span{ color: red; }
span{ color: #ff0000; }
span{ color: rgb(100%, 0%, 0%); }
```

## 블록 레벨 요소 VS 인라인 요소
> 블록 레벨 요소 : 자기가 속한 영역의 너비를 모두 차지하여 블록을 형성한다. (div, p, h1)   
> 인라인 요소 : 자기에게 필요한 만큼의 공간만 차지한다.
(span, a)   
   
### display 속성
> display 속성은 요소를 블록과 인라인 요소 중 어느 쪽으로 처리할 지 정의한다.

```css
/*
블록 레벨 요소인 div 요소를 인라인으로 처리하고 싶다면
*/
div{ display: inline }

/*인라인 요소인 a 요소를 블록 레벨로 처리하고 싶다면*/
a{ display: block}
```

|속성값|의미|
|:--:|:--|
|inline|인라인으로 처리한다.|
|block|블록 레벨로 처리한다.|
|inline-block|인라인으로 배치하되, 블록 레벨 요소의 속성을 추가할 수 있도록 처리한다.|
|none|디스플레이(표시)하지 않는다.|

## 박스 모델
> block요소와 inline요소 모두 **ppading, margin, border속성**을 가질 수 있지만,   
inline은 block과 다르게 **widthd와 height**를 적용할 수 없다.   
widthd와 height를 inline요소에 적용하려면 **display: inline-block**를 넣어주면 된다. 

- 콘텐츠 영역: width, height
- 안쪽 여백: padding
- 바깥쪽 여백: margin
- 테두리: border-width 

## box-sizing
> box-sizing 속성은 요소의 너비(width)와 높이(height)를 계산하는 방법을 지정한다.

|속성값|의미|
|:--|:--|
|content-box|**기본값**, 너비와 높이가 콘텐츠 영역만을 포함한다.|
|border-box|너비와 높이가 안쪽 여백과 테두리까지 포함한다.|
=> 너비와 높이가 같더라도, box-sizing 속성값에 따라 크기가 달라질 수 있다.

## background
> 배경은 콘텐츠의 배경을 정의한다.   
단축 속성으로써 색상, 이미지, 반복 등 다양한 하위 속성을 정의할 수 있다.

|하위 속성|역할|
|:--:|:--|
|background-color|배경 색을 정의한다.|
|background-image|배경 이미지를 정의한다.|
|background-position|배경 이미지의 초기 위치를 정의한다.|
|background-size|배경 이미지의 크기를 정의한다.|
|background-repeat|배경 이미지의 반복 방법을 정의한다.|
```css
<div>
background-image: url(./위치);
background-repeat: no-repeat; //반복금지
background-size: cover; //이미지 비율이 깨지지 않는 선에서 최대로 증가
background-size: contain; //이미지가 찌그러지거나 잘리지 않는 선에서 최대사이즈

background: no repeat url(./위치); //background에 각각 속성을 따로 입력하지 않아도 알아서 지정해서 넣어준다.
</div>
```

## float
> float 속성은 요소가 문서의 일반적인 흐름에서 제외되어 자신을 포함하고 있는 컨테이너의 왼쪽이나 오른쪽에 배치되게 한다.

|속성값|의미|
|:--|:--|
|none|기본값, 원래 상태|
|left|자신을 포함하고 있는 박스의 왼편에 떠 있어야 함|
|right|자신을 포함하고 있는 박스의 오른편에 떠 있어야함|
=> 문서의 흐름에서 제외되지만, 필요한 만큼의 공간의 차지한다.


## clear
> clear 속성은 float 요소 이후에 표시되는 요소가 float을 해체(clear)하여 float 요소의 아래로 내려가게 할 수 있다.

|속성값|의미|
|:--|:--|
|none|기본값, 아래로 이동되지 않음을 나타내는 키워드|
|left|float이 left인 요소의 아래로 내려가겠다.|
|right|float이 right인 요소의 아래로 내려가겠다.|
|both|float이 left 및 right인 요소의 아래로 내려가겠다.|
=> clear: both;를 사용하면 한방에 해결

## position
> position은 문서 상에 요소를 배치하는 방법을 정의한다.
position이 요소의 배치 방법을 결정하면, top, bottom, right, left가 최종 위치를 결정하는 방식이다.

- position: 난 이렇게 배치할거야;
- top: 윗면에서부터 얼만큼 떨어뜨릴거야;
- right: 오른쪽면에서부터 얼만큼 떨어뜨릴거야;
- bottom: 아랫면에서부터 얼만큼 떨어뜨릴거야;
- left: 왼쪽면에서부터 얼만큼 떨어뜨릴거야;   

=> 상하좌우 위치 지정은 필요에 따라 선택적으로 사용

### postion 속성값
> position 속성에는 다음 속성값들을 지정할 수 있다.

|속성값|의미|
|:--|:--|
|static|기본값, 요소를 일반적인 문서 흐름에 따라 배치한다.|
|relative|일반적인 문서 흐름에 따라 배치하되, 상하좌우 위치 값에 따라 오프셋을 적용한다.|
|absolute|일번적인 문서 흐름에서 제거하고, 가장 가까운 position 지정 요소에 대해 상대적으로 오프셋을 적용한다.|
|fixed|일반적인 문서 흐름에서 제거하고, 지정한 위치에 고정된다.|
|sticky|일반적인 문서 흐름에서 제거하고, 스크롤 동작이 존재하는 가장 가까운 요소에 대해 오프셋을 적용한다.|

## flexbox
> flexbox란 박스 내 요소 간의 공간 배분과 정렬 기능을 제공하기 위한 1차원 레이아웃 모델이다.   
flexbox를 1차원 모델이라 부르는 이유는, 레이아웃을 다룰 때 한 번에 하나의 차원(행이나 열)만을 다룬다는 특성 때문이다.
행(row), 열(column)
flexbox에는 '주축(main-axis)'과 '교차축(cross-axis)'이 있다. 

```css
<div class="display: flex;">
  <div class="item">하나</div>
  <div class="item">둘</div>
  <div class="item">셋</div>
</div>
```
 ### flex-direction
 > flex-direction 속성은 flexbox 내 요소를 배치할 때 사용할 주축 및 방향(정방향, 역방향)을 지정한다.

|속성값|의미|
|:--|:--|
|row|기본값, 주축은 행이고 방향은 콘텐츠의 방향과 동일|
|row-reverse|주축은 행이고 방향은 콘텐츠의 방향과 반대|
|column|주축은 열이고 방향은 콘텐츠의 방향과 동일|
|column-reverse|주축은 열이고 방향은 콘텐츠의 방향과 반대|

### flexbox 다루기
> flexbox를 다루기 위해 다음과 같은 속성들을 사용할 수 있다.
- 주축 배치 방법: justify-content
- 교차축 배치 방법: align-item
- 교차축 개별요소 배치 방법: align-self
- 줄 바꿈 여부: flex-wrap
```html
<div class="container">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</div>
```
```css
.container{
  dispaly: flex;
  width: 300px; height: 300px;
  border: 2px solid black;
  justify-content: center; 
  /** 주축 가운데정렬 / flex-start, 앞으로 정렬 / flex-end 끝으로 정렬 /space-around 각각의 여백을 동일하게 / space-between 양쪽 끝에 붙이고 나머지 간격을 동일하게 **/
  align-items: center; //교차축에서의 정렬방법
}

.item{
  width: 60px; height: 60px;
  background-color: teal;
}
```
## 의사클래스
> 의사클래스(가상클래스)는 선택자에 추가하는 키워드로, 요소가 어떤 특정한 상태가 되었을 때 요소를 선택하겠다는 의미이다.
```css
/*
선택자:의사클래스{
  속성명: 속성값;
}
*/
h1:hover{
  color: red;
}
```
=> h1 요소에 마우스 커서가 올라오면(hover) 글자를 빨간색으로 하겠다.

|속성값|의미|
|:--|:--|
|hover|마우스 포인터가 요소에 올라가 있다.|
|active|사용자가 요소를 활성화했다.(예를 들면, 마우스로 누르기와 같은)|
|focus|요소가 포커스를 받고 있다.|
|disabled|비활성 상태의 요소이다.|
|nth-child()|형제 사이에서의 순서에 따라 요소를 선택한다.|

=> 사용 가능한 모든 의사클래스 링크
https://developer.mozilla.org/ko/docs/Web/CSS/Pseudo-classes

## 의사요소
> 의사요소(pseudo-elements)는 선택자에 추가하는 키워드로, 이를 이용하면 선택한 요소의 특정 부분에 대한 스타일을 정의할 수 있다.
```css
/*
선택자::의사요소{
 속성명: 속성값;
}
*/
li::first-letter{
  font-size: 20px;
}
```
=> li 요소의 첫 번째 글자만 크기를 20px로 하겠다(기본값은 16px)


|의사요소|의미|
|:--|:--|
|after|요소의 앞에 의사 요소를 생성 및 추가한다.|
|before|요소의 뒤에 의사 요소를 생성 및 추가한다.|
|first-line|블록 레벨 요소의 첫 번째 선에 스타일을 적용한다.|
|marker|목록 기호의 스타일을 적용한다.|
|placeholder|입력 요소의 플레이스홀더(자리표시자) 스타일을 적용한다.|

=> 의사요소 링크   
https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements

## 상속
> 성속(Inheritance)이란 하위 요소가 상위 요소의 스타일 속성값을 물려받는 것을 의미한다.
>다 되는 건 아니다 : 상위요소로부터 상속이 이루어지는 속성이 있는 반면, 그렇지 않은 속성도 있다.

예)
|상속 된다.| 상속 안 된다.|
|:--|:--|
|color, font-family, font-size, font-weight, text-align, cursor 등|background-color, background-image, background-repeat, border, display 등|

=> 상속 여부 링크   
https://www.w3.org/TR/CSS21/propidx.html

## 공용 키워드
> 모든 CSS 속성에 사용 가능한 키워드가 있다.
때문에 이를 '전역 값'이라 표현하기도 한다.

|키워드|의미|
|:--|:--|
|inherit|상위 요소로부터 해당 속성의 값을 받아 사용한다.|
|initial|(브라우저에 지정되어 있는)해당 속성의 기본값을 요소에 적용한다. 초기값|
|unset|상속 속성에 대해서는 inherit처럼, 상속되지 않는 속성에 대해서는 initial처럼 적용된다.|

=> 속성 테이블
https://www.w3.org/TR/CSS21/propidx.html

## z-index
> z-index 속성은 요소의 **쌓임 순서(stack order)** 를 정의할 수 있다.   
정수 값을 지정하여 쌓임 맥락(stacking context)에서의 레벨을 정의하는 방식으로 적용되며, 위치 지정 요소에 대해 적용할 수 있는 속성이다.   
=> 위치 지정 요소(positioned element)란, position 속성이 정의되어 있는 요소를 말한다.

