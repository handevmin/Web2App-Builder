# Web2App-Builder
기존 웹 사이트를 react-native와 webView를 이용하여 앱으로 변환해줍니다.  

<br>

## 이용방법  

### 1. web뷰 앱을 만들기 위한 리액트 설치

```jsx
expo install react-native-webview
// 그냥 npm install 하셔도 됩니다
```

### 2. 원하는 웹사이트 주소 등록

```jsx
// app.js
uri: 'https://expo.io' → 자신의 URI
```

### 3. 앱 출시 정보 수정

```jsx
// app.json
{
	"expo": {
		"name": "앱 아이콘 밑에 표시될 이름",
		"slug": "프로젝트명",
		...
	"ios": { 
		"supportsTablet": true,
		"bundleIdentifier": "com.회사이름.앱이름",
		"buildNumber": "1.0.0" 
	},
	"android": {
		"package": "com.회사이름.앱이름",
		"versionCode": 1
} 
```

참고: slug 에는 "^[a-zA-Z0-9_\-]+$" 이외 사용이 불가능함

### 4. 아이콘, 스플래쉬 이미지 변경

asset폴더 안의 icon(1024*1024), splash(1242*2436) 이미지를 같은 크기의 원하는 이미지로 변경

### 5. app build 및 출시

1) app build

```jsx
npm install -g expo-cli
```

2) .expo폴더 삭제 // 오류 방지 차원

3) 안드로이드 abb (apk의 새로운 버전) 출시

```jsx
 expo build:android
```

빌드를 하기 위해서는 expo 계정이 필요하다. 없으면 "Make a new Expo account"를 선택해서 새로 만들어 줍니다.

빌드과정에서 Keystone 관리를 어디서 할거냐는 메세지가 뜨면 특이사항 없으면 그냥 Expo가 하도록 맡겨줍니다.

4) 안드로이드 번들 출시 

```jsx
expo build:android -t app-bundle
```
