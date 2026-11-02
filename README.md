# edu-notes (응용 교육 쪽별 진행 노트)

정적 사이트입니다. 빌드 과정이 없고 모든 경로가 상대 경로라서, 단독으로 올려도 다른 폴더 아래(하위 경로)에 두어도 그대로 동작합니다.

```
edu-notes/
├ index.html            1일차 · 2일차 · 부록(실습) 탭이 있는 한 페이지
├ assets/
│  ├ d1/p001.webp …     1일차 교재 1~117쪽 화면
│  ├ d2/p001.webp …     2일차 교재 1~98쪽 화면
│  └ ap/p001.webp …     부록(실습교재) 1~35쪽 화면
├ downloads/
│  ├ edu-report.zip     교육이수현황보고.zip (5장 실습 폴더)
│  └ leave-review.zip   휴가신청검토.zip (6장 실습 폴더)
└ vercel.json           캐시·다운로드 헤더(선택)
```

## Vercel에 올리기

- 이 폴더만 올릴 때: 폴더 안에서 `vercel --prod` (Framework Preset은 Other, Build Command와 Output Directory는 비움).
- 여러 페이지를 한 프로젝트로 올릴 때: 이 폴더를 프로젝트 루트 아래에 그대로 넣습니다. 주소는 `/edu-notes/` 입니다.
  이 폴더의 `vercel.json`은 하위 폴더에서는 적용되지 않으므로, 헤더가 필요하면 루트 `vercel.json`에
  `source`를 `/edu-notes/assets/(.*)`, `/edu-notes/downloads/(.*)`로 바꿔 옮깁니다. 헤더가 없어도 사이트와 다운로드는 정상 동작합니다.

## 바꾸는 방법

- 쪽 화면을 바꾸려면 같은 이름(`assets/d1/p039.webp`)으로 덮어씁니다.
- 실습 파일을 바꾸려면 `downloads/`의 zip을 같은 이름으로 덮어씁니다.
- 특정 쪽으로 바로 가는 주소: `#d1-p39`(1일차 39쪽), `#d2-p25`(2일차 25쪽), `#ap-p5`(부록 5쪽). 탭은 `#d1` `#d2` `#ap`.
