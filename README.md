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

### 특정 타입만 뽑아낸다

#### 객체로 뽑아낸다

```typescript
type Person = {
  name: string;
  age: number;
};

type NameObj = Pick<Person, "name">;

const myNameObj: NameObj = {
  name: "yoon",
};
```

#### 딱 그 프로퍼티의 타입만 뽑아낸다

```typescript
type Person = {
  name: string;
  age: number;
};

type NameType = Person["name"];

const myName: NameType = "yoon";
```

### 객체에서 key만 뽑아서 string union으로 만들자

```typescript
type ObjKeys<T extends object> = keyof T;

const BreakPoints = {
  xs: 0,
  sm: 500,
  md: 786,
  lg: 1200,
};

type Size = ObjKeys<typeof BreakPoints>;

function mq(size: Size) {
  return `@media (max-width: ${BreakPoints[size]}px)`;
}
```

## React

## Emotion

## 기타등등
