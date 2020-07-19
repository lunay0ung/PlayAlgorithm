- [문제](https://www.hackerrank.com/challenges/grading/problem)

````sh
HackerLand University has the following grading policy:

Every student receives a  in the inclusive range from  0 to 100.
Any grade less than 40 is a failing grade. 

점수는 0~100점까지, 40점 미만은 과락 

Sam is a professor at the university and likes to round each student's grade according to these rules:
If the difference between the grade and the next multiple of 5 is less than 3, round grade up to the next multiple of 5.
If the value of grade is less than 38, no rounding occurs as the result will still be a failing grade.
점수와 그보다 큰 5의 배수의 차이가 3보다 작으면 5의 배수로 반올림
점수가 38점보다 낮을 경우 반올림은 하지 않으며 그대로 과락 
````

  - 예시 
    - ![](https://s3.amazonaws.com/hr-challenge-images/0/1484768684-54439977a1-curving2.png)
    
- 결과: 풀긴 풀었고 지난번보단 나아졌지만 난잡함을 지울 수 없다 ㅋㅋㅋ 맴에 안듦 
- 풀이
````sh


    public static List<Integer> gradingStudents(List<Integer> grades) {

        /*
        The first line contains a single integer, n, the number of students.
        Each line i of the n subsequent lines contains a single integer, grades[i], denoting student i's grade.
         */
        //점수와 그보다 큰 5의 배수의 차이가 3보다 작으면 5의 배수로 반올림
        //점수가 38점보다 낮을 경우 반올림은 하지 않으며 그대로 과락
        //점수가 38보다 작으면 아무것도 하지 않음 -> 38보다 큰가 작은가를 따져봐야 함
        List<Integer> result = new ArrayList<>();
        for(int i=0; i<grades.size();i++) {

            if(grades.get(i) >= 38) {
                //grade보다 큰 5의 배수 ->
                int a = (5*(grades.get(i)/5))+5;
                if((a - grades.get(i)) < 3) {
                    System.out.println("원래 수: "+grades.get(i));

                    result.add((5*(grades.get(i)/5))+5);
                    System.out.println("결과 1: "+(5*(grades.get(i)/5))+5);
                }

                else {
                    result.add(grades.get(i));
                    System.out.println("결과 2: "+Math.round(grades.get(i)));

                }

            }
            else {
                result.add(grades.get(i));
                System.out.println("결과 3: "+Math.round(grades.get(i)));

            }

        }

        return result;
    }
````


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
