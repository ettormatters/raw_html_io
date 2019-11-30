# Flutter Gitpod Env
## Flutter download problem
- flutter 공식 홈페이지의 zip을 다운하면 gitpod에 업로드가 불가하다. 싸지방에서는 자료유출방지시스템이 있어서 파일업로드가 금지 되어있기 때문이다.
- 그래서 다른방식으로 linux command 를 이용하여 gitpod repo에 바로 다운로드를 해야한다.
- 아래의 사진에서 git 을 이용한 직접 다운로드가 가능하다.
![flutter git download](https://i.imgur.com/wJQ1OHr.png)

## Gitpod env $PATH problem
- 예전에 python을 이용한 주식api를 건드려 보았을때도 gitpod을 썼는데, python path때문에 애먹었던 적이 있었다.
- 그래서 workspace 위로 거슬러 올라가서 .bashrc등을 편집해보았지만 어떤 이유에선지 계속 적용이 되지 않았다.
- gitpod의 기능중에 variables라는 게 있는데 그걸 써봐도 오히려 $PATH가 리셋되버리기도 했다.
- 그래서 커맨드로 바로 PATH에 넣는 법을 찾게 되었다.
- 이렇게 매번 커맨드를 입력하면 번거롭지만, gp 커맨드로 workspace를 자동화시키면 환경을 시작할때마다 한번의 커맨드로 설정을 마칠 수 있다.
***
![1](https://i.imgur.com/JdSUud3.png)
***
![2](https://i.imgur.com/DxRwHSU.png)
***
![3](https://i.imgur.com/MTjOnQP.png)

## Web device rendering problem
- gitpod에서 flutter -d chrome 을 하면 chrome을 찾지 못하여 render를 못한다.
- 그러므로 자체 브라우저를 통해서만 rendering을 해야한다.
- 그 방법을 찾았다. https://medium.com/swlh/flutter-hot-reload-in-gitpod-101a86394527
```
flutter channel master
flutter config --enable-web
flutter doctor -v
flutter run -d web-server
```

![](https://i.imgur.com/M9QNEcR.png)
***
![](https://i.imgur.com/kOeIJqq.png)
***
![](https://i.imgur.com/plqpSt7.png)
***
![](https://i.imgur.com/g0xFtac.png)

## Further
- linux path deep
- gitpod deep
- gitpod localhost
- rendering random port exposing prob

