- [문제](https://www.hackerrank.com/challenges/grading/problem)

- 중간 결과 
  - 애썼으나...머리가 안돌아가고 피곤하다 ㅜ 
  - + 생각을 잘못한 부분이 있음. 다시 풀어야됨.
```sh
    public static List<Integer> gradingStudents(List<Integer> grades) {
        // Write your code here
        for (int i=0; i < grades.size(); i++) {
            if(grades.get(i) > 40) { //5로 나눈 나머지값이
                //int a = grades.get(i)%5;//5로 나눈 나머지값
                if ((grades.get(i)%5) >=3) {

                }
            }

        }
        return grades;
    }
``` 

---------
- 다른 사람 풀이
```sh
static int[] solve(int[] grades)
        {            
            int[] res = new int[grades.Length];
            for (int i = 0; i < grades.Length; i++)
            {
                if (grades[i] % 5 > 2 && !(grades[i] < 38))              
                    res[i] = grades[i] + (5-grades[i]%5);                               
                else               
                    res[i] = grades[i];
               
            }
            return res;
        }
```
