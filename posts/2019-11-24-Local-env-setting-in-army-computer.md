# Local env setting in army computer
## Information Education Room
군대 컴퓨터들이 모여있는 곳을 정보화교육장이라고 부른다.  
하루에 지정된 시간대에 2시간을 사용할 수 있다.  
내가 속한 본부소대 같은 경우에는 출근 전과 점심 시간, 퇴근 후에 사용할 수 있다.  
모니터는 21inch정도 되고, 성능은 ... 답이 없다.  
파일업로드를 막는 프로그램과 껐다키면 리셋되는 프로그램도 있다.  
타이머가 돌아가는 java프로그램도 항상 돌아간다.  
나중에 파일업로드를 이 프로그램들을 해킹하는 포스팅도 할 예정이다.  
## Situation and Problem and Idea
1. Gitpod이라는 online 개발환경을 찾아서 잘 사용하고 있었다. 
2. 하지만 browser에 rendering을 하는 데에 사소한 제약들이 생겼다.
    1. port가 열렸다 닫혔다 random하게 발생하는 문제
    2. chrome브라우저가 아닌 gitpod 내장 브라우저로서 띄워야 하는 문제
3. gitpod에 file uploading을 자유롭게 못하도록 프로그램이 걸려있는것도 문제였다.
4. terminal이 local network에 연결되지 않는 문제
5. 지금 위와 같은 문제들을 비롯하여 기억이 나지 않는 여러 문제들을 gitpod에서 해결하는 방법을 찾아 나가고 있던 상황
```
>> idea
그냥 desktop에 local 환경을 매번 빠르게 구축하는게 나을수도 있겠다. (매번 리셋되니까)
테스트해봐야지.
```
## Testing
https://zetawiki.com/wiki/%EC%9C%88%EB%8F%84%EC%9A%B0_Chocolatey_%EC%84%A4%EC%B9%98

https://chocolatey.org/packages/vscode

https://chocolatey.org/packages/git.install

https://chocolatey.org/packages/nodejs-lts

```
@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
```
command(관리자)에서 위의 코드를 입력한다.  
그럼 choco가 깔린다.  
choco는 npm같은거라고 보면된다.  
```
refreshenv
```
를 통해 컴퓨터를 껐다키지 않고 환경변수를 갱신한다.  
위 명령어는 관리자권한이 있어야 한다.  
```
choco install vscode
```
```
choco install git.install
```
```
choco install nodejs-lts
```
위와 같은 코드들을 통해 환경을 구축한다.  
인터넷이 느려서 생각보다 오래걸린다. 5~10분.  
참고로 정보화교육장에서는 nodejs 오피셜 홈페이지를 막아놨다.  
이유는 모르겠다. 아무튼 막아놨다.  
그래서 오페라 vpn으로 우회해서 들어가기도 하는데,  
그냥 choco 로 설치한다.  
## Feedback and Conclusion
1. choco는 정말 재밌고 편하다. 윈도우를 멋있게 만들어주는 느낌이다. 나중에 더 깊게 알아봐야 겠다.
2. desktop과 vscode를 사용하는 환경이 역시나 좋다. gitpod보단.
3. git 의 cmd credential 을 지워줘야 할 것만 같은 찝찝함이 있다. 누구나 쓸 수 있는 컴퓨터 니까 누군가 내 git으로 commit 을 할수도 있다는 여기선 상상도 할수없는 일인데, 그냥 찝찝하다.
4. 설치하는데 생각보다 오래걸린다.
5. 오래걸려서 매번 이렇게 하는게 시간을 잡아먹는다. 그래서 별로 안내키고 그냥 gitpod으로 할때가 많다.
6. gitpod이 정말 불편해지면 local환경말고 외장하드를 이용한 windows to go 도 시도해봐야 겠다. 내 군생활은 많이 남았기 때문이다.