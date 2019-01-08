![](http://image.kyobobook.co.kr/images/book/large/475/l9788968481475.jpg)

이것이 자바다 도서를 보고 정리한 자료입니다.

# 목차
- [목차](#%EB%AA%A9%EC%B0%A8)
- [멀티 스레드 개념](#%EB%A9%80%ED%8B%B0-%EC%8A%A4%EB%A0%88%EB%93%9C-%EA%B0%9C%EB%85%90)
  - [멀티 스레드, 싱글 스레드](#%EB%A9%80%ED%8B%B0-%EC%8A%A4%EB%A0%88%EB%93%9C-%EC%8B%B1%EA%B8%80-%EC%8A%A4%EB%A0%88%EB%93%9C)
- [스레드 우선 순위](#%EC%8A%A4%EB%A0%88%EB%93%9C-%EC%9A%B0%EC%84%A0-%EC%88%9C%EC%9C%84)
  - [동시성과 병렬성](#%EB%8F%99%EC%8B%9C%EC%84%B1%EA%B3%BC-%EB%B3%91%EB%A0%AC%EC%84%B1)
  - [스레드 스케줄링](#%EC%8A%A4%EB%A0%88%EB%93%9C-%EC%8A%A4%EC%BC%80%EC%A4%84%EB%A7%81)
    - [우선 순위](#%EC%9A%B0%EC%84%A0-%EC%88%9C%EC%9C%84)
- [동기화 메서드와 동기화 블록](#%EB%8F%99%EA%B8%B0%ED%99%94-%EB%A9%94%EC%84%9C%EB%93%9C%EC%99%80-%EB%8F%99%EA%B8%B0%ED%99%94-%EB%B8%94%EB%A1%9D)
  - [공유 객체를 사용할 때 중의 할 점](#%EA%B3%B5%EC%9C%A0-%EA%B0%9D%EC%B2%B4%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%A0-%EB%95%8C-%EC%A4%91%EC%9D%98-%ED%95%A0-%EC%A0%90)
  - [동기화 메서드 및 동기화 블록 - synchronized](#%EB%8F%99%EA%B8%B0%ED%99%94-%EB%A9%94%EC%84%9C%EB%93%9C-%EB%B0%8F-%EB%8F%99%EA%B8%B0%ED%99%94-%EB%B8%94%EB%A1%9D---synchronized)
- [스레드 상태 제어](#%EC%8A%A4%EB%A0%88%EB%93%9C-%EC%83%81%ED%83%9C-%EC%A0%9C%EC%96%B4)
  - [다른 스레드에게 실행 양보 : yield()](#%EB%8B%A4%EB%A5%B8-%EC%8A%A4%EB%A0%88%EB%93%9C%EC%97%90%EA%B2%8C-%EC%8B%A4%ED%96%89-%EC%96%91%EB%B3%B4--yield)
  - [다른 스레드의 종료를 기다림 : join()](#%EB%8B%A4%EB%A5%B8-%EC%8A%A4%EB%A0%88%EB%93%9C%EC%9D%98-%EC%A2%85%EB%A3%8C%EB%A5%BC-%EA%B8%B0%EB%8B%A4%EB%A6%BC--join)
  - [스레드 간 협업 : wait(), notify(), notifyAll()](#%EC%8A%A4%EB%A0%88%EB%93%9C-%EA%B0%84-%ED%98%91%EC%97%85--wait-notify-notifyall)
  - [동기화 메서드는 또는 블록에서만 호출 가능한 Object의 메소드](#%EB%8F%99%EA%B8%B0%ED%99%94-%EB%A9%94%EC%84%9C%EB%93%9C%EB%8A%94-%EB%98%90%EB%8A%94-%EB%B8%94%EB%A1%9D%EC%97%90%EC%84%9C%EB%A7%8C-%ED%98%B8%EC%B6%9C-%EA%B0%80%EB%8A%A5%ED%95%9C-object%EC%9D%98-%EB%A9%94%EC%86%8C%EB%93%9C)
  - [두 개의 스레드가 교대로 번갈아 가며 실행해야 할 경우에 주로 사용](#%EB%91%90-%EA%B0%9C%EC%9D%98-%EC%8A%A4%EB%A0%88%EB%93%9C%EA%B0%80-%EA%B5%90%EB%8C%80%EB%A1%9C-%EB%B2%88%EA%B0%88%EC%95%84-%EA%B0%80%EB%A9%B0-%EC%8B%A4%ED%96%89%ED%95%B4%EC%95%BC-%ED%95%A0-%EA%B2%BD%EC%9A%B0%EC%97%90-%EC%A3%BC%EB%A1%9C-%EC%82%AC%EC%9A%A9)
  - [스레드의 안전한 종료 : stop 플래그, interrupt()](#%EC%8A%A4%EB%A0%88%EB%93%9C%EC%9D%98-%EC%95%88%EC%A0%84%ED%95%9C-%EC%A2%85%EB%A3%8C--stop-%ED%94%8C%EB%9E%98%EA%B7%B8-interrupt)
    - [stop() 메서드 이용하는 방법](#stop-%EB%A9%94%EC%84%9C%EB%93%9C-%EC%9D%B4%EC%9A%A9%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95)
    - [interrupt() 메서드를 이용하는 방법](#interrupt-%EB%A9%94%EC%84%9C%EB%93%9C%EB%A5%BC-%EC%9D%B4%EC%9A%A9%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95)
- [데몬 스레드](#%EB%8D%B0%EB%AA%AC-%EC%8A%A4%EB%A0%88%EB%93%9C)
- [스레드 그룹](#%EC%8A%A4%EB%A0%88%EB%93%9C-%EA%B7%B8%EB%A3%B9)
- [스레드 풀](#%EC%8A%A4%EB%A0%88%EB%93%9C-%ED%92%80)
  - [스레드 폭증](#%EC%8A%A4%EB%A0%88%EB%93%9C-%ED%8F%AD%EC%A6%9D)
  - [스레드 풀](#%EC%8A%A4%EB%A0%88%EB%93%9C-%ED%92%80-1)
  - [ExecitorService 인터페이스와 Excecutors 클래스](#execitorservice-%EC%9D%B8%ED%84%B0%ED%8E%98%EC%9D%B4%EC%8A%A4%EC%99%80-excecutors-%ED%81%B4%EB%9E%98%EC%8A%A4)
  - [스레드풀 종료](#%EC%8A%A4%EB%A0%88%EB%93%9C%ED%92%80-%EC%A2%85%EB%A3%8C)
  - [콜백 방식의 작업 완료 통보](#%EC%BD%9C%EB%B0%B1-%EB%B0%A9%EC%8B%9D%EC%9D%98-%EC%9E%91%EC%97%85-%EC%99%84%EB%A3%8C-%ED%86%B5%EB%B3%B4)
    - [콜백 이란?](#%EC%BD%9C%EB%B0%B1-%EC%9D%B4%EB%9E%80)

# 멀티 스레드 개념
* 멀티 프로세스 : 독립적으로 프로그램을 실행하고 여러 가지 작업을 처리
* 멀티 스레드 :  한 개의 프로그램을 실행하고 내부적으로 여러 가지 작업 처리
* 메인 스레드
  * 모든 자바 프로그램은 메인 스레드가 메인 메서드를 실행하면서 시작된다.
  * main() 메서드의 첫 코드부터 아래로 순차적으로 실행한다.
  * main() 메서드의 마지막 코드를 실행하거나, return 문을 만나면 실행이 종료된다.
  * 메인 스레드(메인 스레드는 JVM이 생성)는 작업 스레드를 만들어서 병렬로 코드들을 실행 할 수있다.

## 멀티 스레드, 싱글 스레드
![](../../draw/java-thread-single-multy.png)


* 싱글 스레드 : 메인 스레드가 종료하면 프로세스도 종료된다.
* 멀티 스레드 : 실행 중인 스레드가 하나라도 있다면, 프로세스는 정료되지 않는다.
  * 메인 스레드가 작업 스레드보다 먼저 종료되더라도 작업 스레드가 계속 실행 중이라면 프로세스는 종료되지 않는다.

# 스레드 우선 순위

## 동시성과 병렬성
![](../../draw/concurrency-Parallelism.png)

* 동시성(concurrency)
  * 멀티 작업을 위해 하나의 코드에서 멀티 스레드가 번갈아 가며 실행하는 성질
  * 하나에 한 쓰레드만 실행할 수 있다. 
  * 하나의 쓰레드가 실행하면 다른 스레드는 대기 상태가 된다.
* 병렬성(Parallelism)
  * 멀티 작업을 위해 멀티 코어에서 개별 스레드를 동시에 실행하는 성질

## 스레드 스케줄링

![](../../draw/thead-shduler.png)

* 스레드의 개수가 코어의 수보다 많은 경우
  * 스레드를 어떤 순서로 동시성으로 실행할것인가를 결정, **스레드 스케쥴링**
  * 스레드 스케쥴링에 의해서 스레드를 번갈아 가면서 그들의 run() 메서드를 조금씩 실행
* 자바의 스레드 스케쥴링
  * 우선순위(Priority) 방식과 순한 할당 (Round-Robin) 방식을 사용
  * 우선순위(Priority) : 우선 순위가 높은 스레드가 실행 상태를 더 많이 가지도록 스케쥴링하는 방식
  * 방식과 순한 할당 (Round-Robin) : 시간 할당량을 정해서 하나의 스레드를 정해진 시간만큼 실행하는 방식

### 우선 순위 
* 스레드들이 동시성을 가질 경우 우선적으로 실행할 수 있는 순위
* 우선 순위는 1(낮음) 부터 10(높음)까지로 부여
  * 모든 스레드들은 기본적으로 5의 우선순위를 할당
* 우선 순위 효과
  * 싱글 코어 경우
    * 우선 순위가 높은 스레드가 실행 기회를 더 많아 가지기 때문에 우선순위가 낮은 스레드보다 계산 작업을 빨리 끝낸다.
  * 멀티 코어 경우
    * 쿼드 코어 경우에는 4개의 스레드가 병렬성으로 실행될 수 있기 때문에 4개 이하의 스레드들을 실핼할 경우 우선순위 방식은 크게 영향을 미치치 못한다.
    * 최소한 5개의 스레드가 실행되어야 우선 순위의 영향을 받는다.

# 동기화 메서드와 동기화 블록

## 공유 객체를 사용할 때 중의 할 점

![](../../draw/thread-synchronization.png)
1. User 1 스레드 : 메모리에 100을 Calculator 객체에 저장
2. User 2 스레드 : 메모리에 50을 Calculator 객체에 저장
3. User 1 스레드 : 출력 100을 예상하지만 50이 출력
4. User 2 스레드 : 50 출력

## 동기화 메서드 및 동기화 블록 - synchronized 
* 단 하나의 스레드만 실핼 할 수 있는 메서드 또는 블록을 말한다.
  * Mutex 방식인거 같음 (뇌피셜)
* 다른 스레드는 메서드나 블록이 실행이 끝날 때까지 대기해야한다.

# 스레드 상태 제어

![](../../draw/thread-status.png)

* 실행 중인 스레드의 상태를 변경하는 것을 말한다.
* 실행 변화를 가져오는 메소드의 종류


상태    | 열거 상수        | 설명
------|--------------|--------------------------------------
객채 생성 | NEW          | 스레드 객체가 생성, 아직 start()메서드가 호출되지 않은 상태
실행 대기 | RUNNABLE     | 실행 상태로 언제든지 갈 수 있는 상태
일시 정지 | WATING       | 다른 스레드가 통지할 때까지 기다리는 상태
일시 정지 | TIME_WAITING | 주어진 시간 동안 기다리는 상태
일시 정지 | BLOCKED      | 사용하고자 하는 객체의 락이 풀릴 때까지 기다리는 상태
종료    | TERMINATED   | 실행을 마친 상태


## 다른 스레드에게 실행 양보 : yield()
![](../../draw/thread-yield.png)

스레드가 처리하는 작업은 반복적인 실행을 위해 for문이나 while문을 포함하는 경우가 많다. 스레드가 시작되어 run() 메서드를 실행하면 블록을 무한 반복 실행한다. 만약 while 문은 어떤 실행문도 실행하지 않고 무의미한 반복을 한다면 이것보다 다른 스레드에게 실행을 양보하고 자신은 실행 대기 상태로 가는 것이 전체 프록램 성능에 도움이 된다. 

이런 기능을 위해 스레드는 yield()메서드를 제공하고 있다. yield() 메서드를 호출한 스레드는 실행디기 상태로 돌아가고 동일한 우선수위 또는 높은 우선순위를 갖는 다른 스레드가 실행 기회를 가질 수 있도록 해준다.

## 다른 스레드의 종료를 기다림 : join()
![](../../draw/thread-join.png)

* `threadB.join()` 메서드는 Thread B를 일시 정지하는 것이 아니라, Thread A를 일시 정지 하는 것이다.
* ThreadA가 ThreadB의 결과 값을 받아 작업이 진행될때 ThreadA는 `threadB.join()`를 통해서 ThreadB의 종료를 기다린다.
* 계산 작업을 하는 스레드가 모든 계산 작업을 마쳤을 때, 계산 결과값을 받아 이용하는 경우 주로 사용

## 스레드 간 협업 : wait(), notify(), notifyAll()
![](../../draw/thread-notify.png)

## 동기화 메서드는 또는 블록에서만 호출 가능한 Object의 메소드
* wait()
  * 호출한 스레드는 일시 정지가 된다.
  * 다른 스레드가 notify() 또는 notifyAll()을 호출하면 실행 대기 상태가 된다.
  * **일시 정시가된 스레드는 절대 자기 스스로 실행 대기로 갈 수 없다.**
  * wait(long timeout)
    * notify()가 호출되지 않아도 시간이 지나면 스레드가 자동적으로 실행 대기 상태가 된다.
    * wait(long timeout)의 시간이 지나지 않아도 notify(), notifyAll() 메서드가 호출되면 즉시 실행 대기 상태로 넘어간다.
    * sleep() 무조건 주어진 시간이 다되야 실행 대기로 넘어간다.

## 두 개의 스레드가 교대로 번갈아 가며 실행해야 할 경우에 주로 사용
![](../../draw/thrad-share-data.png)

* **wait(), notify(), notifyAll() 메서드는 동기화 메소드, 동기화 블록에서만 호출 가능**
* 소비자 스레드가 한 번읽고 생성자 스레드에게 notify()를 호출해서 생성자 스레드가 새로운 데이터를 넣을 때까지 기다린다.

## 스레드의 안전한 종료 : stop 플래그, interrupt()
* 경우에 따라서 실행 중인 스레드를 즉시 종료할 필욕 ㅏ있다.

### stop() 메서드 이용하는 방법
  * 스레드를 즉시 종료시킨다.
  * 스레드를 갑자기 종료하게 되면 사용 중이던 자원들이 불안전한 상태로 남겨진다.
  * deprecated되었음

### interrupt() 메서드를 이용하는 방법
* 일시 정지 상태일 경우 InterruptedException을 발생시킴
* 실행대기 또는 실행 상태에서 InterruptedException이 발생하지 않는다.
* 일시 정지 상태로 만들지 않고 `Thread.interrupted()` 메서드를 통해서 boolean 값을 리턴 받고 `while` 반복문에서 break 코드를 작성한다.

# 데몬 스레드
* 주 스레드의 작업을 돕는 보조적인 역할을 수행하는 스레드
* 주 스레드가 종료되면 데몬 스레드는 강제적으로 자동 종료
  * 워드프로세스에서의 자동저장, 미디어플레이어의 동양상 및 음악 재생, 가비지 컬렉터

# 스레드 그룹
* 관련된 스레드를 묶어서 관리할 목적으로 이용
* 스레드 그룹은 계층적으로 하위 스레드 그룹을 가질 수 있다.
* 자동 생성되는 스레드 그룹
  * system 그룹 : JVM운영에 필요한 스레드들을 포함
  * system/main 그룹 : 메인 스레드를 포함
* 스레드는 반드시 하나의 스레드 그룹에 포함
  * 기본적으로 자신을 생성한 스레드와 같은 스레드 그룹에 속하게 된다.
  * 명시적으로 스레드 그룹에 포함히키지 않으면 기본적으로 system/main 그룹에 속한다.

# 스레드 풀

## 스레드 폭증
* 병렬 작업 처리가 많아지면 스레드의 개수가 증가
* 스레드 생성과 스케쥴링으로 인해 CPU가 바빠지고, 메모리 사용량이 늘어난다.
* 따라서 애플리케이션의 성능이 급격히 저하된다.

## 스레드 풀
* 작업 처리에 사용되는 스레드를 제한된 개수만큼 미리 생성
* 작업 큐에 들어오는 작업들을 하나씩 스레드가 맏아 처리
* 작업 처리가 끝난 스레드는 작업 결과를 애플리케이션으로 전달
* 스레드는 다시 작업큐에서 새로운 작업을 가져와 처리

## ExecitorService 인터페이스와 Excecutors 클래스
* 스레드풀을 생성하고 사용할 수 있도록 java.util.concurrent 패키지에서 제공
* Excecutors의 정적 메서드를 이용해서 ExecitorService구현 객체 생성
* 스레드 풀 = ExecitorService 객체

## 스레드풀 종료
* main 스레드가 종료되더라도 스레드풀의 스레드는 작업을 처리하기 위해서 계속 실행되므로 애플리케이션은 종료되자 않는다.
* 따라서 스레드풀을 종료해서 모든 스레드를 종료 시켜야한다.
  

리턴타입        메서드명        설명
void        shutdown()      현재 처리 중인 작업뿐만 아니라 작업큐에 대기하고 있는 모든 작업을 처리한 뒤에 스레드풀을 종료 시킨다.
List<Runnable>      shutdownNow() 현재 작업 처리 중인 스레들을 interrupt 해서 작업 중지를 시도하고 스레드풀을 종료시킨다. 리턴값은 작업큐에있는 미처리된 작업 Runnable의 목록이다.

## 콜백 방식의 작업 완료 통보

### 콜백 이란?
![](../../draw/blocking-callback.png)

애플리케이션이 스레드에게 작업 처리를 요청한 후, 스레드가 작업을 완료하면 특정 메소드를 작동 실행하는 기법을 말한다. 이때 자동 실행되는 메서드를 콜백 메소드라고 한다.

