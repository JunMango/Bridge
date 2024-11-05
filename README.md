<!-- @format -->

# 졸업 논문
## 클라우드 전자칠판_saas
졸업 논문으로 클라우드의 전자 칠판의 개발과 배포를 통해 클라우드 공동 판서의 인프라에 대해서 연구 하기 위한 프로젝트 입니다.
아키텍쳐 구조는 google Docs, JamBoard를 벤치마킹 하였습니다.
공동 문서 작업은 pdf를 옮겨 가면서 통신하면 pdf를 교환하는 과정에서 여러 매우 비효율적이기 때문에 pdf를 직접 교환하는 방법을 사용하지 않았습니다.
공유 판서의 권한이 있는 사람들끼리만 특정 페이지를 제공한후에 통신을 하는 구조를 가지게 할것입니다.
특정 url은 해시값을 생성하고 서버에서 검증하는 형식으로 각 유저의 권한을 확인하는 형식으로 접근이 가능하게 합니다.

###  10.11
지우개를 구현 하였습니다.

![10 11 개발 사진](https://github.com/user-attachments/assets/77a2aafa-ab5a-4574-9167-a3df51183c92)

### 10.14
파일 트리 구조를 레퍼런스에서 가져와서 업데이트를 하였다. ps. React의 FSD 구조를 적용 할까 고민중

![10 14 개발 사진](https://github.com/user-attachments/assets/4f5f62b1-bfd5-4417-9546-6ea1e71897f1)

### 10.24 ~ 11.04
중간고사 이후로 작업분기가 완벽하지 못하여 저의 컴퓨터 local git에 하위 브랜치로만 있다가 이제서야 github으로 업데이트를 합니다.
구글 로그인 기능을 구현하였습니다
* 공용판서로서 가장 중요한것 중 하나가 로그인이고 어떻게 유저 정보와 각 판서들을 관리하는 방법이라고 생각합니다.각 어플리케이션 마다의 차이는 있겠지만 이번 프로젝트에서 개별적으로 유저를 구분하는 방법은 google 로그인 후 user.id를 사용하였습니다.
```
{id: "101573265873198117667", email: "gudwns4985@gmail.com", verified_email: true,…}
email
: 
"gudwns4985@gmail.com"
family_name
: 
"KIM"
given_name
: 
"HyungJun"
id
: 
"101573265873198117667"
name
: 
"HyungJun KIM"
picture
: 
"https://lh3.googleusercontent.com/a/ACg8ocLeXBpHuV1Cn-BxNlGx9uUWSR489b4ozR8bkX9I8c8-PcQl-Q=s96-c"
verified_email
: 
true
```
<img width="1728" alt="스크린샷 2024-11-04 오후 3 22 26" src="https://github.com/user-attachments/assets/904f8681-a90f-46d9-add9-ebf895f5e5de">
<img width="1728" alt="스크린샷 2024-11-04 오후 3 22 34" src="https://github.com/user-attachments/assets/92b5b40c-2bc7-494f-af1a-355ec020551e">
<img width="1728" alt="스크린샷 2024-11-04 오후 3 22 45" src="https://github.com/user-attachments/assets/15c950fc-a771-4c3b-8303-6bd922513e32">
다음과 같이 라우팅을 나누었다.
**user/:id** 이후로 note list 와 group list 그리고 각 판서마다 객체번호를 부여하여 인가 과정을 거치는 작업을 서버에서 구현 할것이다.

### 11.05
- 빠른 프로젝트를 위해서 Tailwind Mui를 적용하였다. 기존의 Flowbite를 지우고 좀더 컴포넌트가 풍부한 Tailwind를 프로젝트에 넣으면서 여러 의존성이 겹쳐서 그것을 해결하는데 애를 먹었다. 
Tailwind MUI를 설치하고 나서 라이브러리 자체에서 사용하는 useContext에 대한 오류를 찾기 위해 Tailwind MUI 레포지토리를 찾아보고 오류를 해결하였다. 이유는 버전의오류였는데 최근 react 18.3.1로 업데이트 되면서 약간의 간섭이 생긴것 같다 오류는 다음과 같이 해결했다.
```
"overrides": {
    "react": "^18.3.1",
    "react-dom": "^18.3.1"
  },
```
pagkage.json 에 다음과 같이 의존성을 추가하면된다.

- 로그인후 user를 위한 SideBar를 추가 하였다. 여기에는 user의 노트들과 공유 되어 있는 노트 및 그룹들이 표시될 예정이다.
<img width="1711" alt="스크린샷 2024-11-05 오후 6 16 51" src="https://github.com/user-attachments/assets/be01da7c-52ec-4f68-9bd2-67f1e62b146c">
