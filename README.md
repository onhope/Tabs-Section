# Tabs-Section
<img src="./image.gif">

## 효과 
탭을 클릭하면, 해당 탭으로 이동

## 학습  
### 1. JS : HTMLElement: dataset property   
**HTMLElement에 대한 읽기/쓰기 액세스를 제공**      
- **html의 변수 역할**   
  : 태그 내에 data- 로 시작하는 키워드를 기재하고 그 뒤에 하이픈(-)이 조합된 형태로 개발자가 정의하고 싶은 속성명을 기재해주고 속성값을 써주면 사용자 변수가 완성      
  
  : 데이터 속성을 쓰면 훨씬 스크립트가 간결해지며 또한 하나의 요소에는 여러 데이터 속성을 동시에 사용할 수도 있어 확장성이 높다.   

  : 데이터셋에 배열, 객체 데이터 저장    
  ```
  <!-- 객체 형태로 된 문자열 데이터셋 -->
  <div data-person='{"name": "Chris Coyier", "job": "Web Person"}'></div>

  <!-- 배열 형태로 된 문자열 데이터셋 -->
  <div data-fruit='["apple", "banana", "melon"]'></div>
  ```
<br>    

- **HTML**   
속성 이름은 data-으로 시작됩니다 . 문자, 숫자, 대시( -), 마침표( .), 콜론( :) 및 밑줄( _)만 포함할 수 있습니다. 모든 ASCII 대문자( A~ Z)는 소문자로 변환됩니다.
  ```
    <button class="button live" data-id="step1">Step 1</button>
    <button class="button" data-id="step2">Step 2</button>
    <button class="button" data-id="step3">Step 3</button>  
  ```
  <br>

- **자바스크립트**   
사용자 정의 데이터 속성의 속성 이름은 data-접두사가 없는 HTML 속성과 동일하며, 속성의 " 카멜 케이스- " 이름을 대문자로 사용하는 경우 단일 대시( )를 제거합니다 .

<br>   

- **값에 접근하기**     
  
  속성은 데이터 세트의 객체 속성인 camelCase 이름/키로 설정하고 읽을 수 있습니다       
  ```
  element.dataset.keyname.
  ```       
  대괄호 구문을 사용하여 속성을 설정하고 읽을 수도 있습니다        
    ```
    element.dataset['keyname']
    ```
  운영자 in는 주어진 속성이 존재하는지 확인할 수 있습니다 
  ```
  'keyname' in element.dataset
  ```
  예) 데이터 접근하기 
  1. dataset 프로퍼티로 접근     
    : 자바스크립트에서 변수명으로 - 기호가 허용되지 않기 때문에, 속성 이름이 자동으로 낙타 표기법(Camel-Case) 으로 변환된다.   
   
      ```
      <div id="post" 
        data-columns="3" 
        data-title="javascript" 
        data-index-number="123">
      </div >
      ```

      ```
      const $div = document.getElementById('post');
 
      // 일반적인 객체 속성 접근
      $div.dataset.columns // "3"

      // 배열 인덱스로 접근
      $div.dataset['title'] // "javascript"

      // data-index-number에서 dataset.indexNumber로 변환
      $div.dataset.indexNumber // "12314"
      ```

  2. 일반적인 속성 접근 메서드 getAttribute() 사용     
      ```
      const $div = document.getElementById('post');
 
      $div.getAttribute('data-columns') // "3"

      $div.getAttribute('data-title') // "javascript"

      $div.getAttribute('data-index-number') // "12314"
      ```
<br>

- **데이터셋 추가 / 변경 하기**   
  
  1. dataset 프로퍼티로 접근해 추가/변경
   
      ```
      const $div = document.getElementById('post');
      $div.dataset.comments = '10';
      $div.dataset.countryLangInfo = 'ko'; //data-country-lang-info 로 저장    
      ```
  3. 일반적인 속성 변경 메서드 setAttribute() 사용
      ```
      const $div = document.getElementById('post');
      $div.setAttribute('data-comments', '10')
      $div.setAttribute('data-country-lang-info', 'ko')
      ```
<br>

- **데이터셋 삭제하기**    
  1. delete 키워드로 객체 속성 삭제         
  2. 일반적인 속성 제거 메서드 removeAttribute() 사용
   
      ```
      const $div = document.getElementById('post');
      delete $div.dataset.title; // delete 키워드로 객체 속성 삭제
      $div.removeAttribute('data-comments');
      ``` 

<br>    

- **데이터셋 리스트 출력**    
자바스크립트는 DOM 생성 시점에 data- 로 시작하는 속성들을 하나로 모아 dataset 맵(Map)을 만들어 관리한다. 위처럼 데이터셋 속성을 하나씩 출력해 확인할 수도 있지만, .dataset 프로퍼티 자체를 접근하면 아래 처럼 데이터셋 관련 모든 속성 리스트 출력이 가능    
```
 console.log(event.target.dataset);
```


## 학습출처
**유튜브**    
https://www.youtube.com/@JavaScriptKing    

**JS**    
https://inpa.tistory.com/entry/JS-%F0%9F%93%9A-HTML-%EB%8D%B0%EC%9D%B4%ED%84%B0%EC%85%8Bdata-%EC%86%8D%EC%84%B1      
https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/dataset      
https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes    
https://www.w3schools.com/tags/att_data-.asp       
