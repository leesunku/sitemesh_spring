# spring 에서 sitemesh 적용하는 방법

### 1. pom.xml 설정
##### dependency 추가, groupId opensymphony , artifactId sitemesh , version 2.4.2

### 2. web.xml 환경 설정
##### filter name - sitemesh
##### filter class - com.opensymphony.module.sitemesh.filter.PageFilter
##### url-pattern - /*
##### 설명
##### http://localhost:8080 을 입력하면, /* 
##### (/는 controller로 지정된 java 파일을 찾아가는 것) 
##### (\*는 /index.html, /index, /aaa, /bbb 같이 /뒤에  '*' 모든 것을 의미)
##### 를 sitemesh의 형태로 표현하게 하는 설정
