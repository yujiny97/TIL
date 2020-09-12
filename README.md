#TIL

java 문법

헤더
```java
import java.util.*;
```


정수배열은 ()가 없음
```java
int arr[]
```
arr의 사이즈:
```java
arr.length;
```

String s
s의 사이즈: 
```java
arr.length();
```

String은 startsWith(), indexOf()로 문자열 속해있는지 알수 있다.

CompareTo() 는 같으면 0 


##HashMap
선언방법
```java
Map<String,Integer> map=new HashMap<String,Integer>();
```

값 넣기
```java
map.put(“유진”,24);
```
값 삭제하기
```java
Iterator it=map.keySet().iterator();
while(it.hasNext()){
String k=(String)it.next();
if(조건){
map.remove(k);
it=map.keySet().iterator();
}
}
```

반복문
```java
for(String k:map.keySet()){
int value=map.get(k);
}
```
Hashmap 정렬방법
key에 대해서 정렬하기(Treemap 사용하기) (Comparator 방법으로 해도 됨)

오름차순
```java
TreeMap<String,Integer> m2=new TreeMap<String,Integer>(m);//Hashmap으로 만들었으면 treemap에 넣어주기
```
내림차순
내림차순을 하려면 그냥 TreeMap로 생성하거나 Comparator을 쓰는게 낫다.
```java
TreeMap<String,Integer> m2=new TreeMap<String,Integer>(Collections.reverseOrder());
```
value에 의한 정렬
**Comparator 사용하기
Entry 헤더 추가하기
```java
import java.util.Map.Entry;

Set<Entry<String,Integer> > s=m.entrySet();
ArrayLIst<Entry<String,Integer>> ll=new ArrayList<<Entry<String,Integer>>>(s);
Collections.sort(ll,new Comparator<Entry<String,Integer>>(){
	@Override
	public int compare(Entry<String,Integer> a,Entry<String,Integer> b){
		return a.getValue()-b.getValue();//value에 대하여 a가 b보다 크면 바꾼다. (즉 오름차순임)
//compare에서 return이 양수면 앞뒤가 바뀌는 방식이므로 내림차순으로 하고싶으면 자리 바꿔주면 됨
	}
});

```
Set (중복 삽입 불가)
선언
```java
Set<String> s=new HashSet<String>();
```
집어넣기
```java
s.add(“a”);
```
삭제하기
(반복문)출력하기
```java
Iterator<String> it=s.iterator(); //<String> 이거는 안해도 되지만 (String)it.next() 안하면 이렇게 캐스팅 해야한다. 
while(it.hasNext()){
	String val=it.next();
	System.out.println(“it:”,val);//값 꺼내기
}

```
