---
title:  "Google Cloud Platform 무료서버를 가져가보자"
toc: true
date: 2022-04-10 22:38:07
tags:
- aws
- project
categories: google
---

<style>
 img{
	 border-radius: 5px;
 }

</style>


# 목적
Google Cloud Platform 에서 제공하는 1년치 인스턴스를 제외하고, 무료로 서버를 받는 방법을 알아보자!

## 사용방법
> 무료로 사용하기 위해서는 다음 조건을 충족을 해야한다 - 해당 리전과, 용량을 지정해서 사용할 것


<img src="https://user-images.githubusercontent.com/45492520/89964158-59e20580-dc84-11ea-8f0a-5545f57b3937.png" width=50%>


## 경로 및 설정 방법

<!-- <img src="https://user-images.githubusercontent.com/45492520/89963037-7b8dbd80-dc81-11ea-83ae-bb8e476ec597.png" width=40%> -->

(1) [구글 클라우드 플랫폼](https://cloud.google.com/free?hl=ko) 홈페이지 접속<br>
(2) 메인 화면의 [[무료로 시작하기](https://console.cloud.google.com/freetrial/signup/tos?hl=ko&_ga=2.12091890.778630772.1597133095-287812363.1597133095&_gac=1.170650260.1597133169.EAIaIQobChMIz8m8s9iS6wIVUqmWCh3RsgffEAAYASAAEgI8X_D_BwE)] 클릭 <br>
(3) 계정 및 결제정보 입력 후 접속<br>

<img src="https://user-images.githubusercontent.com/45492520/89982363-8ca1f300-dcb0-11ea-9218-af59268b35a7.png" width=50%>

(4) [햄버거 메뉴] - [Compute Engine] - [VM인스턴스] 이동<br>
(5) [만들기] 클릭 후 <b>다음과 같이 설정을 한다.</b><br>
   - 리전은 국가 3개 중 하나 선택(오리건, 아이오와, 사우스캐롤라이나), 영역은 아무거나
   - 시리즈는 N1(냅둬도됨), 머신은 f1-micro
   - 부팅디스크는 원하는거 선택, 안에 용량은 표준에 30GB안에서 선택
   - 엑세스 범위는 모든 클라우스 api 허용, 방화벽 모두 체크


<img src="https://user-images.githubusercontent.com/45492520/89982935-99731680-dcb1-11ea-9d40-326eb3a39402.png" width=50%>

> 지정 완료 후 월별 예상금액이 나오는데, 설정만 잘 해줬을 경우 큰 문제없이 과금이 되지 않을 것이다.

## 결과 화면
> [VM 인스턴스] 페이지에서 결과된 모습을 보고, 표시된 [SSH] 연결 버튼도 눌러보자
 
<img src="https://user-images.githubusercontent.com/45492520/89987806-967c2400-dcb9-11ea-88c1-41532e3568c0.png" width=60%>



## 다른 기기에서 서버로 접속을 해보자
>  mac 기준 key 만들기
```
$ cat ~/.ssh/id_rsa.pub // 키 있나 보기
$ cd ~/.ssh //  없으면 이동 후
$ ssh-keygen // 키 생성
```
> 키 값 집어넣기
1. [메타데이터] - [SSH 탭] 에서 키 추가 


> 아이피 고정 설정하기

<img src="https://user-images.githubusercontent.com/45492520/89992088-badaff00-dcbf-11ea-890d-c7b9866e862d.png" width=60%>


1. [해당 옆 추가메뉴] - [네트워크 세부설정 보기] 후 왼쪽 메뉴에 [외부 IP 주소] 클릭 
2. 해당 아이피 유형을 고정으로 변경

> 최종 연결
```
$ ssh [등록된 key 이름]@[클라우드 아이피 주소]
```
<!-- <img src="https://user-images.githubusercontent.com/45492520/89992445-3fc61880-dcc0-11ea-817e-116c8fa85d5d.png" width=40%> -->
<img src="https://user-images.githubusercontent.com/45492520/89992445-3fc61880-dcc0-11ea-817e-116c8fa85d5d.png" width=40%>




