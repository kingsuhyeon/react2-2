# 201930109 노수현 

## 2024년 11월 20일 강의 내용

### **`use client`란?**
- Next.js 13에서 도입된 새로운 지시어로, 컴포넌트가 클라이언트 사이드에서만 렌더링된다는 것을 명시.

### **`use client`의 주요 특징과 사용 이유**
1. **동적 데이터와 상호작용**  
   - 실시간 채팅, 동적 폼 검증, 클라이언트 사이드에서만 가능한 계산이나 데이터 처리에 적합.
2. **브라우저 API 접근**  
   - `window`, `navigator`와 같은 브라우저 전용 API에 접근 가능.
3. **성능 최적화**  
   - 초기 페이지 로드 시 필요하지 않은 리소스의 로딩을 방지하며, 서버 부담을 줄이고 성능 최적화.

### **주요 디렉토리 및 파일**
- **`app`**: 라우팅 및 페이지 관리.
- **`components`**: 재사용 가능한 공통 컴포넌트 관리.
- **`features`**: 재사용 불가능하거나 수정이 많은 컴포넌트 관리.
- **`context`**: 기능별 상태 관리 컴포넌트 관리.
- **`store`**: Redux store 설정 파일 관리.
- **`styles`**: CSS, Sass 등 스타일 파일 관리.

---

## **Redux**

### **Slice**
- Redux Toolkit에서 사용하는 개념으로, 특정 기능에 관련된 상태와 리듀서를 한 곳에서 정의.

### **Provider**
- Redux 상태를 공급하는 컴포넌트.
- 특정 페이지에서 사용하는 경우 해당 페이지에, 전역적으로 사용할 경우 `layout` 파일에 정의하거나 별도의 컴포넌트로 분리.

---

## **Context API와 Redux 비교**

### **Context API**
- **특징**: React 기본 제공 상태 관리 도구. 외부 라이브러리 설치 불필요.
- **장점**: 간단하고 React에 내장된 상태 관리 방식.
- **단점**: 복잡한 상태 관리에는 적합하지 않음. 상태 트리가 깊을 경우 성능 저하.

### **Redux**
- **특징**: 독립적인 상태 관리 라이브러리. 상태를 구조적으로 관리.
- **장점**:
  - 명확한 상태 관리 구조 제공.
  - 미들웨어 및 디버깅 도구 지원.
  - 다양한 프레임워크와 호환 가능.
- **단점**:
  - 설정 복잡도 증가.
  - 작은 애플리케이션에는 과도한 설정.

---

## 2024년 11월 13일 강의 내용

### **Props 흐름의 이해**
- **데이터 흐름**: Next.js의 데이터 흐름은 단방향. 부모 → 자식 방향으로 전달.
- **Props Drilling 문제**:
  - 중간 컴포넌트에 불필요한 props 전달.
  - 타겟 컴포넌트까지 전달되지 않을 경우 디버깅 어려움.
  - 복잡한 코드로 인해 유지보수 어려움.
- **해결 방법**: Context API를 사용하여 전역적으로 props 관리.

---

## 2024년 11월 6일 강의 내용

### **UI 라이브러리**
- 필수는 아니지만 생산성을 높이고 UI 일관성을 유지하는 데 도움.
- **대표적인 라이브러리**:
  - Chakra UI
  - Tailwind CSS
  - Headless UI

#### **Chakra UI**
- 오픈소스 컴포넌트 라이브러리.
- 접근성과 모듈성이 뛰어나며 Dark/Light 모드 지원.
- 다양한 내장 컴포넌트를 제공하며 기본 컴포넌트 조합으로 새로운 컴포넌트를 생성 가능.

#### **Tailwind CSS**
- CSS 규칙만 제공하며 자유도가 높음.
- 빌드 시 사용하지 않는 클래스 제거 → 최적화.
- Dark/Light 모드 간단 적용 가능.

#### **Headless UI**
- Tailwind Labs의 프로젝트.
- CSS 클래스 대신 동적 컴포넌트 제공.

#### **설치**
1. `npx create-next-app@14`
2. 모든 질문에 "YES" 응답.

---

## 2024년 10월 30일 강의 내용

### **Style JSX**
- **CSS-in-JS 라이브러리**: 내장 모듈로 설치 불필요.
- **단점**:
  - IDE 지원 부족(문법 하이라이팅, 자동 완성 미흡).
  - 번들 크기 증가로 성능 저하.

### **CSS Module**
- Style JSX 단점을 보완.
- `.module.css` 확장자로 CSS 클래스를 자바스크립트 객체로 변환하여 사용.
- CSS 클래스의 이름 충돌을 방지하고 모듈화된 스타일 제공.
