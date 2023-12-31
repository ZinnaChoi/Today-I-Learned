# 인접 행렬과 인접 리스트 차이

- 둘 중 어느것을 써야 할까? 차이점에 대해 알아보자

### 공간복잡도

- 인접행렬 : O(V^2)
- 인접리스트 : O(V + E)

```java
// 인접행렬
bool adj[V][V];
// 인접리스트
vector<int> adj[V];
```

### 시간복잡도 : 간선 한개 찾기

- 인접행렬 : O(1)
- 인접리스트 : O(V)

```cpp
// 인접행렬
for(int i = 0;i < V; i++){
    for(int j = 0; j < V; j++){
        if(a[i][j]){
        }
    }
}
// 인접리스트
for(int j = 0; j < adj[i].size(); j++){
    cout << adj[i][j] << " ";
}
```

### 시간복잡도 : 모든 간선찾기

- 인접행렬 : O(V^2)
- 인접리스트 : O(V + E)

### 결론

- 그래프가 희소(sparse)할 때는 인접 리스트, 조밀할 때는 인접 행렬을 사용하는 것이 좋다
  - 그래프가 희소할 때는 인접 행렬이 인접 리스트보다 메모리를 많이 써야 한다. 간선이 없어서 대부분의 요소가 0인데도 불구하고 해당 부분을 포함해서 2차원 배열을 만들어야 하기 때문
  - 그래프가 조밀할 때는 인접 행렬이 인접 리스트보다 좋다. 어짜피 다 연결되어 있기 때문에 메모리적 효율성은 비슷해지고 정점 i에서 정점 j까지의 간선이 있는지 확인하는 속도가 더 빠르기 때문

=> 보통은 인접 리스트를 사용하면 된다 sparse한 그래프 문제가 많이 출제되기 때문
=> 다만 코딩테스트나 인터뷰에서 인접행렬로 주어진다면 그대로 인접 행렬로 푸는 것이 좋음
