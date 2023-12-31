# 이터레이터 패턴

> 이터레이터를 사용하여 컨테이너의 요소들에 접근하는 디자인 패턴. 각기 다른 자료 구조들을 똑같은 인터페이스로 순회할 수 있다는 장점 존재. 여기서 컨테이너란 동일한 요소들을 담아놓는 집합 ex) 배열, 맵

- 컬렉션 구현 방법을 노출시키지 않으면서도 그 집합체 안에 들어있는 모든 항목에 접근할 수 있게 해주는 방법을 제공해주는 패턴
- 이터레이터 패턴을 사용하면 집합체 내에서 어떤 식으로 일이 처리되는지 몰라도 그 안에 들어있는 항목들에 대하여 반복작업을 수행할 수 있다
- 맵이든 배열이든 상관없이 하나의 자료구조만으로 각기 다른 자료 구조들을 탐색할 수 있음

ex) 서로 다른 맵, 집합 배열 (자료구조)를 하나의 이터레이터 for(let ~ of )라는 인터페이스 만으로 탐색 가능

```js
//자료구조 1: 맵
const mp = new Map();
mp.set("a", 1);
mp.set("b", 2);
mp.set("cccc", 3);

// 자료구조 2: 집합
const st = new Set();
st.add(1);
st.add(2);
st.add(3);

// 자료구조 3: 배열
const a = [];
for (let i = 0; i < 10; i++) a.push(i);

for (let aa of a) console.log(aa);
for (let a of mp) console.log(a);
for (let a of st) console.log(a);
```
