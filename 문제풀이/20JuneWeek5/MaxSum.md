
- 코딩테스트
```sh

//2개의 최대값 구하기
public class MaxSum {
    public static int findMaxSum(List<Integer> list) {
        int max = 0;

        //list를 sort한다
        list = list.stream().sorted().collect(Collectors.toList());
        for(int i= 2; i< list.size(); i++) {
            max += list.get(i);
            System.out.println("max: "+max);
        }
        return max;
    }

    public static void main(String[] args) {
        List<Integer> list = Arrays.asList(5, 9, 7, 11);


        System.out.println(findMaxSum(list));
    }
}
```
