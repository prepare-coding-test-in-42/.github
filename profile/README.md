# Prepare Coding Test 🏓

## 🔔 규칙
<p align="center">
  <img 
    width="400" 
    alt="스크린샷 2024-07-01 오후 2 14 34" 
    src="https://github.com/wanted-preonboarding-android-gyurim/android-preonboarding-Archive/assets/31344894/d588711a-28e4-44d2-8ca3-dd871c355909"
  />
</p>

## ⚒️ 코딩테스트

1. **[프로그래머스 고득점 kit](https://school.programmers.co.kr/learn/challenges?tab=algorithm_practice_kit)에서 문제를 하나씩 골라 진행**
   - 일주일 동안 kit 안의 문제를 진행
2. **목요일 20시까지 문제 풀이를 완료**하고, 개인 레포지토리에 `수도 코드`, `시간 복잡도`, `문제 소요 시간`을 포함한 `README` 작성
   - 매주 레포지토리의 새로운 브랜치를 생성하고, 풀이 완료 후 Pull Request를 생성하여 코드 리뷰
3. **다른 사람의 문제 풀이에 대한 피드백을 일요일까지 완료**

## 💻 코딩테스트 스케줄

- **25.01.06 ~ 25.01.09: 정렬**
  - [H-Index](https://school.programmers.co.kr/learn/courses/30/lessons/42747)
- **25.01.10 ~ 25.01.13: 해시**
  - [폰켓몬](https://school.programmers.co.kr/learn/courses/30/lessons/1845)
  - [완주하지 못한 선수](https://school.programmers.co.kr/learn/courses/30/lessons/42576)
  - [전화 번호 목록](https://school.programmers.co.kr/learn/courses/30/lessons/42577)
  - [의상](https://school.programmers.co.kr/learn/courses/30/lessons/42578)
  - [베스트앨범](https://school.programmers.co.kr/learn/courses/30/lessons/42579)

## 📑 Pull Request 제목 형식
- **월 week N**
  - ex) JAN week2

## 🥨 README 작성 예시

### 안전지대_2468

#### 소요 시간
> 30분 (매우 쉬웠습니다!)

#### 간단 풀이 방식
- 맵을 구성하면서 건물들의 높이를 리스트에 저장 (중복 없음)
- 해당 높이 리스트를 순회하며, 각 높이 이상인 영역을 상하좌우로 BFS 탐색
- 각 탐색 결과 중 영역 개수의 최댓값을 도출

#### Pseudo Code
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

            if (ny < 0 || ny >= N || nx < 0 || nx >= N 
                || visited[ny][nx] || map[ny][nx] < h) {
                continue;
            }
            q.add(new Pos(ny, nx));
            visited[ny][nx] = true;
        }
    }
}
```

#### 메모리 및 시간
- 57168kb
- 272ms
