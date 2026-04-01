# Hotel 360° Survey Viewer

Pannellum 기반 360° 파노라마 뷰어 — Qualtrics 설문 embed용

## 폴더 구조

```
survey/
├── viewer.html          ← 360° 뷰어 (이 파일 1개로 모든 호텔 커버)
├── index.html           ← 테스트 페이지 (연구자 확인용)
├── README.md
└── images/              ← 여기에 360° 파노라마 이미지를 넣으세요
    ├── hotel_01_lobby.jpg
    ├── hotel_01_room.jpg
    ├── hotel_02_lobby.jpg
    ├── hotel_02_room.jpg
    ├── ...
    ├── hotel_15_lobby.jpg
    └── hotel_15_room.jpg
```

## 설정

- FOV: 120° (고정, 줌 불가)
- 수직 시야: ±60°
- 줌인/줌아웃: 비활성화
- 자동 회전: 비활성화
- 체류 시간 & 회전량 자동 추적

## GitHub Pages 배포 방법

1. GitHub에 새 repository 생성 (예: `hotel-survey`)
2. 이 survey 폴더의 내용을 push
3. Settings → Pages → Source: main branch → Save
4. 몇 분 후 `https://USERNAME.github.io/hotel-survey/` 에서 접속 가능

## Qualtrics에서 사용하는 방법

1. Qualtrics에서 새 질문 추가
2. 질문 텍스트 영역에서 "HTML View" (소스 편집) 클릭
3. 아래 코드 붙여넣기:

```html
<iframe
  src="https://USERNAME.github.io/hotel-survey/viewer.html?image=hotel_01_lobby.jpg"
  width="960"
  height="560"
  frameborder="0"
  allow="gyroscope"
  style="border-radius:10px; display:block; margin:0 auto;">
</iframe>
```

4. 각 호텔/공간마다 별도 Qualtrics 페이지에서 `?image=` 파라미터만 변경

## 이미지 요구사항

- 형식: JPG (equirectangular projection)
- 권장 해상도: 4096×2048 이상
- 파일명 규칙: hotel_XX_lobby.jpg / hotel_XX_room.jpg
