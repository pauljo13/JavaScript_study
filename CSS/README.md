# CSS
## CSS - 1
### 01. CSS의 기본
#### 1-1. 웹 문서에 디자인 입히기
##### CSS(스타일) 필요성?
웹 문서에서 스타일style이란 HTML 문서에서 자주 사용하는 글꼴이나 색상, 정렬, 각 요소의 배치 방법과 같이 문서의 겉모습을 결정짓는 것을 가리킨다. HTML 말고 CSS을 이용해 스타일을 바꾼다. 그러는 이유는?

- 웹 문서의 내용과 상관없이 디자인만 바꿀 수 있다.  
    HTML로 웹 문서 내용을 CSS로 웹 문서의 디자인을 만들면 내용을 수정하거나 디자인을 수정할때 서로에게 영향을 주지 않고 수정하는 것이 가능해진다.  
- 다양한 기기에 맞게 탄력적으로 바뀌는 문서를 만들 수 있다.  
    기본의 HTML은 PC 웹 브라우저 화면을 기반으로 한다. 하지만 현대에는 스마트폰, 태블릿 등과 같은 여러 기기가 존재한다. CSS을 이용하면 굳이 HTML을 수정하지 않고 해당 기기에 맞는 CSS만 바꾸면 여러 기기에서 볼 수 있게 된다.  
    - **반응형 웹 디자인** : 사용자가 PC로 접속하든, 모바일로 접속하든 웹 브라우저의 크기에 따라 화면 레이아웃을 자동으로 바꿔 주는 방법이다.
  

#### 1-2. 스타일과 스타일 시트
```CSS
선택자 { 속성1: 속성값1; 속성2: 속성값2; }

p {
    text-align: center;
    color: blue;
}
```
CSS 소스에서 한 줄이 하나의 스타일에 해당하고, 줄마다 형태가 비슷한다.
- 선택자 : 스타일을 적용할 태그
- 중괄호{ } : 스타일 정보
- 스타일 규칙 : 속성과 값이 하나의 쌍
- 세미콜론(;) : 스타일 구분 
    
**스타일 규칙을 작성하는 방법**  
스타일 규칙은 세미콜론(;)으로 구분하여 중괄호({})안에 나열한다. 이때 사용할 스타일 속성이 여러 개일 경우 한 줄에 속성을 하나만 적는 것이 이해하기도 편하고 오른쪽에 주석을 붙여 관리하기도 좋다. 하지만 CSS 가 길어지지 않도록 중괄호({})사이에 스타일 규칙을 한 줄로 표기하기도 한다. 
```css
/*여러 줄 표기 -> 가독성과 관리의 편리*/
p {
    text-align: center;
    color: blue;
}

/*한 줄 표기 -> 용략이 적어진다.*/
p { text-align: center; color: blue;}
```
  
**스타일 주석 표기**
(/* */)을 이용 CSS에서 주석을 처리할 수 있다.  
  
##### 스타일 시트
웹 문서 안에서는 스타일 규칙을 여러 개 사용한다. 
- 스타일 시트
    - 브라우저 기본 스타일
    - 사용자 스타일
        - 인라인 스타일
        - 내부 스타일 시트
        - 외부 스타일 시트
  
**브라우저 기본 스타일**
- CSS를 사용하지 않은 웹 문서라 하더라도 웹 브라우저에 표시할 때는 기본 스타일을 사용한다.
  
**인라인 스타일**
- 스타일 시트를 사용하지 않고 직접 표시하는 방법이다.
- style="속성: 속성값;" 형태로 스타일을 직접 넣는다.
  
**내부 스타일 시트**
- 웹 문서 안에서 사용할 스타일을 같은 문서 안에 정리한 것으로 &lt;head&gt; 태그 안에 &lt;style&gt;~lt;/style&gt; 사이에 스타일 정보를 입력해서 넣는 방식이다.
  
**외부 스타일 시트**
```html
<link rel="stylesheet" href="외부 스타일 시트 파일 경로">
```
- html 문서와 스타일 정보가 있는 CSS 문서를 따로따로 하는 방법으로 위와 같은 태그를 이용해서 스타일을 적용한다.
  
  
#### 1-3. CSS 기본 선택자
##### 전체 요소에 스타일을 적용하는 전체 선택자
**전체 선택자(Universal selector)**는 말 그대로 스타일을 문서의 모든 요소에 적용할 때 사용한다. 주로 모든 하위 요소에 스타일을 한꺼번에 적용할 때 사용한다. 전체 선택자로는 다음과 같이 *(별표)를 사용한다.
```CSS
* { 속성: 값; ...... }
```
- 마진(Margin) : 요소의 바깥쪽에 위치한 공간으로, 주변 요소와 간격을 생성, 요소 사이의 거리만 조정
- 패딩(Padding) : 요소의 내부에 위치한 공간으로, 요소의 경계(Border)와 내용(Content) 사이의 간격을 생성, 요소의 실제 크기를 변경 된다.
  
##### 특정요소에 스타일을 적용하는 타입 선택자
**타입 선택자(Type selector)** : 특정 태그를 사용한 모든 요소에 스타일을 적용한다. 즉, 지정한 해당 태그의 모든 요소에 적용된다.
```css
태그명 { 스타일 규칙 }
```
  
##### 특정 부분에 스타일 적용하는 클래스 선택자
**클래스 선택자(Class selector)** : 같은 태그 중에서 일부를 다른 스타일로 적용할 때 사용한다. 클래스 선택자는 클래스 명을 이용해 다른 선택자와 구별한다. 이때 클래스 이름 앞에 마침표(.)를 반드시 붙여야 한다.
```css
.클래스명 { 스타일 규칙 }
```
- 태그 안에 class="클래스명" 지정한다.
- 클래스 선택자를 사용 특정 클래스에 스타일을 적용한다.
  
##### 특정 부분에 스타일을 한 번만 적용할 수 있는 id 선택자
**id 선택자(id selector)** : 클래스 선택자와 마찬가지로 웹 문서의 특정 부분을 선택해서 스타일을 지정할 때 사용한다. 마침표(.) 대신 # 기호를 사용한다.
```css
#아이디명 { 스타일 규칙 }
```
- 클래스 선택자는 여러 번 적용 가능 / id 선택자는 문서에서 한 번만 적용가능
- 주문 문서의 레이아웃과 스타일 지정에 주로 사용
  
##### 같은 스타일 규칙을 사용하는 요소들을 묶어주는 그룹 선택자
여러 선택자에서 같은 스타일 규칙을 사용하는 경우 쉼표(,)로 구분해 여러 선택자를 나열한 후 스타일 규칙을 한 번만 정의해 사용할 수 있다.
```css
선택자1, 선택자2 { 스타일 규칙 }

h1 { text-align: center; }
p { text-align: center; }


h1, p { 
    text-align: center; 
}
```
  
  
#### 1-4. 캐스케이딩 스타일 시트 알아보기
##### 캐스케이딩
**캐스케이딩 Cascading** : CSS의 C로 스타일 시트에서 우선순위가 위에서 아래 쯕 계단식으로 적용된다는 의미로 사용한다. 즉, CSS는 우선순위가 있는 스타일 시트 이다.  
CSS에서 웹 요소에 둘 이상의 스타일을 적용할 때 우선순위에 따라 적용할 스타일을 결정한다.
- 스타일이 충돌하지 않는 방법
    - **스타일 우선순위** : 스타일 우선순위: 스타일 규칙의 중요도와 적용 범위에 따라 우선순위가 결정되고, 그 우선순위에 따라 위에서 아래로 스타일을 적용한다.
    - **스타일 상속** : 태그의 포함 관계에 따라 부모 요소의 스타일을 자식 요소로, 위에서 아래로 전달한다.
  
##### 스타일 우선순위
**스타일 우선순위** : 캐스케이딩에서 가장 중요하다. 이때 우선순위란 러떤 스타일을 먼저 적용할 것인지 결정하는 규칙을 말한다.
  
- 중요도 순위  
    1. 사용자 스타일
    2. 제작자 스타일
    3. 브라우저 기본 스타일
