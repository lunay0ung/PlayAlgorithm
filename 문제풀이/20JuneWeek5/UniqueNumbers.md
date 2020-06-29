

- 코딩테스트
  - 예전에 비슷한 문제 풀었던 것 같아서 거기서 힌트를 ㅋ
  
```sh
///겹치지 않는 숫자 구하기
public class UniqueNumbers {
    public static Collection<Integer> findUniqueNumbers(Collection<Integer> numbers) {
        Map<Integer, Integer> map = new HashMap<>();
        for (int element : numbers) {
            if(map.containsKey(element)) {
                map.put(element, 2);
            }
            else {
                map.put(element, 1);
            }
        }
        List<Integer> list = new ArrayList<>();
        for(int key:map.keySet()){
            if(map.get(key)==1){
               list.add(key);
            }
        }


        return list; //list를 반환해야함
    }

    public static void main(String[] args) {
        Collection<Integer> numbers = Arrays.asList(1, 2, 1, 3);
        for (int number : findUniqueNumbers(numbers))
            System.out.println(number);
    }
}
```
