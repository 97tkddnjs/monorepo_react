# monorepo_react
reacte monorepo test


## monorepo 프로젝트 구조

## 1. monorepo 폴더 초기화 필요
cmd 에 다음 명령어

```bash

mkdir react-monorepo
cd react-monorepo

pnpm init
```

## 2. 이후 monorepo 폴더에 pnpm-workspace.yaml 만들기

내용

pnpm이 어떤 폴더들을 관리할지 정의하는 파일입니다. 여기에서는 packages/ 하위의 모든 프로젝트를 workspace로 설정


```yaml

packages:
  - 'packages/*'
```

## 3. 각각 플젝 만들기

### 3-1 vite

```bash
pnpm create vite packages/react-vite-app --template react
```

### 3-2 webpack 만들기

```bash
mkdir packages/react-webpack-app
cd packages/react-webpack-app
pnpm init

pnpm add react react-dom
pnpm add -D webpack webpack-cli webpack-dev-server babel-loader @babel/core @babel/preset-react html-webpack-plugin

```

내부 소스는 CRA 옮긴 것임


## 4 각각 환경에서 빌드

### 4-1 vite
```bash
pnpm --filter react-vite-app dev
```

### 4-2 webpack
```bash
pnpm --filter react-webpack-app dev
```