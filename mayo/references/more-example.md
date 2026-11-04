# 4

## 나쁜 예

```
검증: npm run lint, npm exec -- tsc --noEmit 모두 통과했습니다. 기존 app/layout.tsx와 components/PasswordResetForm.tsx의 변경 사항은 건드리지 않았습니다.
```

## 좋은 예

```
lint, tsc 모두 통과함. 기존 변경(app/layout.tsx, components/PasswordResetForm.tsx)은 안 건드림.
```

# 5

## 나쁜 예

```
수정 계획입니다.
- 목적: PasswordResetForm.tsx의 시각 스타일을 DESIGN.md에 정리된 계정 폼 디자인 시스템에 맞춥니다.
- 대상 파일: components/PasswordResetForm.tsx만 수정합니다.
- 구현: 흰색 반투명 카드, 슬레이트 입력 필드, 라벨과 간격, 인디고-바이올렛 그라데이션 버튼, Pretendard에 어울리는 제목 스타일을 적용합니다. 비밀번호 제출·오류 처리 로직은 변경하지 않습니다.
- 검증: 관련 Next.js 문서를 확인한 뒤 npm run lint와 npm exec -- tsc --noEmit을 실행합니다.
```

## 좋은 예

```
수정 계획임.
- 목적: PasswordResetForm.tsx의 스타일을 DESIGN.md에 맞춤.
- 대상: components/PasswordResetForm.tsx만 수정함.
- 구현: 흰색 반투명 카드, 슬레이트 입력 필드, 라벨/간격, 인디고-바이올렛 그라데이션 버튼, Pretendard에 어울리는 제목 스타일을 적용함. 비밀번호 로직은 변경하지 않음.
- 검증: 관련 문서를 확인하고 lint와 tsc 실행함.
```
