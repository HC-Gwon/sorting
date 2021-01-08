# sorting
Studying sorting

1. 주어진 n개의 수/문자에 대해서 사용자가 지정한 기준에 맞춰 정렬하여 출력하는 것
   -> 원하는 데이터를 찾기가 쉬워진다.(이진탐색 수행이 원활해진다.)
2. 시간복잡도는 항상 최악의 경우를 따진다.
3. 안정정렬과 불안정정렬
   안정정렬 : 같은 숫자에 대해 원래의 순서가 바뀌지 않는 정렬
   불안정정렬 : 같은 숫자에 대해서 원래의 순서가 바뀌는 정렬
4. O(N^2)인 알고리즘   - 백준 2750 수 정렬하기 1을 통해 만든 정렬을 테스트
   ㄱ. 선택정렬 (Selection Sort) / 불안정정렬
       - 현재 위치에 들어갈 값을 찾는 방식
       - 0번 위치부터 시작하여 정렬되지 않은 부분에 대해서 가장 작은/큰 값을 찾고 찾은 값을 0번 위치의 원래 값과 바꾼다.
         그 다음 1번 위치에서 정렬되지 않은 부분에 대해서 가장 작은/큰 값을 찾고 찾은 값을 1번 위치의 원래 값과 바꾼다.
         위의 과정을 n번째 위치까지 반복한다.
       - n-1개, n-2개, ... , 1개를 각 위치에서 비교하므로 시간복잡도가 O(N^2)이다. (1부터 n-1까지의 합)
   ㄴ. 삽입정렬 (Insertion Sort) / 안정정렬
       - 현재 위치에서 앞으로 한칸씩 이동하며 자신의 위치를 찾는 방식
       - 1번 위치에서 0번 위치의 값과 비교하여 1번 위치의 값이 더 크면 그대로 더 작으면 앞으로 이동하고 0번 위치의 값을 한칸 뒤로 이동
         2번 위치에서 1번 위치의 값과 비교하여 2번 위치의 값이 더 크면 그대로 더 작으면 앞으로 이동하고 1번 위치의 값은 한칸 뒤로 이동
                      0번 위치의 값과 비교하여 2번 위치의 값이 더 크면 그대로 더 작으면 앞으로 이동하고 0번 위치의 값은 한칸 뒤로 이동
         위의 과정을 n번째 위치까지 반복한다.
       - 역으로 정렬되어 있을 경우 1개, 2개, ... , n-1개를 각 위치에서 비교하므로 시간복잡도가 O(N^2)이다.
   ㄷ. 버블정렬 (Bubble Sort) / 안정정렬
       - 연속한 두개의 값을 비교하여 큰 값을 뒤로 보내서 정렬하는 방식
       - 0번 위치의 값과 1번 위치의 값을 비교하여 큰 값을 뒤로 보낸다.
         1번 위치의 값과 2번 위치의 값을 비교하여 큰 값을 뒤로 보낸다.
         이런 식으로 반복하여 n-1번 위치의 값과 n번 위치의 값을 비교하여 큰 값을 뒤로보내면 첫번째 반복에서 가장 큰 값을 맨 뒤로 보낼 수 있다.
         위의 과정을 반복한다.
       - n-1번, n-2번, ... , 1번 연속한 두개의 값을 비교하므로 시간복잡도가 O(N^2)이다.
   
   O(NlogN)인 알고리즘   - 백준 2751 수 정렬하기 2을 통해 만든 정렬을 테스트
   ㄱ. 퀵정렬 (Quick Sort) / 불안정정렬
       - 분할정복을 이용, pivot point로 정한 값을 기준으로 작은 값은 왼쪽, 큰 값은 오른쪽으로 옮기는 방식으로 정렬을 진행
       - 임의의 위치의 값을 선택하고 그 값을 pivot이라 하고 pivot값을 제외하고 가장 왼쪽을 left, 가장 오른쪽을 right라 하자.
         left 값은 pivot보다 크고 right 값은 pivot보다 작은 값을 선택했을 때 두 위치를 바꾸고 계속 옆으로 한칸씩 이동한다.
         이렇게 이동하다가 right가 left의 왼쪽에 위치했을 때 pivot을 right 위치의 값과 변경하고 첫번째 재귀를 종료한다.
         그 이후 st(현재는 0) ~ right-1 / right+1 ~ end 에 대해서 퀵정렬을 재귀적으로 반복한다.
       - 정렬된 경우 pivot을 왼쪽에서부터 잡아가면 n-1번, n-2번, ... , 1번 비교를 하기 때문에 시간복잡도가 O(N^2)이다.
         하지만 일반적으로 그런 경우는 없기 때문에 N개의 수에 대해서 logN번 재귀를 수행하므로 시간복잡도가 일반적으로 O(NlogN)이다.
   ㄴ. 합병정렬 (Merge Sort) / 안정정렬
       - 분할정복을 이용하여 분할된 배열의 크기가 1보다 작거나 같을 때까지 반복하고 나눈 배열을 크기를 비교하며 다시 합치는 방식으로 정렬을 진행
       - 주어진 배열을 길이가 1이 될 때까지 계속 나눈다. (주어진 배열에 대해서 left, right 값을 재귀적으로 나누는 과정, 배열을 만들어가며 나누진 않는다.)
         나눈 배열을 크기를 비교해가며 새로운 배열에 저장해가며 합친다.
       - 배열을 나눌 때 logN, 배열을 비교해가며 합칠 때 N의 시간이 나누는데 걸리는 시간의 배수만큼 걸리므로 시간복잡도는 O(NlogN)이다.
   ㄷ. 힙정렬 (Heap Sort) / 불안정정렬
       - 오름차순/내림차순에 맞게 최소힙/최대힙을 구현하여 첫 번째 노드를 제거하고 다시 최소힙/최대힙에 맞게 정렬 후 첫 번째 노드를 제거하는 과정을 반복하여 정렬을 진행
       - n개의 수에 대해서 정렬하는 과정 logN의 시간이 걸리므로 시간복잡도는 O(NlogN)이다.
   
   O(kN)인 알고리즘
   ㄱ. 기수정렬 (Radix Sort) / 안정정렬
       - 주어진 배열의 가장 낮은자리/가장 높은자리부터 가장 높은자리/가장 낮은자리에 대해서 정렬하면서 전체적인 정렬을 진행
       - 가장 작은자리부터 비교하는 LSD / 가장 높은자리부터 비교하는 MSD 방식이 존재한다.
       - 숫자를 정렬할 때 가장 큰 숫자가 10000이라고 하면 5번의 비교가 필요하므로 시간복잡도는 O(5N)이 된다. (문자의 경우는 문자의 길이)


참고
1. https://hsp1116.tistory.com/33#:~:text=%EC%A0%95%EB%A0%AC%20%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98%EC%9D%80%20%EC%A0%95%EB%A7%90%20%EB%8B%A4%EC%96%91%ED%95%9C%EB%8D%B0,%EC%9D%B8%20%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98%EC%9D%84%20%EB%B3%B4%EB%A0%A4%EA%B3%A0%20%ED%95%9C%EB%8B%A4.&text=%EC%84%A0%ED%83%9D%20%EC%A0%95%EB%A0%AC%EC%9D%80%20%EC%9D%B4%EB%A6%84%EC%97%90,%EC%B0%BE%EC%95%84%20%EC%A0%95%EB%A0%AC%ED%95%98%EB%8A%94%20%EB%B0%B0%EC%97%B4%EC%9D%B4%EB%8B%A4.
2. https://gmlwjd9405.github.io/2018/05/08/algorithm-shell-sort.html
3. https://www.zerocho.com/category/Algorithm/post/58007c338475ed00152d6c4c
