# HTML
## HTML - 1
### 01. HTML 기본 문서 만들기
#### HTML 이란?
HTML(Hyper Text Markup Language)
- 웹 문서의 구조 및 내용을 정의해 웹 문서를 만드는 언어이다.
- 하이퍼텍스트란? 문서를 서로 연결해 주는 링크를 의미한다.
- 마크럽이란? 웹 브라우저에 내용을 보여주는 텍스트, 이미지, 영상 등의 위치를 표시
  
##### 주요 구성 요소
1. **태그 (Tags)**: `<태그명>` 형식, 웹 페이지의 다양한 요소를 정의
2. **속성 (Attributes)**: 태그에 추가 정보 제공, 예: `<a href="주소">`
3. **요소 (Elements)**: 시작 태그와 종료 태그 사이의 내용, 예: `<p>문단</p>`
  
#### 기본 구조
HTML문서는 정해진 형식에 맞춰어 내용을 입력한다.  
<!DOCTYPE html> 시작해서  
<html>,<head>,<body> 3개의 영역으로 구성한다.
  
```html
<!DOCTYPE html>
<html>
  <head>
    <title>페이지 제목</title>
  </head>
  <body>
    <h1>제목</h1>
    <p>문단</p>
  </body>
</html>
```
  
1. <!DOCTYPE html> :  
  - 현재 문서가 HTML 5 언어로 작성한 웹 문서
2. <html> ~ </html> :  
  - 웹 문서의 시작과 끝을 나타내는 태그
3. <head> ~ </head> :  
  - 웹 브라우저가 웹 문서를 해석하는 데 필요한 정보를 입력하는 부분
  - <meta> :  
      - 데이터에 관한 데이터
      - 웹 문서와 관련된 정보를 지정
      - 가장 중요한 화면에 글자를 표시할 때 어떤 **인코딩**을 사용할지 지정하는 것
      - 웹 서버는 영어가 기본, 한글 -> **"UTF-8"**  
      ```html
      <meta charset="UTF-8">
      <meta name="keywords" content="html의 구조">
      <meta name="description" content="html의 구조를 알아봅시다">
      <meta name="author" content="Kyunghee Ko">
      ```
  - <title> ~ </title> :  
      - 웹 문서의 제목을 입력하는 태그로 가장 중요한 태그
      - 제목 표시줄의 제목으로 표시된다.
4. <body> ~ </body> :  
  - 실제로 웹 브라우저 화면에 나타나는 내용
  
#### 