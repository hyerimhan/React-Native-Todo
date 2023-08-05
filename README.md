# [React-Native-TodoApp](https://expo.dev/@beiie/whtApp)

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

### 🔆 사용한 라이브러리

- [Expo icons](https://icons.expo.fyi/)

  - 해당 사이트에서 아이콘을 클릭한 후, 디테일 페이지를 확인하여 아이콘을 프로젝트에 적용합니다.

  ```
  ex)
  import {Fontisto} from '@expo/vector-icons'

  <Fontisto name="wind" size={25} color="black" />

  ```

### 🔆 Components

#### Touchables

- [TouchableOpacity](https://reactnative.dev/docs/touchableopacity)

  - 누르는 이벤트를 listen할 준비가 된 애니메이션 효과가 있는 `View`와 비슷한 컴포넌트입니다.
  - 클릭시 해당 컴포넌트가 약간 투명해지는 효과가 있습니다.
    - `activeOpacity` - 해당 컴포넌트 투명도 조절
    - `onPress` - 사용자가 Touchable을 눌렀을때 실행되는 이벤트

  ```JavaScript
  import { TouchableOpacity } from 'react-native'

  <TouchableOpacity activeOpacity={0} onPress={()=>console.log("press")}>...</TouchableOpacity>
  ```

- [TouchableHightlight](https://reactnative.dev/docs/touchablehighlight)

  - 누르는 이벤트를 listen할 준비가 된 애니메이션 효과가 있는 `View`와 비슷한 컴포넌트입니다.
  - 클릭시 해당 컴포넌트의 배경에 효과를 줍니다.
    - `activeOpacity` - 해당 컴포넌트 투명도 조절
    - `onPress` - 사용자가 Touchable을 눌렀을때 실행되는 이벤트
    - `underlayColor` - 클릭 시 배경색 변경, `onPress`와 함께 사용

  ```JavaScript
  import { TouchableHightlight } from 'react-native'

  <TouchableHightlight activeOpacity={0} onPress={()=>console.log("press")} underlayColor="#ddd">...</TouchableHightlight>
  ```

- [TouchableWithoutFeedback](https://reactnative.dev/docs/touchablewithoutfeedback)

  - 그래픽이나 다른 UI 반응없이 화면의 가장 위에서 일어나는 탭 이벤트를 listen하는 컴포넌트
    - `onPress` - 사용자가 Touchable을 눌렀을때 실행되는 이벤트

  ```JavaScript
  import { TouchableWithoutFeedback } from 'react-native'

  <TouchableWithoutFeedback onPress={()=>console.log("press")}>...</TouchableWithoutFeedback>
  ```

- [Pressable](https://reactnative.dev/docs/pressable)

  - 비교적 최근에 나온 컴포넌트입니다.
  - 위의 컴포넌트들과 비슷하지만 보다 좀 더 상세하게 설정할 수 있습니다.
    - `delayLongPress` - 얼마나 길게 누르면 반응하게 할지 설정
    - `disabled` - 비활성화 여부 설정
    - `hitSlop` - 해당 요소 바깥 어디까지 탭 누르는 것을 감지할지 설정

  ```JavaScript
  import { Pressable } from 'react-native'

  <Pressable delayLongPress={500} disabled={false} hitSlop={{ top: 15, right: 15, bottom: 15, left: 15 }}>...</Pressable>
  ```

#### [TextInput](https://reactnative.dev/docs/textinput)

- `input`과 `textarea` 태그를 아울러 사용할 수 있습니다.

  - `onChangeText` - 사용자가 입력하는 Text를 받을 수 있습니다.
  - [`keyboardType`](https://reactnative.dev/docs/textinput#keyboardtype) - 상황에 따른 키보드 타입을 바꿀 수 있게 설정할 수 있습니다.
    - number-pad, email-address, phone-pad 등과 함께 사용합니다.
  - `returnKeyType` - "Enter" 키의 기능을 변경할 수 있습니다.
    - `returnKeyLable` - 안드로이드에서만 작동. "Enter" 키의 이름을 변경할 수 있습니다.
  - `secureTextEntry` - 비밀번호를 입력할 때 입력하는 비밀번호가 보이지 않습니다.
    - `<input type="password" />`와 동일합니다.
  - `multiline` - 여러 내용의 글을 입력할 수 있습니다.
    - `<input type="textarea" />`와 동일합니다.
  - `placeholderTextColor` - placeholder의 텍스트 색을 변경합니다.
  - `onSubmitEditing` - 사용자가 키보드의 "확인(Enter)" 버튼 누르는 것을 감지.

```JavaScript
import { TextInput } from 'react-native'

<TextInput keyboardType="number-pad" returnKeyType="done" onSubmitEditing={addTodo}>...</TextInput>
```

#### [ScrollView](https://reactnative.dev/docs/scrollview)

- 해당 영역에만 Scroll이 적용됩니다.
- CSS의 `overflow: auto`와 비슷합니다.

```JavaScript
import { ScrollView } from 'react-native'

<ScrollView>...</ScrollView>
```

### 🔆 APIs

#### [Alert](https://reactnative.dev/docs/alert)

- 확인 팝업창을 띄웁니다.
  - `text`: 취소 / 확인 버튼을 생성할 수 있습니다.
  - `onPress`: 버튼 클릭 후, 실행될 로직을 작성합니다.

```JavaScript
  const deleteTodo = (key) => {
    Alert.alert('Delete Todo', 'Are you sure?', [
      { text: 'Cancel' },
      {
        text: "I'm Sure",
        onPress: () => {
          const newTodos = { ...todos }
          delete newTodos[key]
          setTodos(newTodos)
          saveTodos(newTodos)
        },
      },
    ])
  }
```

#### [Platform](https://reactnative.dev/docs/platform)

- 플랫폼 OS를 체크합니다.
  - android, ios, macos, web, windows 가 내장되어 있습니다.

```JavaScript
import { Platform } from 'react-native';

  const deleteTodo = (key) => {
    if (Platform.OS === 'web') {
      // ...
    }
  }
```

### 🔆 사용한 라이브러리

#### [AsyncStorage](https://docs.expo.dev/versions/latest/sdk/async-storage/)

- `AsyncStorage`는 `localStorage`와 비슷한 역할입니다.
- 현재 사용중인 expo 버전과 같은 버전의 모듈을 설치(사용 가능한 버전)하기 위해 `expo install`을 사용합니다.

```
expo install @react-native-async-storage/async-storage
```

- set
  - 데이터를 저장합니다.

```JavaScript
import AsyncStorage from '@react-native-async-storage/async-storage';

// Storing string value
const storeData = async (value) => {
  try {
    await AsyncStorage.setItem('my-key', value);
  } catch (e) {
    // saving error
  }
};

// Storing object value
const storeData = async (value) => {
  try {
    const jsonValue = JSON.stringify(value);
    await AsyncStorage.setItem('my-key', jsonValue);
  } catch (e) {
    // saving error
  }
};
```

- get
  - 저장한 데이터를 가져옵니다.

```JavaScript
// Reading string value
const getData = async () => {
  try {
    const value = await AsyncStorage.getItem('my-key');
    if (value !== null) {
      // value previously stored
    }
  } catch (e) {
    // error reading value
  }
};

// Reading object value
const getData = async () => {
  try {
    const jsonValue = await AsyncStorage.getItem('my-key');
    return jsonValue != null ? JSON.parse(jsonValue) : null;
  } catch (e) {
    // error reading value
  }
};
```

### 🔆 빌드

```
npm install -g eas-cli
```

- app store에 보낼 수 있도록 만들어 줍니다.
- 컴퓨터에서 만들어지는 것이 아니라 expo 서버에서 이루어지기 때문에 window에서도 ios앱을 개발할 수 있습니다.

```
eas build -p android or eas build -p ios
```