- 적용 범위
    1. !important : 어떤 스타일보다 우선 적용하는 스타일
    2. 인라인 스타일 : 태그 안에 style 속성을 사용해 해당 태그만 스타일을 적용
    3. id 스타일 : 지정한 부분에만 적용되는 스타일이지만 한 문서에 한 문서에 한 번만 적용할 수 있다. (선택자 이름 앞에 # 기호를 사용)
    4. 클래스 스타일 : 웹 문서에서 지정한 부분에만 적용되는 스타일로 한 문서에 여러 번 적용할 수 있습니다.(선택자 이름 앞에 마침표(.) 기호를 사용)
    5. 타입 스타일 : 웹 문서에 사용한 특정 태그에 스타일을 똑같이 적용한다.
  
##### 스타일 상속
웹 문서에서 사용하는 여러 태그는 서로 포함 관계가 있다. 이때 포함하는 태그를 부모 요소, 포함된 태그를 자식 요소라 한다. 스타일 시트에서는 자식 요소에서 별도로 스타일을 지정하지 않으면 부모 요소의 스타일 속성들이 자식 요소로 전달 된다.  
- 상속 가능한 속성: 일부 CSS 속성은 상속이 가능하며, 이는 주로 텍스트 관련 속성(예: color, font-family, font-size)에 해당합니다. 부모 요소에 적용된 이러한 속성들은 자식 요소에 자동으로 적용될 수 있습니다.
- 상속 불가능한 속성: 상속이 불가능한 속성도 있습니다. 예를 들어, 배경 관련 속성(background-color, background-image 등)이나 박스 모델 속성(margin, padding, border 등)은 자식 요소로 자동으로 상속되지 않습니다.
- 강제 상속: CSS에서는 inherit 키워드를 사용하여 상속이 불가능한 속성도 명시적으로 상속받도록 할 수 있습니다. 예를 들어, margin: inherit;을 자식 요소에 적용하면, 해당 요소는 부모의 margin 속성 값을 상속받습니다.
  
  

### 02. 텍스트를 표현하는 다양한 스타일
#### 2-1. 글꼴 관련 스타일
텍스트 스타일은 사용하는 글짜의 모양새를 지정하는 글꼴 스타일과 웹 문서에 표시도는 텍스트를 지정하는 문단 스타일이 있다. 스타일의 종류를 굳이 나눌 필요는 없지만 font로 시작하는 속성은 글꼴과 관련 있다.
  
##### 글꼴을 지정하는 font-family 속성
```css
태그 {font-family: <글꼴 이름> | [<글꼴 이름>, <글꼴 이름>]}

/* 예시 */
body { font-family: "맑은 고딕", 돋움, 굴림}
```
- 웹 문서의 글꼴을 설정하는 속성
- 지정한 글꼴이 없는 경우 의도한 글꼴이 아닌 다른 글꼴로 표시됨
- 이에 두 세개의 다른 글꼴을 설정해 대비한다.
- 2개 이상의 글꼴을 지정은 쉼표(,)로 구분한다.
- body 태그는 웹문서 전체에 적용됨
  
##### 글짜 크기를 지정하는 font-size 속성
```css
태그 {font-size: <절대 크기> | <상대 크기> | <크기> | <백분율>}

/*
1. 브라우저에서 지정한 글자 크기
2. 부모 요소의 글자 크기를 기준으로 상대적인 글자 크기를 지정
3. 브라우저와 상관없이 글자 크기를 직접 지정
4. 부모 요소의 글자 크기를 기준으로 백분율(%)로 표시
*/
```
- 글짜 크기를 조절하는 속성
- 단위는 px(픽셀), pt(포인트), 백분율(%) 등으로 지정할 수 있다. 
    
- **키워드를 사용하여 글자 크기 지정**
    ```css
    xx-small < x-small < medium < large < x-large < xx-large
    ```
    글자 크기로 사용하도록 미리 약속해 놓은 키워드 중에서 하나를 사용할 수 있다.
- **단위를 사용하여 글자 크기 지정**
    - em : 부모 요소에서 지정한 글꼴의 대문자 M의 너비를 기준(1em)으로 한 후 비율값을 지정
    - rem : 문서 시작 부분(root)에서 지정한 크기를 기준(1rem)으로 한 후 비율값을 지정
    - ex : 해당 글꼴의 소문자 x의 높이를 기준(1ex)으로 한 후 비율값을 지정
    - px : 모니터의 1픽셀을 기준(1px)으로 한 후 비율값을 지정
    - pt : 포인트라고 하며, 일반 문서에서 많이 사용
- **백분율을 사용하여 글자 크기 지정**  
    백분율은 부모요소의 글자 크기가 font-size: 16px처럼 단위로 표현  
  
##### 이탤릭체로 글자를 표시하는 font-style 속성
```css
{font-style: normal(1) | italic(2) | obliqe(3)}

/*
1. 기본값으로 일반적인 형태로 표시
2. 이탤릭체로 표시
3. 이탤릭체로 표시
*/
```
  
##### 글자 굵기를 지정하는 font-weight 속성
```css
font-weight: normal(1) | bold(2) | bolder(3) | lighter(4) | 100(5) | 200 | ... | 800 | 900

/*
1. 기본값, 보통 굵기
2. 굵게
3. 원래보다 더 굵게
4. 원래보다 더 가늘게
5. 100 ~ 900 사이의 굵기를 표현하며 100은 가장 가늘게, 900은 가장 굵게 
*/
```
  
  
#### 2-2. 웹 폰트 사용
font-family 속성으로 글꼴을 지정할 때 글꼴이 사용자 시스템에 없을 경우를 대비해서 글꼴을 2~3개 지정한다. 하만 사용자 시스템에 없는 글꼴도 사용할 수 있다.
##### 웹 폰트
- 사용자 시스템에 없는 글꼴 경우, 그대로 보여주고 싶다면???
- Web font로 모든 사용자의 브라우저에서 똑같은 글꼴로 표현할 수 있다.
- 글꼴 정보를 함꼐 저장 즉, 폰트 파일을 서버에 함께 업로드
  
##### 웹 폰트 업로드하고 사용하기
- 인터넷 사이트에서 제공해 주는 것을 사용하거나 자신이 가지고 있는 TTF을 직접 업로드
- TrueType(확정자 : *.ttf)
```css
@font-face {
    font-family: <글꼴 이름>;
    src: <글꼴 이름>[<글꼴 이름>, <글꼴 이름>, ...];
}
```
  

#### 2-3. 텍스트 관련 스타일
##### 글자색을 지정하는 color 속성
```css
{color : <색상>}
```
color 속성 : 
- 웹 문서에서 문단이나 제목 등의 텍스트에서 글자색을 바꿀수 있다.
- 속성값 : 16진수, rgb(또는 rgba), hsl(또는 hsla), 색상 이름 
    - 16진수 : '#'기호 다음에 6자리의 0~f까지 숫자로 크기를 나타냄, 포토샵과 같은 방식
        - 두 자리씩 묶어 #RR/GG/BB 형태
        - RR : 빨간색 / GG : 초록색 / BB : 파랑색
        - 00(색없음) ~ ff(색완전히 있음)
        - #000000(검은색) ~ #ffffff(힌색)
    - hsl & hsla : h(hue 색상), s(saturation 채도), l(lightness 명도), a(alpha 불투명도)
        - hue : 원형에 0도-360도(빨간색) / 120도(초록색) / 240(파란색)
        - saturation : 0 ~ 100 % 로 표시
        - lightness : 0 ~ 100 % 로 표시
        - hsl(0, 100%, 50%)(빨간) 표시 
    - 색상 영문 : 색상을 영문으로 색상 이름을 이용해 작성
    - rgb & rgba : Red, Green, Blue
        - 0(색없음) ~ 255(색 가득 있음)
        - rgb(0,0,255) 표시
        - a(Alpha) 불투명도의 값으로 0 ~ 1 사이값을 갖는다.
  
##### 텍스트를 정렬하는 text-align 속성
text-align 속성 : 문단의 텍스트 정렬 방법을 지정한다.
```css
{text-align: start | end | left | right | center | justify | match-parent}
```
- start : 현재 텍스트 줄의 시작 위치에 맞추어 문단을 정렬
- end : 현재 텍스트 줄의 위치에 맞추어 문단을 정렬
- left : 왼쪽에 맞추어 문단을 정렬
- right : 오른쪽에 맞추어 문단을 정렬
- center : 가운데에 맞추어 문단을 정렬
- justify : 양쪽에 맞추어 문단을 정렬
- match-parent : 부모 요소를 따라 문단을 정렬
  
##### 줄 간격을 조절하는 line-height 속성
lien-height : 줄 간격을 원하는 만큼 조절할 수 있다.
- 속성값 : px, 배율, 퍼센트(%)
  
##### 텍스트의 줄을 표시하거나 없애 주는 text-decoration 속성
text-deciration : 텍스트에 밑줄을 긋거나 취소선을 표시합니다.
- none : 텍스트에 줄을 표시하지 않음
- underline : 밑줄을 표시
- overline : 윗줄 표시
- line-through : 취소선 표시
  
##### 텍스트에 그립자 효과를 추가하는 text-shadow 속성
```css
{text-shadow: none | <가로 거리> <세로 거리> <번짐 정도> <색상>}
```
text-shadow : 텍스트에 그림자 효과를 줄 수 있다.
- 가로 거리 : 텍스트부터 그림자까지의 가로 거리로 필수 속성, 양숫값은 글자의 오른쪽, 음숫값은 글자의 왼쪽에 그림자를 만듬
- 세로 거리 : 텍스트부터 그림자까지의 세로 거리로 필수 속성, 양숫값은 글자의 아래쪽, 음숫값은 글자의 위쪽에 그림자를 만듬
- 번짐 정도 : 그림자가 번지는 정도, 양숫값을 사용하면 그림자가 모든 방향으로 퍼져 나가므로 그림자가 크게 표시
- 색상 : 그림자 색상을 지정, 한 가지만 지정할 수도 있고 공백으로 구분해 여러 색상을 지정, 기본값은 현재 글자색
  
##### 텍스트의 대소 문자를 변환하는 text-transform 속성
text-transform : 영문자를 표기할 떄 텍스트의 대소 문자를 원하는 대로 바꿀 수 있다.
- capitalize : 첫 번째 글자를 대문자로 변환
- uppercase : 모든 글자를 대문자로 변환
- lowercase : 모든 글자를 소문자로 변환
- full-width : 가능한 한 모든 문자를 전각 문자로 변환
  
##### 글자 간격을 조절하는 letter-spacing, word-spacing 속성
letter-spacing : 글자와 글자 사이의 간격을 조절
word-spacing : 단어와 단어 사이 간격을 조절
  
#### 2-4. 목록 스타일
웹 사이트에서 자주 등장하는 메뉴 항목은 대부분 목록과 링크를 결합하여 만든다. 여기에 CSS를 적용하면 휠씬 멋진 사이트 메뉴가 된다.
##### 불릿 모양과 번호 스타일을 지정하는 list-style-type 속성
list-style-type : 불릿의 모양이나 번호 스타일을 지정할 수 있다.
- disc : 채운 원 모양
- circie : 빈 원 모양
- square : 채운 사각형 모양
- decimal : 1부터 시작하는 10진수
- decimal-leading-zero : 앞에 0이 붙는 10진수
- lower-roman : 로마 숫자 소문자
- upper-roman : 로마 숫자 대문자
- lower-alpha or lower-latin : 알파벳 소문자
- upper-alpha or upper-latin : 알파벳 대문자
- none : 불릿이나 숫자를 없앤다.
  
##### 불릿 대신 이미지를 사용하는 list-style-image 속성
```css
태그 {list-style-image: <url(이미지 파일 경로)> | none}
```
list-style-image : 불릿을 원하는 이미지로 바꿀 수 있다. 
  
##### 목록을 들여 쓰는 list-style-position 속성
```css
{list-style-position: inside | outside;}
```
list-style-position : 불릿이나 번호의 위치를 들여 쓸 수 있다.
- inside : 불릿이나 번호를 기본 위치보다 안으로 들여 쓴다.
- outside : 기본값
  
##### 목록 속성을 한꺼번에 표사허눈 list-styl 속성
list-style :  list-style-type, list-style-image, list-style-position 속성을 한꺼번에 표시할 수 있다.
```css
/* 불릿 제거 */
ul {list-style-type: none;}
ul {list-style: none;}

/* 소문자 목록 */
ul {
    list-style-type: lower-alpha;
    list-style-position: inside;
}
ul {
    list-style: lower-alpha inside;
}
```
  

#### 2-5. 표 스타일
CSS를 이용하면 표의 크기뿐만 아니라 테두리, 셀의 테두리, 여러 가지 여백 등의 표 스타일을 지정할 수 있다.
##### 표 제목의 위치를 정해 주는 caption-side 속성
```css
{caption-side: top | bottom}
```
caption-side : 표의 위치를 아래쪽으로 옮길 수 있다.
- top : 캡션을 표 윗부분에 표시
- bottom : 캡션을 표 아랫부분에 표시
  
##### 표에 테두리를 그려 주는 border 속성
border : 표 테두리는 표 바깥 테두리와 셀 테두리를 각각 지정한다. 
  
##### 셀 사이의 여백을 지정하는 border-spacing 속성
```css
{border-spacing: 수평거리 수직거리}
```
border-spacing : 셀과 셀 사이의 여백을 조절할 수 있다.
- 수평 거리의 값과 수직 거리의 값을 공백으로 구별해서 나타내는데 두 값이 같다면 1개만 지정할 수 있다.
  
##### 표와 셀 테두리를 합쳐 주는 border-collapse 속성
border-collapse : 두 줄로 그냥 둘 것인지 아니면 합쳐서 하나로 표시할 것인지 결정한다.
- collapse : 표와 셀의 테두리를 합쳐 하나로 표시
- separate : 표와 셀의 테두리를 따로 표시 (기본값)
  
  
  
### 03. 레이아웃을 구성하는 CSS 박스 모델
#### 3-1. CSS와 박스 모델
**CSS 박스모델이란?** 웹 문서의 내용을 박스 형태로 정의하는 방법이다. 이 박스 모델이 모여 웹 문서를 이룬다. 박스 모델에는 마진과 패딩, 테두리 등 박스가 여러 겹 들어 있다.
##### 블록레벨 요소와 인라인 레벨 요소
**블록 레벨block-level 요소** : 태그를 사용해 요소를 삽입했을 때 혼자 한 줄을 차지하는 것을 말한다. h1, div, p 태그
**인라인 레벨inline-level 요소** : 한 줄을 차지하지 않는다. 콘텐츠만큼만 영역을 차지하고 나머지 공간에는 다른 요소가 올 수 있다. span, img, strong 태그
  
##### 박스 모델의 기본 구성
**박스 모델 box model 요소** : 스타일 시트에서 이렇게 박스 형태인 요소로 존재한다. 
- 콘텐츠 영역, 패딩, 테두리, 마진등의 요소로 구성
- 콘텐츠 영역 &lt; 패딩 &lt; 테두리 &lt; 마진

##### 콘텐츠 영역의 크기를 지정하는 width, height 속성
박스 모델에서 콘텐츠 영역의 크기를 지정할 때 너비 width, 높이는 height 속성을 사용한다.
- 속성값
    - 크기 : 너비나 높이의 값을 px, em 단위로 저정
    - 백분율 : 박스 모델을 포함하는 부모 요소를 기준으로 너빗값이나 높잇값을 백분율(%)로 지정
    - auto : 박스 모델의 너빗값과 높잇값이 콘텐츠 양에 따라 자동으로 결정(기본값)

##### 박스 모델의 크기를 계산하는 box-sizing 속성
width 속성과 height 속성은 박스 모델에서 콘텐츠 주변의 여백이나 테두리를 뺸 콘텐츠 영역의 크기를 가리킨다. 
- box-sizing 속성 : 박스 모델의 너비와 높이를 어떻게 결정할 것인지 속성값에 따라 선택
    - border-box : 테두리까지 포함해서 너빗값을 지정
    - content-box : 콘텐츠 영역만 너빗값을 지정 (기본값)
  
##### 박스 모델에 그림자 효과를 주는 box-shadow 속성
```css
{box-shadow: 수평거리 | 수직거리 | 흐림 정도 | 번짐 정도 | 색상 | inset}
```
- box-shadow 속성값 : 그림자 효과를 줄 수 있다.
    - 수평거리 : 그림자가 가로로 얼마나 떨어져 있는지 나타낸다. 양숫값은 요소의 오른쪽에, 음숫값은 요소의 왼쪽에 그림자를 만듬 (필수 속성)
    - 수직거리 : 그림자가 세로로 얼마나 떨어져 있는지 나타낸다. 양숫값은 요소의 아래쪽에, 음숫값은 요소의 위쪽에 그림자를 만듬 (필수 속성)
    - 흐림 정도 : 이 값을 생략하면 0을 기본값으로 하여 진한 그림자를 표시, 이 값이 커질수록 부드러운 그림자를 표시하며 음숫값은 사용할 수 없다.
    - 번짐 정도 : 양숫값을 사용하면 모든 방향으로 그림자가 퍼져서 박스보다 그림자 크게 표시, 반대로 음숫값은 모든 방향으로 그림자가 축소되어 보인다. (기본값 0)
    - 색상 : 한 가지만 지정할 수도 있고, 공백으로 구분해서 여러 개의 색상을 지정할 수도 있다. 기본값은 현재 검은색
    - inset : 이 키워드를 함께 표시하면 안쪽 그림자로 그립니다.
  
  
#### 3-2. 테두리 스타일 지정하기
##### 박스 모델의 방향 살펴보기
박스 모델은 상하좌우 4개의 방향이 있어서 테두리나 마진, 패딩 등을 지정할 때 한꺼번에 똑같이 지정하거나, 모두 다르게 지정할 수 있다.
- 윗부분 ***top***, 오른쪽 ***right***, 아랫부분 ***bottom***, 왼쪽 ***left***, 시계 방향으로 순서이다.
  
##### 테두리 스타일을 지정하는 border-style 속성
border-style : 테두리 스타일을 지정한다. (기본값 none)
- 속성값
    - none : 기본값, 테두리 없음
    - hidden : 테두리를 감춘다. border-collapse: collapse일 경우 다른 테두리도 표시
    - solid : 실선 테두리
    - dotted : 점선 테두리
    - dashed : 짧은 직선 테두리
    - double : 이중선의 테두리, 두 선 사이간격 border-width 값으로 조정
    - groove : 창에 조간한 것처럼 표시, 홈이 파인 듯한 입체 느낌
    - ridge : 창에서 튀어나온 것처럼 표시
    - inset : 표 border-collapse : seperate일 경우 전체 박스 테두리가 창에 박혀 있는 것처럼 표시, border-collapse : collapse일 경우 groove와 동일하게 표시
    - outset : 표에 border-collapse : seperate일 경우 전체 박스 체두리가 창에서 튀어나온 것처럼 표시, border-collapse : collapse인 경우 ridge와 동일하게 표시

##### 테두리 두꼐를 지정하는 border-width 속성
```css
{ border-width: 크기 | thin | medium | think }
```
border-width : 테두리의 두께를 지정할 때 사용한다.
- top, right, bottom, left 순서대로 각각 지정할 수 있다.
- 2 개만 적으면 위-아래, 오른쪽-왼쪽 동일하게 적용 된다.
- 3 개 작성시 위,아래,오른쪽은 적용되고 왼쪽은 오른쪽과 동일하게 적용된다.
  
##### 테두리 색상을 지정하는 border-color 속성
border-color : 박스 모델의 테두리 색상을 지정한다.
- border-top-color : 테두리 위의 색상을 지정
- border-right-color : 테두리 오른쪽 색상 지정
- border-bottom-color : 테두리 아래쪽 색상 지정
- border-left-color : 테두리 왼쪽 색상 지정
width 처럼 지정하지 않은 방향은 자동으로 적용되지 않는다.
  
##### 테두리 스타일 묶어 지정하는 border 속성
border : 테두리 스타일, 두께 색상을 한번에 지정할 수 있다.
- 방향 지정 : border-top|right|bottom|left

##### 둥근 테두리를 만드는 border-radius 속성
```css
{border-radius: 크기 | 백분율}
```
border-radius : 박스 테두리를 둥글게 만드는 속성
- 속성값
    - 크기 : 반지름 크기 px, em
    - 백분율 : 현재 요소의 크기를 기준으로 비율(%) 

##### 꼭짓점마다 따로 둥글게 처리하기
박스 모델에서 꼭짓점 4개를 모두 다르게 지정한다.
- top-left
- top-right
- bottom-left
- bottom-right

#### 3-3. 여백을 조절하는 속성
##### 요소 주변의 여백을 설정하는 margin 속성
```css
{margin: 크기 | 백분율 | auto}
```
마진margin : 요소 주변의 여백을 의미한다.
- 방향 : margin-top | right | bottom | left (2~4개 지정할 수 있음)
- 속성값
    - 크기 : 너빗값이나 높잇값을 px이나 em 같은 단위와 함께 수치로 지정
    - 백분율 : 박스 모델을 포함한 부모 요소를 기준으로 너빗값이나 높잇값을 퍼센트(%) 지정
    - auto : display 속성
  
##### margin 속성을 사용하여 웹 문서를 가운데 정렬하기
웹 문서에서 텍스트 요소를 배치할 때는 text-align 속성을 사용해서 정렬한다.  
웹 문서 전체를 중앙에 배치할 때 margin 속성을 사용한다.  
```css
{margin: auto;}
```
- auto로 두면 자동으로 화면의 너비에서 요소 너빗값을 뺀 나머지 영역을 좌우 만진으로 자동 계산 한다.
  
##### 마진 중첩
Margin overlap 마진 중첩 또는 Margin collapse 마진 상쇄 : 요소를 세로로 배치할 경우에 각 요소의 마진과 마진이 서로 만나면 마진값이 큰 쪽으로 겹치지는 문제
- 30px, 30px을 각각 설정했을때 2개가 겹쳐서 60px가 아닌 30px가 된다.
- 여러 요소를 세로로 배치할 때 맨 위의 마진과 맨 아래 마진에 비해 중간에 있는 마진이 지나치게 커지는 것을 방지하는 것
- 아래 마진과 위 마진이 서로 만날 때 큰 마진값으로 햡쳐지는 것
- 오른쪽 마진과 왼쪽 마진이 만날 경우 중첩되지 않는다.

##### 콘텐츠와 테두리 사이의 여백을 설정하는 padding 속성
Padding 패딩 : 콘텐츠 영역과 테두리 사이의 여백
- 테두리 안쪽의 여백
- 4개 방향 : top, right, bottom, left
    
  
#### 3-4. 웹 문서의 레이앙웃 만들기
##### 배치 방법 결정하는 display 속성
display 속성 : 블록 레벨 요소와 인라인 레벨 요소를 서로 바꿔서 사용할 수 있다.  
- 주로 웹 문서의 내비게이션을 만들면서 메뉴 항목을 가로로 배치할 때 사용
- 이미지를 표 형태로 배치 할 때 사용
- 속성값
    - block : 인라인 레벨 요소를 블록 레벨 요소로 만듬
    - inline : 블록 레벨 요소를 인라인 레벨 요소로 만듬
    - inline-block : 인라인 레벨 요소와 블록 레벨 요소의 속서을 모두 가지고 있으며 마진과 패딩을 지정할 수 있음
    - none : 해당 요소를 화면에 표시하지 않음
  
##### 왼쪽이나 오른쪽으로 배치하는 float 속성
웹 문서를 만들다 보면 p 태그처럼 문잔의 왼쪽이나 오른쪽에 이미지를 나란히 표시해야 할 경우가 있다. 그런데 p 태그는 블록 레벨 요소이므로 이미지와 나란히 한 줄에 배치할 수 없다.  
float 속성 : 웹 요소를 문서 위에 떠 있게 만듬
- '떠 있다.' 요소가 왼쪽 구성니나 오른쪽 구석에 배치되는 것
- 속성값
    - left : 해당 요소를 문서의 왼쪽에 배치
    - right : 해당 요소를 문서의 오른쪽에 배치
    - none : 좌우 어느 쪽에도 배치하지 않는다. (기본값)
  
##### float 속성을 해제하는 clear 속성
clear 속성 : float 속성이 더 이상 유용하지 않다고 알려주는 속성
- 속성값
    - left : float: left를 해제
    - right : float: right를 해제
    - both : float: left와 float: right를 해제
  
  
#### 3-5. 웹 요소의 위치 지정하기
##### 웹 요소의 위치를 정하는 left, right, top, bottom 속성
- left : 기준 위치와 요소 사이에 왼쪽으로 얼마나 떨어져 있는지 지정
- right : 기준 위치와 요소 사이에 오른쪽으로 얼마나 떨어져 있는지 지정
- top : 기준 위치와 요소 사이에 위쪽으로 얼마나 떨어져 있는지 지정
- bottom : 기준 위치와 요소 사이에 아래쪽으로 얼마나 떨어져 있는지 지정
  
##### 배치 방법을 지정하는 position 속성
position 속성 : 웹 문서 안의 요소를 자유자재로 배치한다.
- 텍스트, 이미지 요소를 나란히 배치하거나 원하는 위치를 선택할 수 있다.
- 속성값
    - static : 문서의 흐름에 맞춰 배치 (기본값)
    - relative : 위칫값을 지정할 수 있다는 점을 제외하면 static 동일
    - abslute : relative 값을 사용한 상위 요소를 기준으로 위치를 지정 배치
        - 주의점 : 부모 요소에 relative 지정해야 배치할 수 있다.
    - fixed : 브라우저 창을 기준으로 위치를 지정 배치
  


### 04. 이미지와 그라데이션 효과롤 배경 꾸미기
#### 4-1. 배경색과 배경 범위 지정하기
##### 배경색을 지정하는 background-color 속성
background-color 속성 : 배경을 넣고 싶은 요소의 스타일 규칙을 만들 때 사용
- background-color는 상속되지 않는다.
  
##### 배경색의 적용 범위를 조절하는 background-clip 속성
background-clip 속성 : 배경색의 적용 범위를 조절할 수 있다.
- 속성값
    - border-box : 박스 모델의 가장 외곽인 테두리까지 적용(기본값)
    - padding-box : 박스 모델에서 테두리를 뺀 패딩 범위 적용 
    - content-box : 박스 모델에서 내용(콘텐츠) 부분에만 적용
  
  
#### 4-2. 배경 이미지 지정하기
##### 웹 요소에 배경 이미지를 넣는 background-image 속성
```css
{background-image: url('이미지 경로')}
```
background-image 속성 : 웹 요소에 배경 이미지를 넣을 때 사용한다.
- 이미지 파일 : jpg, gif, png
  
##### 배경 이미지의 반복 방법을 지정하는 background-repeat 속성
background-repeat 속성 : 사용하면 배경 이미지를 가로와 세로 중에서 어떤 방향으로 반복 할지 지정하거나, 반복하지 않고 한 번만 나타나게 할 수 있다.
- 속성값
    - repeat : 브라우저 화면에 가득 찰 때까지 가로와 세로로 반복 (기본값)
    - repeat-x : 브라우저 화면에 너비에 가득 찰 때까지 가로로 반복
    - repeat-y : 브라우저 화면에 높에 가득 찰 때까지 세로로 반복
    - no-repeat : 한 번만 표시하고 반복하지 않는다.
  
##### 배경 이미지의 위치로 조절하는 background-position 속성
```css
{background-position: <수평 위치> <수직 위치>;
수평 위치 : left | center | right | 백분율 | 길이 값
수직 위치 : top | center | bottom | 백분율 | 길이 값}
```
background-position 속성 : 배경 이미지의 수평 위치 또는 수직 위치의 값을 지정
- 키워드 : 가장 많이 사용하는 속성값 left, center, right
- 백분율(%) : 요소가 있는 해당 위치에 배경 이미지의 위치를 배분율로 계산하여 맞춘다.
- 크기 : 배경 이미지의 위치를 길이로 직접 지정
  
##### 배경 이미지의 적용 범위를 조절하는 background-origin 속성
background-origin 속성 : 배경 이미지를 적용할 범위을 지정
- 속성값
    - content-box : 박스 모델에서 내용 부분에만 배경 이미지를 표시
    - padding-box : 박스 모델에서 패딩까지 배경 이미지를 표시 (기본값)
    - border-box : 박스 모델에서 테두리까지 배경 이미지 표시
  
##### 배경 이미지를 고정하는 background-attachment 속성
background-attachment 속성 : 배경 이미지를 고정할 수 있다.
- 속성값
    - scroll : 화면을 스크롤하면 배경 이미지도 스크롤 (기본값)
    - fixed : 화면을 스크롤하면 배경 이미지는 고정되고 내용만 스크롤
  
##### backgroud 속성 하나로 배경 이미지 제어하기
```css
body {
    background-image: url("images/bs4.png");
    background-repeat: no-repeat;
    background-position: center bottom;
    background-attachment: fixed;
}

/* 단축적로 작성가능하다 */
body {background: url("images/bs4.png") no-repeat center bottom fixed}
```
  
##### 배경 이미지 크기를 조정하는 background-size 속성
background-size 속성 : 배경 이미지의 크기를 조절할 수 있다.
- 속성값 :
    - auto : 원래 배경 이미지 크기만큼 표시 (기본값)
    - contain : 요소 안에 배경 이미지가 다 들어오도록 이미지를 확대, 축소함
    - cover : 배경 이미지로 요소를 모두 덮더록 이미지를 확대, 축소함
    - 크기 : 이미지의 너비와 높이를 지정, 값이 하나만 주어질 경우 너빗값으로 인식, 이미지의 너비와 너빗값에 맞춘 높잇값도 자동 계산
    - 백분율 : 배경 이미지가 들어가랄 요소의 크기를 기준으로 값을 백분율로 지정하고 그 크기에 맞도록 배경 이미지를 확대, 축소 한다.
  

#### 4-3. 그라데이션 효과로 배경 꾸미기
##### 선형 그라데이션
선형 그라데이션이란, 색상이 수직, 수평 또는 대각선 방향으로 일정하게 변하는 것  
```css
{ background: linear-gradient(to 방향 | 각도, 색상 중지점, [색상 중지점, ...]); }
```
linear-gradient : 선형 그라데이션을 그린다. 색상이 어느 방향으로 바뀌는지 어떤 색상으로 바뀌는지 입력한다.
- 방향 : 그라데이션 방향을 지시
    - to 예약어를 사용, to 다음 최대 2개까지 예약어 사용 가능
    - 수평 : left, right / 수직 : top, bottom
    - to right(왼쪽에서 오른쪽), to right top(왼쪽아래에서 오른쪽위쪽 대각선)
- 각도 : 선형 그라데이션에서 색상이 바뀌는 방향
    - 그라데이션이 끝나는 부분을 deg 표기
    - 시계 방향으로 0, 90, 180, 270(deg)
- 색상 중지점 : 2가지 색 이상의 선형 그라데이션을 만들 때 지정
    - 색상 중지점은 색이 바뀌는 지점
    - 색상 중지점을 지정할 때 쉼표로 색상을 구분
    - 바꿀 색상과 위치(%)를 지정, 끝 색상을 지정
  
##### 원형 그라데이션
원형 그라데이션 : 원 또는 타원의 중심에서부터 동심원을 그리며 바깥 방향으로 색상이 바뀐다.
```css
{ background: radial-gradient(모양 크기 at 위치, 색상 중지점, [색상 중지점, ...])}
```
- 모양 : 원형(circle), 타원형(ellipse) 지정해 그라데이션을 모양을 따로 지정
    - 원형(circle) : 원형 모양으로 그라데이션 생성
    - 타원형(ellipse) : 타원 모양으로 그라데이션 생성(기본값)
- 크기 : 원의 크기를 지정
    - closest-side : 그라데이션 가장자리가 중심에서 가장 가까운 left 측면 닿을 때까지
    - closest-corner : 그라데이션 가장자리가 중심에서 가장 가까운 left top 꼭짓점에 닿을 때까지
    - farthest-side : 그라데이션 가장자리가 중심에서 가장 멀리 떨어진 right 측면 닿을 때까지
    - farthest-corner : 그라데이션 가장자리가 중심에서 가장 멀리 떨어진 right bottom 꼭짓점에 닿을 때까지(기본값)
- 위치 : at 키원드로 원의 그러데이션이 시작하는 원의 중심 표시
    - 위치 속성값 키워드 : left, center, right | top, center, bottom
    - 위치 속성값 백분율(%)
- 색상 중지점 :  색상이 바뀌는 부분
    
##### 그라데이션을 사용한 패턴 만들기
repeating-linear-gradient 속성 : 선형 그라데이션의 패번을 만들 떄 사용
repeating-radial-gradient 속성 : 원형 그라데이션의 패번을 만들 떄 사용
```css
{repeating-linear-gradient(위치, 색1, 색2, ...)}
{repeating-radial-gradient(모양, 색1, 색2, ...)}
```
  

### 05. CSS 고급 선택자
#### 5-1. 연결 선택자
**연결 선택자** : 둘 이상의 선택자를 연결해서 스타일이 적용될 요소가 어느 부분인지 지정한다. 선택자를 둘 이상 조합하므로 '조합 선택자', '콤비네이션 선택자', '콤비네이션 셀렉터' 등으로도 부른다.
  
##### 하위 요소에 스타일을 적용하는 하위 선택자와 자식 선택자
특정 요소를 기준으로 그 안에 포함된 요소를 하위 요소라고 한다. 현재 요소를 기준으로 바로 한 단계 아래 요소는 자식요소, 그 아래를 손자 요소라고 한다.
- 하위 선택자 descendant selector
    ```css
    상위요소 하위요소 { ... }
    ```
    - 하위 선택자를 사용하면 부모 요소에 포함된 하위 요소를 모두 선택하며 자손 선택자라고도 한다.
    - 자식 요소, 손자 요소까지 적용됨
- 자식 선택자 child selector
    ```css
    부모요소 > 자식요소 { ... }
    ```
    - 자식 선택자는 하위 선택자와 다르게 자식 요소에만 스타일을 적용하는 선택자로, &gt; 기호를 표시해 부모요소와 자식 요소를 구분한다.
    - 자식 요소까지만 적용됨 (손자 요소는 적용되지 않음)
  
##### 형제 요소에 스타일을 적용하는 인접 형제 선택자와 형제 선택자
웹 문서에서 부모 요소가 같을 경우 형제 관계라고 하고, 형제 관계인 요소에서 먼저 나오는 요소를 **형 요소**, 나중에 나오는 요소를 **동생 요소**라 한다.
- 인접 형제 선택자 adjacent selector
    - 형제 요소 중에서 첫 번째 동생 요소만 선택 것
    ```css
    요소1 + 요소2 { }
    ```
    - 요소1과 요소2는 같은 레벨이면서 요소1 이후 가장 먼저 오는 요소2를 선택한다.
- 형제 선택자 sibling selector
    - 형제 선택자는 형제 요소의 스타일을 정의하는데 인접 형제 선택자와 달리 모든 형제 요소에 적용된다.
    - 첫 번째 요소와 두 번째 요소 사이에 '~' 기호를 표시한다.
    ```css
    요소1 ~ 요소2 { }
    ```
  
  
#### 5-2. 속성 선택자
##### 특정 속성이 있는 요소를 선택하는 [속성] 선택자
[속성] 선택자 : 여러 가지 속성을 함께 사용할때 그 속성삾에 따라 원하는 요소를 선택하는 것
```css
요소[속성] {}
```
  
##### 특정 속성값이 있는 요소를 선택하는 [속성 = 속성값] 선택자
[속성 = 속성값] 선택자 : 주어진 속성과 속성값이 일치하는 요소를 찾아 스타일을 지정할 때 사용한다. 
```css
요소[속성 = 속성값] {}
```
##### 여러 값 중에서 특정 속성값이 포함된 속성 요소를 선택하는 [속성 ~= 값]선택자
[속성 ~= 값] 선택자 : 여러 속성값 중에서 해당 속성값이 포함된 요소를 선택한다. 
- 속성이 하나면서 속성값이 여러 개일 때 특정 속성값을 찾는데 편리하다.

##### 특정 속성값이 포함된 속성 요소를 선택하는 [속성 |= 값]
[속성 |= 값] 선택자 : 특정 속성값이 포함된 속성에 스타일을 적용한다.
- 속성값은 한 단어로 일치해야 한다.
- 정확하게 값이 일치하거나 지정한 값을 포함해서 하이폰으로 연결된 단어도 선택한다.
  
##### 특정 속성값으로 시작하는 속성 요소를 선택하는 [속성 ^= 값]
[속성 ^= 값] 선택자 : 속성값이 정확하게 일치하지 않더라고 지정한 속성값으로 시작하는 요소를 찾는데 사용한다.
  
##### 특정한 값으로 끝나는 속성의 요소를 선택하는 [속성 $= 값]
[속성 $= 값] : 속성값으로 끝나는 요소를 찾음
  
##### 일부 속성값이 일치하는 요소를 선택하는 [속성 *= 값]
[속성 *= 값] : 속성값이 어느 위치에 있든지 지정한 속성값이 포함되어 있다면 해당 요소를 선택
  
  
#### 5-3. 가상 클래스와 가상 요소
##### 사용자 동작에 반응하는 가상 클래스
사용자가 웹 요소를 클릭하거나 마우스 포인터를 올려놓는 등 특정 동작을 할 때 스타일이 바뀌도록 만들고 싶다면 가상 클래스 선택자를 사용한다.
1. 방문하지 않은 링크에 스타일을 적용하는 ':link 가상 클래스 선택자'
    - 방문전에 파랑색의 밑줄 글자로 표시, 방문 후 색과 밑줄이 제거
2. 방문한 링크에 스타일을 적용하는 ':visited 가상 클래스 선택자'
    - 한 번 이상 방문한 텍스트 링크는 보라색이 기본값
3. 특정 요소에 마우스 포인터를 올려놓으면 스타일을 적용하는 ':hover 가상 클래스 선택자'
    - 메인 메뉴 위로 마우스 포인터를 올려놓았을 때 서브메뉴가 나타나는 효과
4. 웹 요소를 활성화했을 때 스타일을 적용하는 ':active 가상 클래스 선택자'
    - 링크나 이미지 등이 활성화했을 때 스타일을 지정
5. 웹 요소에 초점이 맞추어졌을 때 스타일을 적용하는 ':focus 가상 클래스 선택자'
    - 웹 요소에 초점이 맞추어졌을 때 스타일을 적용
  
##### 요소 상태에 따른 가상 클래스
웹 사이트나 애플리케이션 화면에서 요소의 상태에 따라 스타일을 적용할 수 있는데, 이때 가상 클래스 선택자를 사용한다.
1. ':target 가상 클래스 선택자' : 앵커 대상에 스타일 적용한다.
    - 같은 문서안에서 다른 위치로 이동할 때는 앵커(anchor)를 이용한다.
    - 앵커로 연결된 부분, 즉 앵커의 목적지가 되는 부분의 스타일을 쉽게 적용
2. ':enabled와 :disabled 가상 클래스 선택자' : 요소의 사용 여부에 따라 스타일을 적용한다.
    - :enabled : 해당 요소가 사용할 수 있는 상태일 때 스타일을 지정
    - :disabled : 해당 요소가 사용할 수 없는 상태일 때 스타일을 지정
3. ':checked 가상 클래스 선택자' : 선택한 항목의 스타일을 적용한다.
    - 폼의 라디오 박스나 체크 박스에서 선택된 항목에 스타일을 적용
4. ':not 가상 클래스 선택자' : 특정 요소를 제외하고 스타일을 적용한다.
    - '괄호 안에 있는 요소를 제외한' 이라는 의미
  
##### 구조 가상 클래스
구조 가상 클래스 : 웹 문서의 구조를 기준으로 특정 위치에 있는 요소를 찾아 스타일을 적용 할 때 사용하는 가상 클래스 선택자
- 특정 위치의 자식 요소 선택
    - class나 id를 사용하지 않고도 스타일을 지정
    - :only-child : 부모 안에 자식 요소가 하나뿐일 때 자식 요소를 선택
    - A:only-type-of : 부모 안에 A 요소가 하나뿐일 때 선택
    - :first-child : 부모 안에 있는 모든 요소 중에서 첫 번째 자식 요소를 선택
    - :last-child : 부모 안에 있는 모든 요소 중에서 마지막 자식 요소 선택
    - A:first-of-type : 부모 안에 있는 A 요소 중에서 첫 번째 요소 선택
    - A:last-child : 부모 안에 있는 A 요소 중에서 마지막 요소를 선택
    - :nth-child(n) : 부모 안에 있는 모든 요소 중에서 n번째 요소 선택
    - :nth-last-child(n) : 부모 안에 있는 모든 요소 중에서 끝에서 n번째 요소 선택
    - A:nth-of-type(n) : 부모 안에 있는 A 요소 중에서 n번째 요소 선택
    - A:nth-last-of-type(n) : 부모 안에 있는 A 요소 중에서 끝에서 n번째 요소 선택
- 수식을 사용해 위치 지정하기
    - :nth-child(n) 선태자에서 홀수 번째만 선택하고 싶다면 2n+1 or odd
    - 짝수 번째만 선택하고 싶다면 2n or even
  
##### 가상 요소
가상 요소는 문서 안의 특정 부분에 스타일을 지정하기 위해 가상으로 요소를 만들어 추가한다. 가상 요소를 만들어 사용하는 이유는 특별히 화면에 보이는 부분을 꾸밀 때 불필요한 태그를 사용하지 않도록 하기 위한 것
- 첫 번째 줄, 첫 번째 글자에 스타일을 적용하는 '::first-line 요소, ::first-letter 요소'
- 내용 앞뒤에 콘텐츠를 추가하는 '::before 요소, ::after 요소'
  


### 06. 트랜지션과 애니메이션
#### 6-1. 변형 알아보기
##### transform과 변형 함수
```css
transform: 함수
```
- transform() : 웹 요소를 이동시키는 변형 함수
- 2차원 변형
    - 웹 요소를 평면에서 변형
    - 수평 방향, 수직 방향으로 왜곡
    - x축 : +(오른쪽),-(왼쪽) / y축 : +(아래쪽),-(위쪽)
    - 함수
        - translate(tx, ty) : 지정한 크기만큼 x축, y축으로 이동
        - translateX(tx) : 지정한 크기만큼 x축으로 이동
        - translateY(ty) : 지정한 크기만큼 y축으로 이동
        - scale(sx, sy) : 지정한 크기만큼 x축 y축으로 확대-축소
        - scaleX(sx) : 지정한 크기만큼 x축으로 확대-축소
        - scaleY(sy) : 지정한 크기만큼 y축으로 확대-축소
        - rotate(각도) : 지정한 각도만큼 회전
        - skew(ax, ay) : 지정한 각도만큼 x축과 y축으로 왜곡합니다.
        - skewX(ax) : 지정한 각도만큼 x축으로 왜곡
        - skewY(ay) : 지정한 각도만큼 y축으로 왜곡
- 3차원 변형
    - x축과 y축에 원근감을 주는 z축을 추가해서 변형한다.
    - z축 : +(뒤로 이동), -(앞으로 이동)
    - 함수
        - translate3d(tx, ty, tz) : 지정한 크기만큼 x축, y축, z축으로 이동
        - translateZ(tz) : 지정한 크기만큼 z축으로 이동
        - scale3d(sx, sy, sz) : 지정한 크기만큼 x축, y축, z축으로 확대 축소
        - scaleZ(sz) : 지정한 크기만큼 z축으로 확대 축소 
        - rotate(rx, ry, 각도) : 지정한 각도만큼 회전
        - rotate3d(rx, ry, zy, 각도) : 지정한 각도만큼 회전
        - rotateX(각도) : 지정한 각도만큼 x축 회전
        - rotateY(각도) : 지정한 각도만큼 y축 회전
        - rotateZ(각도) : 지정한 각도만큼 z축 회전
        - perspective(길이) : 입체적으로 보일 수 있도록 갚잇값을 지정
  
##### 웹 요소를 이동시키는 translate() 함수
```css
transform: translate(tx, ty)
transform: translate3d(tx, ty, tz)
transform: translateX(tx)
transform: translateY(ty)
transform: translateZ(tz)
```
  
##### 요소를 확대-축소하는 scale() 함수
```css
transform: scale(sx, sy)
transform: scale3d(sx, sy, sz)
transform: scaleX(sx)
transform: scaleY(sy)
transform: scaleZ(sz)
```
  
##### 요소를 회전시키는 rotate() 함수
- 2차원 rotate()
    ```css
    transform: rotate(각도)
    ```
    rotate() 함수에서 지정할 수 있는 각도의 값은 일반적인 각도나 래디안을 사용하는데, 이때 1래디안은 180도/파이를 의미한다.
    - 양수 : 시계 방향 | 음수 : 시계 반대 방향
- 3차원 rotate()
    ```css
    transform: rotate(rx, ry, 각도)
    transform: rotate3d(rx, ry, rz, 각도)
    transform: rotateX(각도)
    transform: rotateY(각도)
    transform: rotateZ(각도)
    ```
- perspective() 속성 : 3차원 변형에서 사용하는 속성으로 원래 있던 위치에서 사용자가 있는 방향의나 혹은 반대 방향으로 잡아닿기거나 밀어내어 원근감을 표현한다.
    - 값이 클수록 사용자로부터 멀어진다.
    - 변형하는 요소가 아니라 변형하는 요소의 부모 요소에 정의해야 한다.
      
##### 요소를 비틀어 왜곡하는 skew() 함수
```css
transform: skew(x, y)
transform: skewX(x)
transform: skewY(y)
```
skew() : 지정한 각도만큼 요소를 비틀어 왜곡한다. 이떄 양쪽 방향으로 비틀거나 한쪽 방향으로만 비틀 수도 있다.  
  

#### 6-2. 트랜지션 알아보기
##### 트랜지션transition
트랜지션 : 웹 요소의 배경색을 바꾸거나 도형의 테두리를 사각형에서 원형으로 바꾸는 것처럼 스타일 속성이 바뀌는 것을 말한다.
  
##### 트랜지션과 속성
- **transition-property** : 트랜지션 대상 지정
    ```css
    transition-property: all | none | 속성이름
    ```
    - all : 사용하거나 생략할 경우 요소의 모든 속성이 트랜지션 대상이 된다.(기본값)
    - none : 트랜지션을 하는 동안 아무 속성도 바뀌지 않는다.
    - 속성 이름 : 트랜지션 효과를 적용할 속성을 지정, 속성이 여럿일 경우 쉼표(,)
- **transition-duration** : 트랜지션 실행할 시간 지정
    ```css
    transition-duration: 시간
    ```
    - 진행 시간을 지정해 자연스업게 바뀌는 애니메이션 효과를 만들 수 있다.
    - 시간 단위 : 초, 밀리초
    - 대상 속성이 여러 개인 경우 쉼표(,)로 구분해 여러 개를 지정할 수 있다.
- **transition-timing-function** : 트랜지션 실행 형태 지정
    ```css
    transition-timing-function: linear | ease | ease-in | ease-out | ease-in-out | cubic-bezier(n,n,n,n)
    ```
    - linear : 시작부터 끝까지 똑같은 속도로 진행
    - ease : 처음에는 천천히 시작하고 점점 빨라지다 마지막에 천천히 (기본값)
    - ease-in : 느리게 시작
    - ease-out : 느리게 끝냄
    - ease-in-out : 느리게 시작하고 느리게 끝냄
    - cubic-bezier(n,n,n,n) : 베지에 함수를 정의, n값은 0~1 사이
- **transition-delay** : 트랜지션 지연 시간을 지정
    ```css
    transition-delay: 시간
    ```
    - 트랜지션 효과를 언제부터 시작할 것인지 설정
    - 지정한 시간만큼 기다렸다가 트랜지션이 시작됨
    - 기본값 : 0
    - 초, 밀리초
- **transition** : 위의 속성을 한꺼번에 지정
    ```css
    transition: property값 | duration값 | timing-function값 | delay값
    ```
    
#### 6-3. 애니메이션 알아보기
##### CSS 애니메이션에서 사용하는 속성
css3의 animation 속성을 사용하면 자바스크립트를 사용하지 않고도 웹 요소에 애니메이션을 추가할 수 있다. animation 속성은 특정 지점에서 스타일을 바꾸면서 애니메이션을 만드는데, 이렇게 애니메이션 중간에 스타일이 바뀌는 지점을 **키프레임Keyframe** 이라고 한다.
- **@keyframes** : 키프레임을 지정
    ```css
    @keyframes 이름 {
        선택자 { 스타일 }
    }
    ```
- animation 속성
    - **animation-delay** : 애니메이션의 시작 시간 지정
        ```css
        animation-delay: 시간
        ```
        - 값은 초나 밀리초
        - 기본값 = 0 (애니메이션은 실행되지 않는다.)
    - **animation-duration** : 애니메이션을 종료한 뒤 처음부터 시작할지, 역방향으로 진행할지 지정
    - **animation-duration** : 애니메이션 실행 시간
        ```css
        animation-direction: normal | revers | alternate | alternate-reverse
        ```
        - normal : 애니메이션을 from에서 to로 진행 (기본값)
        - reverse : 애니메이션을 to에서 from으로 진행
        - alternate : 홀수 번째는 normal로, 짝수 번째는 reverse로 진행
        - alternate-reverse : 홀수 번째는 reverse, 짝수 번쨰는 normal로 진행
    - **animation-iteration-count** : 애니메이션 반복 횟수
        ```css
        animation-iteration-count: 숫자 | infinite
        ```
        - 숫자 : 반복 횟수
        - infinite : 무한 반복
    - **animation-name** : @keyframes로 설정한 중간 상태를 지정
        ```css
        animation-name: 키프레임 이름 | none
        ```
    - **animation-timing-function** : 키프레임의 전환 형태 지정
        ```css
        animation-timing-function: linear | ease | ease-in | ease-out | ease-in-out | cubic-bezier(n,n,n,n)
        ```
        - 애니메이션의 시작, 중간, 끝에서 속도를ㄹ 지정
    - **animation** : 애니메이션 속성 전부
        ```css
        animation: name | duration | timing-function | delay | iteration-count | direction
        ```
        - 여러 애니메이션 속성을 한줄에 쓸 수 있다.
        - 두 개이상의 애니메이션은 쉼표(,) 사용해 구분한다.
  
  
### 07. 반응형 웹과 미디어 쿼리
#### 7-1. 반응형 웹
##### 반응형 웹 디자인이란
반응형 웹 디자인 reponsice web design : 웹 요소를 화면 크기에 맞게 재배치하고 각 요소의 표시 방법만 바꾸어 사이트를 구현하는 것이다. 이는 pc나 모바일 기기 등 화면 크기에 따라 화면 요소를 자동으로 바꾸는 것이다.
  
##### 모바일 기기를 위한 뷰포트
뷰포트Viewport : 스마트폰 화면에서 실제 내용이 표시되는 영역이다.
- pc와 모바일의 차인의 원인은 화면에서 표시하는 픽셀차이
- 웹키트webkit를 기반으로 한 모바일 브라우저의 기본 뷰포트 너비는 980px
- 이떄, 스마트폰용 웹 사이트를 320px로 만들면 제작자가 의도한 웹 사이트가 안 만들어 진다.
  
##### 뷰포트 지정하기
```css
<meta name="viewport" content="속성1=값1, 속성2=값2, ... ">
```
- 뷰포트는 "meta" 태그를 이용해 "head" 태그에 작성한다.
- 속성
    - width : 뷰포트 너비, device-width 또는 크기, 브라우저 기본값
    - height : 뷰포트 높이, device-height 또는 크기, 브라우저 기본값
    - user-scalable : 확대-축소 가능 여부, yes(기본값) or no 
    - initial-scale : 초기 확대-축소 값, 1(기본값) ~ 10
  
##### 뷰포트 단위
- vw(viewport width) : 1vW = 1%
- vh(viewport height) : 1vh = 1%
- vmin(viewport minimum) : 뷰포트의 너비와 높이 중에서 작은 값이 1%와 같다.
- vmax(viewport maximum) : 뷰포트의 너비와 높이 중에서 큰 값이 1%와 같다.
  
  
#### 7-2. 미디어 쿼리
##### 미디어 쿼리
미디어 쿼리media queries : 사이트에 접속하는 장치에 따라 특정한 css 스타일을 사용하는 방법이다. 미디어 쿼리를 사용하면 접속하는 기기의 화면 크기에 따라 레이아웃이 달라진다.
  
**미디어 쿼리 구문**
```css
@media [only | not] 미디어 유형 [and 조건] * [and 조건]
```
@media 속성 : 미디어 퀴리를 사용해 특정 미디어에서 어떤 css를 적용할 것인지 지정해 준다.
- "stykle" 태그 사이에 사용하며 대소 문자를 구별하지 않는다.
- 속성값
    - only : 미디어 쿼리를 지원하지 않는 웹 브라우저에서는 미디어 쿼리를 무시하고 실행하지 않는다.
    - not : not 다음에 지정하는 미디어 유형을 제외한다.
    - and : 조건을 여러 개 연결해서 추가
- 미디어 유형의 종류
    - all : 모든 미디어 유형에서 사용할 css를 정의
    - print : 인쇄 장치에서 사용할 css 정의
    - screen : 컴퓨터 스크린에서 사용할 css 정의, 스마트폰의 스크린도 포함
    - tv : 음성과 영상이 동시에 출력되는 TV에서 사용할 css 정의
    - aural : 음성 합성 장치(주로 화면을 읽어 소리로 출력해 주는 장치)에서 css 정의
    - braille : 점자 표시 장치에서 사용할 css 정의
    - handheld : 패드처럼 손에 들고 다니는 장치를 위한 css 정의
    - projection : 프로젝터를 위한 css 정의
    - tty : 디스플레이 기능이 제한된 장치에 맞는 css 정의, 이런 장치에서는 px 단위를 사용할 수 없다.
    - embossed : 점자 프린터에서 사용할 css 정의
- 웹 문서의 가로 너비와 세로 높이 속성
    - 조건에 사용
    - width, height : 웹 페이지의 가로 너비, 세로 높이 지정
    - min-width, min-height : 웹 페이지의 최소 너비, 최소 높이를 지정
    - max-width, max-height : 웹 페이지의 최대 너비, 최대 높이를 지정
- 단말기의 가로 너비와 세로 높이 속성
    - device-width, device-height : 단말기의 가로 너비, 세로 높이 지정
    - min-device-width, min-device-height : 단말기 최소 너비, 최소 높이 지정
    - max-device-width, max-device-height : 단말기 최대 너비, 최대 높이 지정
- 화면 회전 속성
    - orientation 속성 기기의 방향을 확인할 수 있고, 그에 따라서 웹 사이트의 레이아웃을 바꿀 수 있다.
    - orientation: portrait : 단말기의 세로 모드를 지정
    - orientation: landscape : 단말기의 가로 모드를 지정
- 미디어 쿼리의 중단점
    - 중단점break point : 미디어 쿼리를 작성할 때 화면 크기에 따라 서로 다른 css를 적용할 분기점
    - 대부분 기기의 화면 크기를 기준으로 css거 달라지고 화면 레이아웃이 바뀐다.
    - 하지만, 시중의 모든 기기를 반영 할 수 없어 모바일, 테블릿, 데스크톱으로 구분
    - 처리 속도, 화면 크기 등에서 모바일 기기가 제약 조건이 더 많음
    - 모바일 퍼스트mobile first : 모바일용 css 먼저 제작 후  제약이 적은 태블릿이나 데스크톱에 더 많은 기능과 스타일을 추가하는 방법 (반대도 존재함)
    - 기기별 조건
        - 스마트폰: 모바일 페이지는 미디어 쿼리를 사용하지 않고 기본 css 작성, min-width 세로와 가로를 각각 portrit 320px, landscape 480px
        - 태블릿: 세로 크기가 768px 이상이면 태블릿으로 지정, 가로 크기는 데스크톱과 같은 1024px 이상 지정
        - 데스크톱: 화면 크기가 1024px 이상이면 데스크톱으로 설정
- 모바일 기기의 뷰포트 크기 : yesviz.com/devices.php
  
##### 미디어 쿼리 적용하기
- 외부 CSS 파일 연결 방법
    ```css
    <link rel="stylesheet" media="미디어 쿼리 조건" href="css 파일 경로">

    @import url(css 파일 경로) 미디어 쿼리 조건
    ```
    각 조건별로 css 파일을 따로 저장한 뒤 link 태그나 @import 문을 사용해서 연결한다.
    - link : head 태그 사이에 넣는다. 
    - @import : style 태그 사이에 넣는다.
    - css 파일이 많고 규모가 큰 사이트에 경우 @import보다 link 태그를 사용
- 웹 문서에서 직접 정의
    ```css
    <style media="<조건>"> {
        <스타일 규칙>
    }
    </style>


    <style>
        @media <조건> {
            <스타일 규칙>
        }
    </style>
    ````
    웹 문서에서 미디어 쿼리를 직접 지정하는 방법으로 위와 같이 2가지 방법이 존재한다.
  
  
#### 7-3. 그리드 레이아웃
##### 그리드 레이아웃이란?
그리 레이아grid layout : 웹 사이트를 여러 개의 칼럼co
lumn으로 나눈 후 메뉴나 본문, 이미지 등의 웹 요소를 화면에 맞게 배치하는 것을 말한다. 그리드 레이아웃을 사용하면 화면을 규칙적으로 배열하므로 레이아웃을 일관성 있게 유지할 수 있다.  
- 특징
    1. 시각적으로 안정된 디자인을 만들 수 있다.
        - 여러 개의 칼럼으로 구성해서 밑으로 블어뜨리는 그리드 레이아웃이 안정감을 준다.
    2. 업데이트가 편한 웹 디자인을 구성할 수 있다.
        - 실제 내용을 넣지 않은 상태에서도 사이트 레이아웃을 미리 만즐어 볼 수 있다. 사이트나 콘텐츠 영역의 너비, 각 요소의 위치 등 사이트 구조를 먼저 만들어 놓고 내용을 추후 넣을 수 있다. 업데이트에 유리하다.
    3. 요소를 자유롭게 배치할 수 있다.
        - 한 줄에 여러 요소를 배치할 수 있고, 중요한 내용은 좀 더 넓은 공간에 두어 사용자에게 잘 보이게 할 수 있다.
  
##### 그리드 레이아웃을 만드는 방법
1. CSS의 float 속성 가변 그리드
2. 플렉서블 박스 레이아웃 flexible box layout or 플렉스 박스 레이아웃 flex box layout
    - 그리드 레이아웃을 기본으로 하고 각 박스를 원하는 위치에 따라 배치하는 것, 이때 여유 공간이 생길 경우 너비나 높이를 적절하게 늘이거나 줄일 수 있다.
    - 플렉스 박스는 수평 방향이나 수직 방향 중에서 한쪽을 **주축**으로 정하고 박스를 배치한다.
3. CSS 그리드 레이앙웃 CSS grid layout
    - 수평과 수직 어느 방향이든 배치할 수 있다. 마치 레고 블록 처럼 끼워 맞추듯
    - 대부분 모던 브라우저에 사용
  

#### 7-4. 플렉스 박스 레이아웃
##### 플렉스 박스 레이아웃에서 사용하는 용어
플렉스 박스 레이아웃은 그리드 레이앙수을 기본으로 한 새로은 개념이다.
- 플렉스 컨테이너(부모 박스) : 플렉스 박스 레이아웃을 적용할 대상의 묶음 요소
- 플렉스 항목(자식 박스) : 플렉스 박스 레이아웃을 적용할 대상
- 주축(main axis) : 플렉스 컨테이너 안에서 플렉스 항목을 배치하는 기본 방향, 기본적으로 왼쪽에서 오른쪽이며 수평 방향으로 배치, 
    - 주축 시작점 : 플렉스 항목 시작되는 위치
    - 주축 끝점 : 플렉스 항목 끝나는 위치
- 교차축(cross axis) : 주축과 교차하는 방향ㅇ을 말하며 기본적으로 위에서 아래로 배치
    - 교차축 시작점 : 플렉스 항목 시작되는 위치
    - 교차축 끝점 : 플렉스 항목 끝나는 위치
  
##### 플렉스 박스 항목을 배치하는 속성
- 속성
    - justify-content : 주축 방향의 정렬 방법
    - align-items : 교차축 방향의 정렬 방법
    - align-self : 교차축에 있는 개별 항목의 정렬 방법
    - align-content : 교차축에서 여러 줄로 표시된 항목의 정렬 방법
- 플렉스 컨테이너를 지정하는 display 속성
    - 웹 콘텐츠에 요소를 감싸는 플렉스 컨테이너를 만들어 주는 속성
    - 속성값
        - flex : 컨테이너 안의 플렉스 항목을 블록 레벨 요소 배치
        - inline-flex : 컨테이너 안의 플렉스 항목을 인라인 레벨 요소로 배치
- 플렉스 방향을 지정하는 flex-direction 속성
    - 주축과 방향을 지정하는 속성
    - 속성값
        - row : 주축을 가로로 지정하고 왼쪽에서 오른쪽으로 배치 (기본값)
        - row-reverse : 주축을 가로로 지정, 오른쪽에서 왼쪽으로 역방향으로 배치
        - column : 주축을 세로로 지정 위쪽에서 아래쪽으로 배치
        - column-reverse : 주축을 세로로 지정 아래쪽에서 위쪽으로 역방향으로 배치
- 플렉스 항목의 줄을 바꾸는 flex-wrap 속성
    - 플렉스 컨테이너 너비보다 많은 플렉스 항목이 있을 경우 줄을 바꿀지 여부를 지정
    - 속성값
        - nowrap : 플렉스 항목을 한 줄에 표시(기본값)
        - wrap : 플렉스 항목을 여러 줄에 표시
        - wrap-reverse : 플렉스 항목을 여러 줄에 표시하되, 시작점과 끝점이 바뀜
- 배치 방향과 줄 바꿈을 한꺼번에 지정하는 flex-flow 속성
    - flex-direction과 flex-wrap 속성을 한꺼번에 지정하여 플렉스 항목의 배치 방향을 결정하거나 줄을 바꿈 (기본값 = row nowrap)
- 주축 정렬 방법을 지정하는 justify-content 속성
    - 주축에서 플렉스 항목 간의 정렬 방법을 지정
    - 속성값
        - flex-start : 주축의 시작점에 맞춰 배치
        - flex-end : 주축의 끝점에 맞춰 배치
        - center : 주축의 중앙에 맞춰 배치
        - space-between : 첫 번째 항목과 끝 항목을 주축의 시작점과 끝점에 배치한 후 나머지 항목은 그 사이에 같은 간격으로 배치
        - space-around : 모든 항목을 주축에 같은 간격으로 배치
- 교차축 정렬 방법을 지정하는 align-items 속성
    - 교차축을 기준으로 플렉스 항목을 정렬
    - 속성값
        - flex-start : 교차축의 시작점에 맞춰 배치
        - flex-end : 교차축의 끝점에 맞춰 배치
        - center : 교차축의 중앙에 배치
        - baseline : 교차축의 문자 기준선에 맞춰 배치
        - streth : 플렉스 항목을 늘려 교차축에 가득 차게 배치
- 특정 항목만 정렬 방법을 지정하는 align-self 속성
    - 교차축을 기준으로 정렬된 항목 중에서 특정 항목만 지정하고 싶을 때 사용
    - 플렉스 항목 선택자에서 사용 
- 여러 줄일 때 교차축 정렬 방법을 지정하는 align-content 속성
    - 주축에서 줄 바꿈이 생겨서 플렉스 항목을 여러 줄로 표시할 때
    - 교차축에서 플렉스 항목 간의 간격을 지정
    - 속성값
        - flex-start : 교차축의 시작점에 맞춰 배치
        - flex-end : 교차축의 끝점에 맞춰 배치
        - center : 교차축의 중앙에 맞춰 배치
        - space-between : 첫 번째 항목과 끝 항목을 교차축의 시작점과 끝점에 맞추고 나머지 항목은 그 사이에 같은 간격으로 배치
        - space-around : 모든 항목을 교차축에 같은 간격으로 배치
        - stretch : 플렉스 항목을 늘려서 교차축에 가득 차게 배치
- 플렉스 레이아웃을 활용해 항상 중앙에 표시하기
  
#### 7-5. CSS 그리드 레이아웃
CSS 그리드 레이아웃은 소스를 최대한 간단하게 유지하면서 대부부느이 기기에 대응할 수 있는 그리드 레이아웃 기법이다.
  
##### CSS 그리드 레이아웃에서 사용하는 용어
CSS 그리디 레이아웃은 그리드 항목을 배치할 때 가로와 세로를 모두 사용한다. 그래서 플렉스 항목은 1차원 css 그리드는 2차원이라고 한다.
- 줄 row : 가로방향
- 칼럼 column : 세로 방향
- 줄과 줄 - 칼럼과 칼럼 사이 간격
  
##### CSS 그리드 레이아웃 항목을 배치하는 속성
- 그리드 컨테이너를 지정하는 display 속성
    - 적용할 요소의 바깥 부분을 그리드 컨테이너를 생성
    - 속성값
        - gird : 컨테이너 안의 항목을 블록 레벨 요소로 배치
        - inline-grid : 컨테이너 안의 항목을 인라인 레벨 요소로 배치
- 칼럼과 줄을 지정하는 grid-template-columns, grid-template-rows 속성
    - 그리드 컨테이너 안에 항목을 배치할 때 칼럼과 줄의 크기와 개수를 지정
    - grid-template-columns : 그리드 컨테이너 안의 항목을 몇 개의 칼럼으로 배치, 너비를 얼마로 할지 지정
    - grid-template-rows : 그리드 컨테이너 안의 항목을 몇 개의 줄로 배치, 너비를 얼마로 할지 지정
- 상대적인 크기를 지정하는 fr 단위
    - px은 항상 크기가 고정되므로 반응형 웹 디자인에 적합하지 않다.
    - 그리드 레ㅔ이아웃에서는 상대적인 크기를 지정할 수 있는 fr(fraction) 단위 사용
- 값이 반복될 때 줄여서 표현할 수 있는 repeat()함수
    - px이나 fr 단위를 똑같은 수치를 여러번 적는 것을 방지
- 최솟값과 최댓값을 지정하는 minmax()
    - 줄 높이를 고정하지 않고 최솟값과 최댓값을 사용해서 유연하게 지정할 수 있다.
- 자동으로 칼럼 개수를 조절하는 auto-fill, auto-fit 값
    - auto-fit : 화면이 넓을 때에는 남는 공간 없이 꽉 채워서 칼럼을 표시
    - auto-fill : 칼럼의 최소 너비만 표시하고 남는 공간은 그대로 둔다.
- 그리드 항목의 간격을 지정하는 grid-column-gap, grid-row-gap, grid-gap 속성
    - grid-column-gap : 칼럼과 칼럼 사이의 간격을 지정
    - grid-row-gap : 줄과 줄 사이의 간격을 지정
    - grid-gap :칼럼과 줄 사이의 간격을 한꺼번에 지정
- 그리드 라인을 이용한 배치
    - 그리드 레이아웃은 눈에 보이지 않는 그리드 라인이 포함되어 있다.
    - n개의 칸을 만들었을 경우 n+1개의 줄이 만들어 진다.앞에서 부터 1 ~ n+1 번
    - 속성값
        - grid-column-start : 칼럼 시작의 라인 번호를 지정
        - grid-column-end : 칼럼 마지막의 라인 번호를 지정
        - grid-column : 칼럼 시작번호와 칼럼 끝 번호 사이에 슬래시(/)를 넣어 사용
        - grid-row-start : 줄 시작의 라인 번호 지정
        - grid-row-end : 줄 마지막의 라인 번호 지정
        - grid-row : 줄 시작번화와 컬럼 끝 번호 사이에 슬래시(/)를 넣어 사용
- 템플릿 영역을 만들어 배치
    - 템플릿 영역으로 항목을 배치면 그리드 레이앙웃을 만드는 것보다 쉽다.
    - grid-area : 각 영역에 템플릿 이름을 지정
    - grid-template-areas : 템플릿 영역을 어떻게 배치할지 지정
        - 큰 따음표 (" ") : 따음표 안에 템플릿 이름을 칸 만큼 지정
        - 마침표(.) : 비워 두려는 자리

