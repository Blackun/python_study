# 4.2 크롤러를 만들 때 주의해야 하는 것

크롤러를 매우 빼른 속도로 돌려 상대방 사이트에 너무 많은 부하를 주면 업무 방해등으로 고소를 당할 수 있습니다.

## robots.txt 로 크롤러에게 지시하기

* robots.txt : 웹사이트 최상위 디렉터리에 배치돼 있는 텍스트 파일
  * User-agent : 디렉티브 정보의 대상이 되는 크롤러를 나타냅니다.
  * Disallow : 크롤링을 거부할 경로를 나타냅니다.
  * Allow : 크롤링을 허가할 경로를 나타냅니다.
  * Sitemap : XML 사이트 맵의 URL을 나타냅니다.
  * Crawl-delay : 크롤러의 간격을 나타냅니다.
* robots.txt 파싱하기
  * 파이썬 표준 라이브러리인 urllib.robotparser 사용
* robots meta 태

## XML사이트

크롤러에게 크롤링해도 괜찮은 URL목록을 제공하기 위한 XML 파일

## 크롤링 대상에 대한 부하

현대 웹 브라우저는 한 호스트에 최대 6개의 동시 접속을 허용. 크롤러는 이것보다 적게 동시접속을 거는 게 좋음

동시 접속수가 1이라도 시간간격을 두고 연속적으로 웹 페이지를 추출 하여야 함\(1초 이상을 권장\)



## 연락처 명시하기



## 상태 코드와 오류 처리

* HTTP 통신 오류 분류
  * 네트워크 레벨의 오류
  * HTTP 레벨의 오류
* HTTP 통신 오류 대처 방법
  * 시간을 두고 재시도\(재시도 간격은 지수함수적으로, 1초, 2초, 4초, 8초 ..\)
  * 해당 페이지를 포기
* 파이썬에서 오류 처리하


