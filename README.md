## 리눅스 명령어들에 대하여

### TOP명령어

>top 명령어는 현재 OS의 상태를 나타내주는 명령어입니다. 메모리 사용량, CPU 사용량 등을 나타내주며 top을 실행하는 동안에는 주기적인 업데이트로 실시간에 근접한 내용을 보여줍니다.

![op1](https://github.com/adfxi/-sw-2-/assets/171476230/4ed941d2-1a7b-4300-bfd9-37043b69b9e1)
(top 실행결과)

**요약 정보(top명령어의 출력)**

* 시스템 시간 및 업타임: 현재 시간, 시스템이 시작된 이후의 경과 시간.
* 사용자 세션 정보: 현재 로그인한 사용자 수.
* 로드 애버리지 (Load Average): 1, 5, 15분 동안의 시스템 평균 부하.
* 작업 상태 (Tasks): 총 프로세스 수, 실행 중, 대기 중, 중단된 프로세스 수.
* CPU 상태 (CPU Usage): CPU 사용률을 사용자(user), 시스템(system), 대기(wait), 공(idle) 등의 상태로 나눠서 표시.
* 메모리 사용 (Memory Usage): 총 메모리, 사용 중, 사용 가능한 메모리, 버퍼/캐시된 메모리.
* 스왑 메모리 (Swap Usage): 스왑 메모리의 총량, 사용량, 사용 가능량

**top의 키 명령어**

* h: 도움말 표시.
* q: top 종료.
* z: 색상/단색 모드 전환.
* u: 특정 사용자의 프로세스만 표시.
* k: 프로세스 종료 (PID를 입력해야 함).
* r: 프로세스의 우선순위 변경 (PID와 nice 값을 입력해야 함).
* P: CPU 사용률 기준으로 정렬.
* M: 메모리 사용률 기준으로 정렬.
* T: 실행 시간 기준으로 정렬.
* 1: 각 CPU의 개별 사용량 표시.

--------------------------------------------------------------------------------------------------------

### ps명령어

>ps 명령어는 Process State의 약자로 현재 실행 중인 프로세스와 상태를 출력하는 명령어입니다.

![image](https://github.com/adfxi/-sw-2-/assets/171476230/3f40923b-820e-4c5e-a724-25dba2d971c9)
(ps -efl 실행결과)

**요약정보(ps명령어의 출력)**

* PID: 프로세스 ID.
* USER: 프로세스를 실행한 사용자.
* %CPU: CPU 사용률.
* %MEM: 메모리 사용률.
* VSZ: 가상 메모리 사용량 (KB).
* RSS: 실제 메모리 사용량 (KB).
* TTY: 터미널 타입.
* STAT: 프로세스 상태 (R: 실행 중, S: 대기 중, D: 중단 불가능 대기, T: 멈춤, Z: 좀비).
* START: 프로세스 시작 시간.
* TIME: 누적 CPU 사용 시간.
* COMMAND: 실행된 명령어와 인자.

**ps의 키 명령어**

* a: 터미널에 관계없이 모든 사용자의 프로세스를 보여줌.
* u: 사용자 중심 형식으로 보여줌.
* x: 터미널에 연결되지 않은 프로세스도 포함.
* e: 모든 프로세스를 보여줌.

--------------------------------

### jobs명령어

>jobs 명령어는 백그라운드로 실행된 프로그램이나 실행한 프로그램에 대해서 확인하는 명령어 입니다.

![image](https://github.com/adfxi/-sw-2-/assets/171476230/c563b214-b091-4873-882a-346947a37bf9)

(jobs 실행결과)

**요약정보(jobs명령어의 출력)**

* Job ID: 각 작업의 고유 ID. 작업 앞에 % 기호가 붙습니다.
* 상태 (State): 작업의 현재 상태. 일반적인 상태는 다음과 같습니다:
* Running: 작업이 실행 중.
* Stopped: 작업이 일시 중지됨.
* Done: 작업이 완료됨.
* 명령어 (Command): 작업을 시작한 명령어.

**jobs의 키 명령어**

* &: 명령어 뒤에 붙여서 작업을 백그라운드에서 실행.
* bg: 일시 중지된 작업을 백그라운드에서 재개.
* fg: 백그라운드 또는 일시 중지된 작업을 포어그라운드로 가져오기.
* kill: 작업을 종료.

***ps와 top 비교***

| 특징                  | ps                                     | top                                      |
|-----------------------|-------------------------------------------|---------------------------------------------|
| 기본 기능        | 현재 실행 중인 프로세스의 스냅샷 제공     | 실행 중인 프로세스의 실시간 업데이트 정보 제공 |
| 사용 사례       | 특정 시점의 프로세스 상태 확인             | 지속적으로 시스템 성능과 프로세스 상태 모니터링 |
| 출력 형식      | 명령 실행 시점의 정적 정보 출력             | 실시간으로 갱신되는 동적 정보 출력             |
| 주요 출력 정보    | PID, USER, %CPU, %MEM, VSZ, RSS, TTY, STAT, COMMAND | PID, USER, PR, NI, VIRT, RES, SHR, S, %CPU, %MEM, TIME+, COMMAND |
| 옵션              | 다양한 옵션을 통해 사용자 정의 출력 가능   | 제한된 옵션, 주로 실시간 인터랙티브 명령 제공  |
| 인터랙티브 기능  | 없음                                       | 키보드 입력을 통한 실시간 상호 작용 가능        |
| 실시간 모니터링   | 불가능                                     | 가능                                         |
| 시스템 부하      | 낮음                                       | 상대적으로 높음                               |
| 유용한 상황     | 특정 프로세스의 상태를 스냅샷으로 확인할 때 | 실시간으로 시스템 전체의 성능을 모니터링할 때   |
-------------------

### kill명령어

> kill 명령어는 실행 중인 프로세스를 종료하거나 신호를 보내는 데 사용됩니다.

![image](https://github.com/adfxi/-sw-2-/assets/171476230/7eec3951-1aa9-4be7-a6ef-6aceda6cca9f)
(kill signal)

**요약정보(kill명령어의 주요 신호)**

* SIGTERM (15): 기본 신호로, 프로세스를 정상적으로 종료하라는 요청.
* SIGKILL (9): 즉시 프로세스를 종료하는 신호. 프로세스가 종료를 거부할 수 없으며, 강제로 종료.
* SIGHUP (1): 프로세스가 터미널과의 연결을 잃었음을 알리는 신호.
* SIGINT (2): 인터럽트 신호로, 일반적으로 Ctrl+C에 의해 발생.
* SIGSTOP (19): 프로세스를 일시 중지하는 신호.
* SIGCONT (18): 일시 중지된 프로세스를 재개하는 신호.
* [추가적인 시그널 번호 의미](https://passing-story.tistory.com/entry/Linux-kill-%EC%8B%9C%EA%B7%B8%EB%84%90-%EC%A2%85%EB%A5%98-kill-%EC%8B%9C%EA%B7%B8%EB%84%90-%EB%9C%BB, "네이버 블로그")

***kill의 주의 사항***

**루트 권한 필요: 일부 시스템 프로세스나 다른 사용자의 프로세스를 종료하려면 루트 권한이 필요합니다.**

**데이터 손실 위험: SIGKILL 신호는 프로세스를 즉시 종료하므로, 데이터 손실 위험이 있습니다. 가능하면 먼저 SIGTERM 신호를 사용하여 프로세스가 정상적으로 종료할 수 있는 기회를 주는 것이 좋습니다.**
