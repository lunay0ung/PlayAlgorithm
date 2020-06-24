
- [문제](https://leetcode.com/problems/last-stone-weight/)

- 해결 과정 
```sh
  //array에서 max, subMax값을 구해야됨
  //순서대로 0번째부터 검토시작. 0번째 값을 max에 저장, 1번째와 비교한 후 그게 더 크면 max는 1로 교체됨, subMax에는 0번째 것 저장
  //2번째와 비교 -> 2번째 값을 max, submax와 비교. max보다 크면 max에 넣고, max보단 작지만 submax보다 크면 그걸 저장
  //아니면 해시맵? --x
  //재귀로 풀어야.....
  //1) 큰 값 두개를 뽑아서 비교한다 -> 원소를 없애거나 다른 값으로 대체한다 
  //2) 1)에서 구해진 array를 1)의 과정에 반복한다 
  ```
   
- 결론 / 힌트 / 교훈
  - 생각지도 못한 자료구조를 이용하는 것이었음. -> 백날 혼자만 골머리 싸봐야 소용x
  - https://leetcode.com/problems/last-stone-weight/discuss/294993/JavaPython-3-easy-code-using-PriorityQueueheapq-w-brief-explanation-and-analysis.
