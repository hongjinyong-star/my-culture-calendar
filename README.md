# 마이 컬처 캘린더 v2.6 — GitHub Pages 배포 안내

## 1. 준비
- 이전 2.5.2에서 JSON 백업을 다운로드합니다.
- 이 ZIP을 압축 해제하면 `index.html`, `manifest.webmanifest`, `icon-192.png`, `icon-512.png`가 있습니다.
- GitHub 저장소를 새로 만들고 **네 파일 모두 저장소 최상위(root)** 에 올립니다. (저장소는 Public)

## 2. GitHub Pages 설정
- 저장소의 Settings → Pages → Build and deployment → Source: Deploy from a branch
- Branch: main, Folder: /(root) → Save
- 표시되는 사이트 주소 `https://사용자명.github.io/저장소명/`으로 접속합니다.
- 공개 URL을 만들기 때문에 HTML에 비밀번호나 service_role 키를 넣지 마세요.

## 3. 처음 접속 시 중요 사항
- `file://`에서 사용하던 localStorage/IndexedDB/로그인 세션은 GitHub Pages `https://` 주소로 자동 이동하지 않습니다.
- 사이트에서 기존 Supabase Project URL과 publishable key를 다시 입력하고 로그인합니다.
- 기존 로컬 기록이 없다면 클라우드 기록 다운로드를 먼저 실행하고, 사진은 자동 동기화로 받거나 수동 사진 다운로드를 이용합니다.
- 자동 동기화 시작 전에 기록이 일치하는지 확인하고 JSON 백업을 보관하세요.
- 같은 계정의 여행 앱 저장소나 `travel-photos` 버킷은 변경하지 않습니다.

## 4. 휴대폰 바로가기
- Android Chrome: 사이트 접속 → 메뉴(⋮) → 홈 화면에 추가(또는 앱 설치).
- iPhone Safari: 사이트 접속 → 공유 → 홈 화면에 추가.
- 브라우저/기기에 따라 독립 실행 앱이 아닌 홈 화면 바로가기 형태일 수 있습니다.
- 이 버전은 오프라인 캐시 서비스 워커를 포함하지 않아 네트워크 연결이 필요합니다.

## 5. 보안
- GitHub 저장소의 HTML과 설정된 publishable key는 공개됩니다. publishable key는 공개 클라이언트용이지만 Supabase의 RLS와 Storage 정책이 올바르게 적용되어야 합니다.
- Supabase 로그인 비밀번호, service_role/secret key는 절대로 저장소에 올리지 마세요.
- 로그인 상태 유지 옵션은 개인 기기에서만 사용하세요.
