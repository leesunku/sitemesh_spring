# spring 에서 sitemesh 적용하는 방법

### 1. pom.xml 설정
##### dependency 추가, groupId opensymphony , artifactId sitemesh , version 2.4.2

### 2. web.xml 환경 설정
##### context-param
##### param-name - sitemesh.configfile
##### param-value - /WEB-INF/sitemeshConfig/sitemesh.xml
##### 설명
##### sitemesh.xml 설정파일의 위치지정

##### filter name - sitemesh
##### filter class - com.opensymphony.module.sitemesh.filter.PageFilter
##### url-pattern - /*
##### 설명
##### http://localhost:8080 을 입력하면, /* 
##### (/는 controller로 지정된 java 파일을 찾아가는 것) 
##### (\*는 /index.html, /index, /aaa, /bbb 같이 /뒤에  '*' 모든 것을 의미)
##### 를 sitemesh의 형태로 표현하게 하는 설정

### 3. sitemesh.xml 작성
##### property
##### name - decorators-file
##### value - /WEB-INF/sitemeshConfig/decorators.xml
##### 설명
##### decorators.xml 위치 지정

##### excludes
##### file - ${decorators-file}
##### 설명
##### sitemesh를 사용하지 않을 페이지 지정
##### 데코레이터 파일에 설정하기 위한 매핑

##### decorator-mappers
##### mapper class - com.opensymphony.module.sitemesh.mapper.ConfigDecoratorMapper
##### params name - config, value - ${decorators-file}
##### 설명
##### 데코레이터 설정 맵핑

### 4. decorators.xml 작성
##### decorators defaultdir - /decorators
##### excludes
##### pattern - *.json
##### 설명
##### excludes는 sitemesh를 사용하지 않을 페이지 지정

##### decorator
##### name - layout
##### page - /WEB-INF/layout/layout.jsp
##### pattern - /*
##### 설명
##### layout.jsp를 레이아웃 페이지로 지정

### 마지막으로 layout.jsp를 작성
##### title에, decorator:title default="test" 라는 테그를 넣으면 각 페이지마다 title명을 각 페이지에서 지정가능
##### decorator:head는 head에 넣을 css나 js를 각 페이지의 헤더에서 지정가능
##### body태그 안에 레이아웃을 그리고 페이지별로 변환 시킬 부분을 decorator:body에 지정

### 나머지 설명은 코드를 보아야 이해가 쉬움
