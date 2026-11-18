# Todo Tutorial

[Claude Code Playbook](https://docs.claude-hunt.com) 강의에서 작은 할 일 앱을 직접 만들어 보며 Claude Code 쓰는 법을 배우는 연습용 저장소입니다.

## 관련 링크

- 강의 본문: https://docs.claude-hunt.com
- 수강생 결과물 공유: https://claude-hunt.com

## 기술 스택

- Next.js 16 (App Router, Turbopack)
- React 19
- Tailwind CSS v4
- shadcn/ui (radix-maia 스타일, taupe 베이스)
- TypeScript / ESLint / Prettier
- 패키지 매니저: bun 1.3.6

## 시작하기

### 준비물

- [Git](https://git-scm.com)
- [bun](https://bun.sh) 1.3.6 이상 (패키지 매니저 겸 스크립트 실행기)
- [Node.js](https://nodejs.org) (Next.js 실행에 필요)

```bash
bun -v   # 버전이 출력되는지 확인
```

### 설치와 실행

```bash
git clone https://github.com/CamelGoong/todo-tutorial.git
cd todo-tutorial
bun install   # 의존성 설치
bun dev       # 개발 서버 실행
```

개발 서버는 기본적으로 [http://localhost:3000](http://localhost:3000) 에서 열립니다. 종료는 터미널에서 `Ctrl+C` 입니다.

### 프로덕션 빌드로 실행

```bash
bun run build   # 프로덕션 빌드
bun run start   # 빌드 결과 실행 (http://localhost:3000)
```

### 검사와 테스트

```bash
bun run typecheck  # 타입 검사 (tsc --noEmit)
bun run lint       # ESLint
bun run test       # 테스트 (Vitest, 1회 실행)
bun run format     # Prettier 포맷팅
```

`bun run test`에서 `Worker exited unexpectedly`나 `out of memory` 오류로 테스트가 시작되지 않으면 스레드 방식으로 실행해 보세요. (최신 Node.js에서 확인된 문제입니다.)

```bash
bunx vitest run --pool=threads
```

## 레슨별 시작 브랜치

레슨마다 시작 시점의 코드를 `lesson/<레슨 이름>` 브랜치로 제공합니다. 레슨 본문이 안내하는 브랜치로 바꾼 뒤 따라가세요.

```shell
git checkout lesson/claude-md
```

## 컴포넌트 추가

shadcn/ui 컴포넌트는 다음과 같이 추가합니다.

```bash
bunx --bun shadcn@latest add button
```

`components/ui` 디렉토리에 컴포넌트가 추가됩니다.

## 컴포넌트 사용

```tsx
import { Button } from "@/components/ui/button";
```
