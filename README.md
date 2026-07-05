# Claude-interactive-01 — Hand Bloom

손을 펼치는 정도에 따라 꽃 영상이 봉오리에서 만개까지 스크럽되는 웹캠 인터랙티브 페이지입니다.

## 🔗 바로 실행하기

**[👉 여기를 클릭해서 실행](https://lgw7126.github.io/claude-interactive-01/handbloom.html)**

> 위 링크가 "404 File not found"로 뜬다면 아직 GitHub Pages가 켜지지 않은 것입니다. 아래 [GitHub Pages 켜는 법](#github-pages-켜는-법-한-번만-하면-됨)을 먼저 진행해 주세요.

## 무엇을 하는 페이지인가요?

- `handbloom.html`을 열면 웹캠이 켜지고, 화면에 손을 비추면 손의 움직임을 인식합니다.
- **주먹을 쥐면** `flower-bloom.mp4` 영상의 첫 프레임(꽃봉오리)이,
- **손을 활짝 펼치면** 영상의 마지막 프레임(만개한 꽃)이 나옵니다.
- 즉, 손을 쥐었다 펴는 정도가 영상 재생 위치를 실시간으로 조종(스크럽)하는 방식입니다.
- 손 모양을 따라 은은한 글로우 이펙트도 함께 표시됩니다.

## 파일 구성

| 파일 | 설명 |
|---|---|
| `handbloom.html` | 웹캠으로 손 모양을 인식하고 영상을 조종하는 메인 페이지 |
| `flower-bloom.mp4` | 꽃봉오리 → 만개 과정이 담긴 영상 (반드시 html과 같은 폴더에 있어야 함) |

## GitHub Pages 켜는 법 (한 번만 하면 됨)

1. 이 저장소의 **Settings** 탭 클릭
2. 왼쪽 메뉴에서 **Pages** 클릭
3. **Build and deployment → Source**를 `Deploy from a branch`로 설정
4. **Branch**를 `main` / `/ (root)`로 선택 후 **Save**
5. 1~2분 기다리면 위 실행 링크가 정상 작동합니다.

## 내 컴퓨터에서 직접 실행하기 (인터넷 없이도 가능)

GitHub Pages 없이도 내 컴퓨터에서 바로 실행할 수 있습니다.

### 1. 파일 받기

이 저장소를 다운로드하거나(Code → Download ZIP) `git clone`으로 받아서, **`handbloom.html`과 `flower-bloom.mp4`가 같은 폴더**에 있는지 확인하세요.

### 2. 로컬 서버 켜기

브라우저 보안 정책(웹캠 사용)때문에 파일을 더블클릭해서 여는 것은 동작하지 않습니다. 반드시 간단한 로컬 서버를 통해 열어야 합니다.

**Mac / Linux (터미널)**
```bash
cd 다운받은_폴더_경로
python3 -m http.server 8000
```

**Windows (PowerShell)**
```powershell
cd 다운받은_폴더_경로
python -m http.server 8000
```

> `python`이 인식되지 않는다는 오류가 나오면 [python.org](https://www.python.org/downloads/)에서 파이썬을 설치하세요. 설치 시 "Add python.exe to PATH" 옵션을 꼭 체크하세요.

### 3. 브라우저에서 열기

Chrome, Edge 등에서 아래 주소로 접속합니다.

```
http://localhost:8000/handbloom.html
```

카메라 접근 권한 요청이 뜨면 **허용**을 눌러주세요.

### 4. 사용하기

- 카메라 앞 30~60cm 거리에서 손바닥이 카메라를 향하게 들어주세요.
- 화면 아래 "OPEN YOUR HAND TO BLOOM" 문구가 사라지면 손이 인식된 것입니다.
- 주먹 ↔ 손 펴기를 반복하며 꽃이 피고 지는 모습을 확인하세요.

## 문제 해결

| 증상 | 원인 / 해결 |
|---|---|
| 카메라 팝업 없이 화면이 계속 검은색 | 서버(`http.server`)를 안 거치고 파일을 직접 열었을 가능성이 큽니다. 위 2~3단계를 다시 확인하세요. |
| "Requested device not found" 오류 | 컴퓨터에 웹캠이 없거나 Windows 설정에서 카메라 접근이 꺼져 있는 상태입니다. 설정 → 개인정보 및 보안 → 카메라에서 접근을 허용하세요. |
| 영상이 안 뜨고 꽃 그림만 안 보임 | `flower-bloom.mp4` 파일명이 정확히 일치하는지, `handbloom.html`과 같은 폴더에 있는지 확인하세요. |
| 손을 흔들어도 반응이 없음 | 조명이 너무 어둡거나 손이 화면 밖에 있을 수 있습니다. 밝은 곳에서 손 전체가 카메라에 보이도록 조정하세요. |
