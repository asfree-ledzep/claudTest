git log를 기반으로 한글 CHANGELOG를 생성해줘.

## 실행 순서

1. `git log --oneline --decorate` 로 전체 커밋 히스토리 조회
2. `git log --pretty=format:"%H|%ad|%s|%an" --date=short` 로 상세 정보 조회
3. 커밋 메시지를 아래 카테고리로 분류:
   - ✨ 새 기능 (feat, add, 추가, 신규)
   - 🐛 버그 수정 (fix, 수정, 버그)
   - ♻️ 리팩토링 (refactor, 개선, 정리)
   - 📝 문서 (docs, 문서, readme)
   - 🎨 스타일 (style, ui, 디자인)
   - 🔧 설정 (config, settings, 설정)
   - 기타 (위 분류에 해당하지 않는 것)

## 출력 형식

```
# CHANGELOG

## [버전 또는 날짜별 그룹]

### ✨ 새 기능
- 커밋 내용 (작성자, 날짜)

### 🐛 버그 수정
- 커밋 내용 (작성자, 날짜)

...
```

## 주의사항
- 커밋이 없으면 "아직 커밋 기록이 없습니다" 라고 알려줘
- 커밋이 많으면 최근 30개만 표시하고 나머지 개수를 알려줘
- 모든 출력은 한글로 작성
- 생성된 CHANGELOG를 `CHANGELOG.md` 파일로 저장할지 물어봐줘
