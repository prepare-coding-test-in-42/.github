# prepare coding test 🏓

## 🔔 규칙
<img width="400" alt="스크린샷 2024-07-01 오후 2 14 34" src="https://github.com/wanted-preonboarding-android-gyurim/android-preonboarding-Archive/assets/31344894/d588711a-28e4-44d2-8ca3-dd871c355909">

## ⚒️ 코딩테스트
1. [프로그래머스 고득점 kit](https://school.programmers.co.kr/learn/challenges?tab=algorithm_practice_kit) 에서 하나씩 골라 진행
- 일주일에 kit 안에 있는 문제 진행
2. 목요일 20시까지 문제를 풀어 자신의 repo에 '수도 코드, 시간 복잡도, 문제 소요 시간'에 대한 Readme로 작성
- 일주일 마다, repo의 브렌치를 파서, 문제 풀이가 끝나면 pull request 통해 리뷰 받는 형식
3. 다른 사람의 문제 풀이에 대한 피드백을 일요일까지 진행

## 💻 코딩테스트 스케줄
**25.01.06 ~ 25.01.10 정렬** [H-Index](https://school.programmers.co.kr/learn/courses/30/lessons/42747)

## 🥨readme 작성 예시

### 안전지대_2468
### 소요 시간
30분 (아주 쉬웠어영)

### 간단 풀이 방식
맵을 구성하면서, 건물들의 높이를 list에 저장한다(중복 허용하지 않는다)
건물의 높이 list을 순회하면서, 각 높이 이상의 건물을 상하좌우로 구한다 (bfs로 탐색한다)
각 영역의 max 값을 도출한다.

### pseudo code
```java
private static void bfs(Pos pos, int h) {
    Queue<Pos> q = new LinkedList<>();
    q.add(pos);
    visited[pos.y][pos.x] = true;
    cnt++;
    while (!q.isEmpty()) {
        Pos p = q.poll();

        for (int i = 0; i < 4; ++i) {
            int ny = p.y + dy[i];
            int nx = p.x + dx[i];

            if (ny < 0 || ny >= N || nx < 0 || nx >= N || visited[ny][nx] || map[ny][nx] < h) {
                continue;
            }
            q.add(new Pos(ny, nx));
            visited[ny][nx] = true;
        }
    }
}
```

### 메모리 및 시간
- 57168kb
- 272ms
