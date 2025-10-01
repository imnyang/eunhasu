# 🌌 Eunhasu

Eunhasu[ɯn.ɦa.su]는 한국어로 "은하수"를 의미하는 단어입니다.

## 개요

은하수는 [imnya.ng](https://imnya.ng)의 React UI 컴포넌트 라이브러리로, Next.js 애플리케이션에 최적화된 UI 컴포넌트들을 제공합니다.

React, Next.js를 지원하고 있습니다.

MIT 라이선스에 따라 자유롭게 사용, 수정, 배포할 수 있습니다.

## 설치

```bash
npm install @imnyang/ui
# or
yarn add @imnyang/ui
# or
pnpm add @imnyang/ui
# or
bun add @imnyang/ui
```

## 사용법

### Button 컴포넌트

```tsx
import { Button } from '@imnyang/ui';

function App() {
  return (
    <Button 
      primary 
      size="medium" 
      label="Click me" 
      onClick={() => console.log('Button clicked!')}
    />
  );
}
```

### Header 컴포넌트

```tsx
import { Header } from '@imnyang/ui';

function App() {
  const user = { name: 'John Doe' };
  
  return (
    <Header
      user={user}
      onLogin={() => console.log('Login')}
      onLogout={() => console.log('Logout')}
      onCreateAccount={() => console.log('Create Account')}
    />
  );
}
```

### 스타일 가져오기

컴포넌트의 스타일을 사용하려면 CSS 파일을 가져와야 합니다:

```tsx
import '@imnyang/ui/styles';
```

또는 Next.js의 `_app.tsx`에서:

```tsx
import '@imnyang/ui/styles';
import type { AppProps } from 'next/app';

export default function App({ Component, pageProps }: AppProps) {
  return <Component {...pageProps} />;
}
```

## API

### Button Props

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| `primary` | `boolean` | `false` | 기본 버튼 스타일 여부 |
| `backgroundColor` | `string` | - | 배경색 |
| `size` | `'small' \| 'medium' \| 'large'` | `'medium'` | 버튼 크기 |
| `label` | `string` | - | 버튼 텍스트 |
| `onClick` | `() => void` | - | 클릭 이벤트 핸들러 |

### Header Props

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| `user` | `{ name: string }` | - | 사용자 정보 |
| `onLogin` | `() => void` | - | 로그인 버튼 클릭 핸들러 |
| `onLogout` | `() => void` | - | 로그아웃 버튼 클릭 핸들러 |
| `onCreateAccount` | `() => void` | - | 계정 생성 버튼 클릭 핸들러 |

## 개발

### Storybook으로 컴포넌트 확인

```bash
npm run storybook
```

### 빌드

```bash
npm run build
```

### 테스트

```bash
npm run test
```

## 배포

이 패키지는 GitHub Actions를 통해 자동으로 배포됩니다.

### 자동 배포 (권장)

1. 변경사항을 main 브랜치에 커밋
2. 버전 태그 생성 및 푸시:
   ```bash
   npm version patch  # 또는 minor, major
   git push origin main --tags
   ```
3. GitHub Actions가 자동으로 빌드하고 npm에 배포

### 수동 배포

로컬에서 직접 배포하려면:

```bash
npm run build
npm publish --access public
```

**참고**: GitHub Actions를 사용하려면 GitHub repository의 Secrets에 `NPM_TOKEN`을 설정해야 합니다.

## 라이선스

MIT License - 자세한 내용은 [LICENSE](LICENSE) 파일을 참조하세요.