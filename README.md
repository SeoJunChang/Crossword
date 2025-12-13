# Crossword Puzzle PWA

모바일에서 앱처럼 사용할 수 있는 영어 십자말 퍼즐 게임입니다.

## ✨ 기능

- **랜덤 퍼즐 생성** - 매번 새로운 퍼즐
- **모바일 최적화** - 터치 인터페이스, 가상 키보드
- **방향 전환** - 같은 칸 클릭 시 가로↔세로 자동 전환
- **힌트 시스템** - 최대 5회 랜덤 글자 공개
- **한글 번역** - 모든 힌트에 한글 번역 제공
- **오프라인 지원** - 인터넷 없이도 플레이 가능
- **홈 화면 추가** - 네이티브 앱처럼 사용

## 📱 아이폰에서 설치하기

### 방법 1: GitHub Pages 배포 (추천)

1. **GitHub 저장소 생성**
   - GitHub에서 새 저장소 만들기 (예: `crossword-pwa`)
   - Public으로 설정

2. **파일 업로드**
   ```
   crossword-pwa/
   ├── index.html
   ├── manifest.json
   ├── sw.js
   ├── icon-192.png
   └── icon-512.png
   ```

3. **GitHub Pages 활성화**
   - 저장소 → Settings → Pages
   - Source: Deploy from a branch
   - Branch: main, / (root)
   - Save

4. **URL 확인**
   - 몇 분 후 `https://[사용자명].github.io/crossword-pwa` 에서 접속 가능

5. **아이폰에 설치**
   - Safari로 위 URL 접속
   - 공유 버튼 (□↑) 탭
   - "홈 화면에 추가" 선택
   - 앱처럼 아이콘이 생성됨!

### 방법 2: Netlify 배포 (더 쉬움)

1. [Netlify](https://netlify.com) 가입
2. "Sites" → "Add new site" → "Deploy manually"
3. `crossword-pwa` 폴더 드래그 앤 드롭
4. 자동 생성된 URL로 접속
5. Safari에서 "홈 화면에 추가"

### 방법 3: 로컬 서버 (개발/테스트용)

```bash
# Python 3
cd crossword-pwa
python -m http.server 8000

# 같은 Wi-Fi에서 아이폰으로 접속
# http://[컴퓨터IP]:8000
```

## 🎮 사용법

| 동작 | 설명 |
|------|------|
| 셀 탭 | 해당 셀 선택 |
| 같은 셀 다시 탭 | 가로↔세로 방향 전환 |
| 키보드 입력 | 글자 입력 후 자동 이동 |
| ↔️ 버튼 | 방향 전환 |
| ⌫ 버튼 | 글자 삭제 및 이전 셀로 이동 |
| 💡 Hint | 랜덤 글자 공개 (5회 제한) |
| Clues | 전체 힌트 목록 보기 |
| 한글 번역 | 힌트의 한글 번역 표시 토글 |

## 📂 파일 구조

```
crossword-pwa/
├── index.html      # 메인 앱 (HTML + CSS + JS 통합)
├── manifest.json   # PWA 설정 (앱 이름, 아이콘 등)
├── sw.js          # 서비스 워커 (오프라인 캐싱)
├── icon-192.png   # 앱 아이콘 (192x192)
├── icon-512.png   # 앱 아이콘 (512x512)
└── README.md      # 이 파일
```

## 🔧 커스터마이징

### 단어 추가하기

`index.html`의 `WORD_DATABASE` 배열에 단어 추가:

```javascript
{ word: "HELLO", clue: "Greeting word", korean: "안녕" },
```

### 그리드 크기 변경

```javascript
let gridSize = 11;  // 11x11 그리드 (기본값)
```

### 힌트 횟수 변경

```javascript
let hintsRemaining = 5;  // 기본 5회
```

## 🌐 브라우저 지원

- ✅ Safari (iOS)
- ✅ Chrome (Android/Desktop)
- ✅ Firefox
- ✅ Edge

## 📜 라이선스

자유롭게 사용하세요!
