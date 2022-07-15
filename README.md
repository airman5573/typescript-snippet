# typescript-snippet

타입스크립트관련 코드 모음입니다

## Utilities

### 특정 property만 optional로 만든다

```typescript
type MakeOptional<T, K extends keyof T> = Omit<T, K> & Partial<Pick<T, K>>;

type Clock = {
  hour: number;
  minute: number;
  second: number;
};

type MaybeNoSecondClock = MakeOptional<Clock, "second">;

const clock1: Clock = {
  hour: 3,
  minute: 15,
  second: 54,
};

const clock2: MaybeNoSecondClock = {
  hour: 3,
  minute: 15,
};
```

## React

## Emotion

## 기타등등
