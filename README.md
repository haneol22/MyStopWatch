# MyStopWatch
시간을 측정하는 스톱워치<br>
안드로이드 스튜디오에서 자바로 제작하였습니다.
## 실행화면 
![제목 없음](https://user-images.githubusercontent.com/93521167/202835964-2a6049ae-21a2-41ee-896c-4ad6ee903f64.png)
![제목 없음](https://user-images.githubusercontent.com/93521167/202835976-64675b89-1128-44ee-93c2-bc73a4da564d.png)
<br>
시작,중지,초기화의 모습을 나타내었습니다.
## 간단한 코드설명
우선 스톱워치를 만드려면 Chronometer라는 것이 필요한데, Chronometer는 타이머 기능을 구현할 수 있게 하여주는 클래스입니다.

```JAVA
//중지
stopBtn.setOnClickListener(new View.OnClickListener() {
  @Override
   public void onClick(View v) {
    if (running) {
    chronometer.stop();
    pauseOffset = SystemClock.elapsedRealtime() - chronometer.getBase();
    running = false;
    }
  }
});
```
<br>위 코드는 중지 버튼의 코드입니다. 
elapsedRealtime이라는 메소드를 사용하여 부팅된 시점부터 현재까지의 시간을 millisecond로 리턴합니다. <br>
부팅 직후에는 0을 리턴하고 10초가 지났다면 10000이 리턴됩니다.
getBase는 설정된 기본 시간을 반환하는데 부팅된 시점부터 현재까지의 시간에서 기본 시간을 빼면 지난 시간이 나오는 원리입니다. 

