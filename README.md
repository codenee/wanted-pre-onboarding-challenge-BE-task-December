- (1) 동기와 비동기 프로그래밍에 대한 차이점을 설명해주세요.
    
    동기(Synchronous)
        -현재 작업의 응답이 끝남과 동시에 다음 작업이 요청된다.
        -함수를 호출하는 곳에서 호출되는 함수가 결과를 반환할 때까지 기다린다.
        -작업 완료 여부를 계속해서 확인한다.
        -요청과 응답의 순서가 보장된다.

    비동기(ASynchronous)
        -현재 작업의 응답이 끝나지 않은 상태에서 다음 작업이 요청된다.
        -함수를 호출하는 곳에서 결과를 기다리지 않고, 다른 함수(callback)에서 결과를 기다린다.
        -작업 완료 여부를 확인하지 않는다. (싱글쓰레드에서 비동기적인 프로그래밍을 한다고 해서 멀티쓰레드처럼 동시 다발적인 실행이 가능해지는 것은 아니다.)
        -요청과 응답의 순서가 보장되지 않는다.

- (2) 블로킹과 논블로킹의 차이점을 설명해주세요.
    블록킹 (Blocking) 
        -자신의 수행결과가 끝날 때까지 제어권을 갖고 있는 것이다.
        -Request를 보낸 Thread는 Response가 도착하기 전까지는 아무것도 하지 못하는 Block 상태가 됨을 의미한다.

    논블록킹 (non-blocking)
        -자신이 호출되었을 때 제어권을 자신을 호출한 쪽으로 넘기고 자신을 호출한 쪽에서 다른 일을 할 수 있도록 하는 것이다.
        -Response를 기다리지 않고 있으니 Request를 보낸 Thread는 다른 일을 할 수 있다. Request를 보내고 Response를 기다리지 않고 다른 일을 하는 이러한 상태를 Non Block 상태라로 한다.

- (3) 본인이 주로 사용하는 언어에서 비동기 프로그래밍을 사용하는 방법을 설명해주세요.
    C++에서 비동기 프로그래밍을 사용하기 위해 std::thread를 사용하여 스레드 기반 비동기적 실행을 구현하고 있습니다.

- (4) 메세지 큐를 쓰는 이유에 대하여 2가지 예시를 서술해주세요.
    메시지 큐는 프로세스 또는 프로그램 간에 데이터를 교환할 때 사용하는 통신 방법 중에 하나로, 메시지 지향 미들웨어(Message Oriented Middleware:MOM)를 구현한 시스템을 의미한다. 메시지 지향 미들웨어란 비동기 메시지를 사용하는 응용 프로그램들 사이에서 데이터를 송수신하는 것을 의미한다

    메시지 큐를 사용하는 2가지 예시는 다음과 같다.
    
    1. 이메일 전송
      메시지 큐에 들어오는 메시지 수가 급증하는 경우 메시징 시스템이 잠시 다운되어도 각 서비스에는 직접적인 영향을 미치지 않는다. 메세지 큐에 저장되어 있기 때문에 데이터 손실를 방지할 수 있다.

    2. 블로그 포스팅
      고용량의 이미지와 텍스트를 처리하기 위해 사용자가 업로드한 모든 이미지를 게시 과정에서 즉각 처리하는 것이 아닌, 사후 처리하며 최적화가 가능하다. 고용량 데이터 전송은 서버 부하를 많은 작업이다. 메시지 큐를 사용하면 서비스 응답 시간을 저해하지 않으면서 사용자들에게 유연성을 제공할 수 있다.

    메시지 큐는 메시지를 임시로 저장하는 간단한 버퍼라고 생각하면 된다. 메시지를 전송 및 수신하기 위해 중간에 메시지 큐를 두는 것이다. 서버에서 실행되는 일부 작업을 메시지 큐를 사용함으로 웹 어플리케이션의 성능을 향상시킬 수 있다.

- (5) 본인이 작성한 서버 코드가 있는 github repo 주소를 제출해주세요. (CRUD 기능을 모두 포함하여야 하며, 서버에 대한 설명을 README에 작성해주시면 더욱 좋습니다.) 
    https://github.com/codenee/Pre-onboarding_challenge_backend
    
- (6 - Optional) 해당 수업을 통해 꼭 배우고 싶은 주제 또는 지식이 있다면 자유롭게 서술해주세요.