# 과제 조건
라인 플러스 메인 페이지 마크업 구조 설계하고, CSS 스타일링하기
  - 개인 깃허브에 homework 레포 만들고 일자별로 폴더 만든 뒤 그 안에 html과 css 파일을 구분해서 작성해서 업로드
  - 데스크탑 1200px 기준 고정형 레이아웃으로 만들기
  - https://linepluscorp.com/
  
  
  1. 과제전 생각<br/>
  ![KakaoTalk_20190403_165716560](https://user-images.githubusercontent.com/48181483/55462402-9d107b00-5631-11e9-8e68-161686e4f37f.jpg)
  2. 진행중 생각<br/>
  3번째 친구 list가 아니라 div, 다른친구들이 넓은게 아니라 이친구가 좁은거
  3. 코딩<br/>
  ![p1](https://user-images.githubusercontent.com/48181483/55448955-c7980f00-5604-11e9-82d2-71d2d438245c.png)
  과제를 하기에 앞서, 3가지 영역으로 나누어 코딩할것이라 큰틀을 그려보았다 배경색상으로 영역을 잘 차지했는지 구별하였는데,
  푸터는 display가 block이라 혼자 영역을 차지하는 것을 보니 다른친구들은 inline블록으로 생각했다. (나중에 아니란거 알게됨)
  ![p2](https://user-images.githubusercontent.com/48181483/55449755-be5c7180-5607-11e9-8b1b-99ed9e1782b6.png)
  
  헤더랑 푸터에는 width 1200px고정값을 주고, 컨테이너에는 꽉찬 화면을 유지하기위해 100%를줬다, 다만 서로 다른 영역을 차지하기 위해
  display block을 줬다. 여기서 생각한대로 되지않아서 시간낭비했는데 오타때문이다
  
  ![p3](https://user-images.githubusercontent.com/48181483/55455668-76e1df80-561f-11e9-96d9-6c8584b2334b.png)
  
  헤더에 기본골자들을 넣었다 이제 이친구들을 배치하자
  
  
  ![p4](https://user-images.githubusercontent.com/48181483/55463585-5a9c6d80-5634-11e9-8fe3-072509a54ab4.png)
  배치하기전에 Eric Meyer의 css리셋했다 내가 설정하지도 않은 마진패딩등이 브라우저에 들어가있기 때문이다
  
  ![p5](https://user-images.githubusercontent.com/48181483/55463735-9e8f7280-5634-11e9-88b0-2712faa5010e.png)
  배치중...

  
  
  ![p6](https://user-images.githubusercontent.com/48181483/55463737-a18a6300-5634-11e9-96e7-69897a12f2ca.png)
  
  배치하면서 몇몇개는 display none으로 숨겨두고 마진패딩 조절 및 float로 정렬하였는데
  또 디자인적 관점에서만 배치가 된것같은 느낌이다
  
  display none해놓은 친구들을 찾기위해 자바스크립트를 사용하지 않고 css의 hover를 쓰려고하는데
  
  클래스를 선택하는 방법을 몰라서 시간을 날렸다
  
  html에서 class = "hi bye" 랑 css에서 .hi bye{} 는 다르다는것을 인지못했다 전자는 클래스로 hi, bye 두가지를 한다는거고,
  hi나 bye 아무거나 선택해도 다됨 후자의 hi bye는 hi밑에있는 bye다
  
  ![p7](https://user-images.githubusercontent.com/48181483/55464958-24acb880-5637-11e9-869f-482dc0c6f29c.png)
  
  호버됬을때 밑에 앱솔루트된 친구들을 불러오려고했다 근데 같은 레벨의 친구들에 호버를 걸면 마우스가 이동되는 사이에 호버가 풀릴수 있어서
  부모의 영역에 호버를 줬다 이제 헤더를 고정시켜야한다 
  
  ![p8](https://user-images.githubusercontent.com/48181483/55465436-190dc180-5638-11e9-8b10-28172654c5c9.png)
  
  헤더를 고정시켰다 그랬더니 아래있는 컨테이너랑 푸터가 올라왔다
  
  
![p9](https://user-images.githubusercontent.com/48181483/55465750-c1bc2100-5638-11e9-9705-bb3dbf57f200.png)

헤더랑 컨테이너 사이에 헤더크기랑 같은 empty를 만들어 컨테이너랑 푸터가 눈에 보이기 쉽게 임시조치했다
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
 
 
  4. 문제
  5. 해결
  6. 배운것/얻은것 느낀것
  7. 배워야할 것
  
