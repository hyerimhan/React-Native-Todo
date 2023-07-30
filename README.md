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

### 🔆 Components

#### Touchables

1. TouchableOpacity

- 누르는 이벤트를 listen할 준비가 된 애니메이션 효과가 있는 `View`와 비슷한 컴포넌트입니다.
- 클릭시 해당 컴포넌트가 약간 투명해지는 효과가 있습니다.
  - `activeOpacity` - 해당 컴포넌트 투명도 조절
  - `onPress` - 사용자가 Touchable을 눌렀을때 실행되는 이벤트

```JavaScript
import { TouchableOpacity } from 'react-native'
<TouchableOpacity activeOpacity={0} onPress={()=>console.log("press")}>...</TouchableOpacity>
```

2. TouchableHightlight

- 누르는 이벤트를 listen할 준비가 된 애니메이션 효과가 있는 `View`와 비슷한 컴포넌트입니다.
- 클릭시 해당 컴포넌트의 배경에 효과를 줍니다.
  - `activeOpacity` - 해당 컴포넌트 투명도 조절
  - `onPress` - 사용자가 Touchable을 눌렀을때 실행되는 이벤트
  - `underlayColor` - 클릭 시 배경색 변경, `onPress`와 함께 사용

```JavaScript
import { TouchableHightlight } from 'react-native'
<TouchableHightlight activeOpacity={0} onPress={()=>console.log("press")} underlayColor="#ddd">...</TouchableHightlight>
```

3. TouchableWithoutFeedback

- 그래픽이나 다른 UI 반응없이 화면의 가장 위에서 일어나는 탭 이벤트를 listen하는 컴포넌트
  - `onPress` - 사용자가 Touchable을 눌렀을때 실행되는 이벤트

```JavaScript
import { TouchableWithoutFeedback } from 'react-native'
<TouchableWithoutFeedback onPress={()=>console.log("press")}>...</TouchableWithoutFeedback>
```

4. Pressable

- 비교적 최근에 나온 컴포넌트입니다.
- 위의 컴포넌트들과 비슷하지만 보다 좀 더 상세하게 설정할 수 있습니다.
  - `delayLongPress` - 얼마나 길게 누르면 반응하게 할지 설정
  - `disabled` - 비활성화 여부 설정
  - `hitSlop` - 해당 요소 바깥 어디까지 탭 누르는 것을 감지할지 설정

```JavaScript
import { Pressable } from 'react-native'
<Pressable delayLongPress={500} disabled={false} hitSlop={{ top: 15, right: 15, bottom: 15, left: 15 }}>...</Pressable>
```
