# [React-Native-TodoApp]()

:point_up_2: 제목을 클릭하면 배포된 사이트를 확인하실 수 있습니다.

<br />

## :pencil2: 학습 목적

- React-Native를 활용하여 TODO앱 구현하기.

<br />

## 🛠️ Stacks

<img src="https://img.shields.io/badge/ReactNative-61DAFB?style=flat-round&logo=react&logoColor=white"/> <img src="https://img.shields.io/badge/Expo-000020?style=flat-round&logo=expo&logoColor=white"/>

<br />

## :book: 학습 내용

### 🔆 React-Native란?

> 📃 Docs: [React-Native APIs](https://reactnative.dev/docs/accessibilityinfo)

- 페이스북이 개발한 오픈 소스 모바일 애플리케이션 프레임워크. Android, ios 등 애플리케이션을 개발하기 위해 사용되며, 개발자들이 네이티브 플랫폼 기능과 더불어 리액트를 사용할 수 있습니다.
- 가상 DOM을 통해 DOM을 조작하지 않는다는 점을 제외하고는 리액트와 실질적으로 동일합니다.
- 개발자가 작성한 JavaScript를 해석하는 백그라운드 프로세스입니다.

### 🔆 프로젝트 생성

#### 1. expo 전역 설치

> ❗Java, Xcode를 설치하지 않고 즉시 코드를 테스트하기 위해서 expo를 설치합니다. 모바일에도 expo앱을 설치합니다.

```
npm i -g expo-cli
```

> ❗MacOS의 경우 [watchman](https://facebook.github.io/watchman/docs/install#buildinstall)을 추가로 설치합니다.

```
brew update
brew install watchman
```

#### 2. 프로젝트 생성

```
expo init [프로젝트명]
```

#### 3. 프로젝트 실행

```
cd <프로젝트 폴더명>
npm start or expo start --tunnel
```

### 🔆 유용한 사이트

- [Expo icons](https://icons.expo.fyi/)
  - 해당 사이트에서 아이콘을 클릭한 후, 디테일 페이지를 확인하여 아이콘을 프로젝트에 적용합니다.

  ```
  ex)
  import {Fontisto} from '@expo/vector-icons'

  <Fontisto name="wind" size={25} color="black" />
  ```