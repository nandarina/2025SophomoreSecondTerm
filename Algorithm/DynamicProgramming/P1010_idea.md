#1010번: 다리 놓기

문제 내용:
왼쪽 영역 N개, 오른쪽 영역 M개가 주어지고, 교차하지 않고 이들을 N개의 다리로 이을 수 있는 경우의 수 구하기.

나의 접근 방식:
1) 재귀로 구현

```C++
int leg(int pos, int cnt, int maxN, int maxM){
    if(cnt >= maxN){
        return 1;
    }
    if(pos >= maxM){
        return 0;
    }
    
    return leg(pos+1, cnt, maxN, maxM) + leg(pos+1, cnt+1, maxN, maxM);
}
```

N개의 영역을 하나씩 선택해서 경우를 일일이 재귀로 구하는 방법!
문제는 N=15, M=30과 같은 입력이 들어오면 (N=0인 경우)*(N=1인 경우 + ... N=15인 경우) (이때 N=k인 경우에 대하여 또 곱하기를 해줌. 즉, 자식이 k-1개인 트리다.)

<img src="./1010_image1.png", height="100x", width="100px"></img>

2) 
