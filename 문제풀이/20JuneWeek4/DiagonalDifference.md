- [문제] (https://www.hackerrank.com/challenges/diagonal-difference/problem?h_r=next-challenge&h_v=zen)

- 
```sh
 public static int diagonalDifference(List<List<Integer>> arr) {
    // Write your code here

        int leftToRight= 0;
        int rightToLeft = 0;
        int i = 0;
        for(List<Integer> list : arr) { //리스트의 리스트에서 i개의 원소를 꺼낸다
            leftToRight += list.get(i);
            i++;
            System.out.println("i: "+i);
        }

        i--;
        for(List<Integer> list2 : arr) {
            System.out.println("i2: "+i);
            rightToLeft += list2.get(i);
            i--;
            
        }

        return Math.abs(leftToRight - rightToLeft);

    }
```
