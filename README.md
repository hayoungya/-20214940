# 오픈소스 과제 20214940
양하영입니다.

# 리눅스 프로세스 관리 명령어

## 주요 명령어 요약

| 명령어 | 설명 | 주요 옵션 | 사용 예시 |
| ------ | ---- | -------- | -------- |
| `top`  | 실시간 시스템 모니터링 | `-u [사용자]`: 특정 사용자 프로세스만 표시<br>`-n [횟수]`: 지정된 횟수만큼 갱신 후 종료 | `top`<br>`top -u username`<br>`top -n 10` |
| `ps`   | 현재 실행 중인 프로세스 목록 | `-e`: 모든 프로세스 표시<br>`-u [사용자]`: 특정 사용자 프로세스만 표시<br>`-o [필드 목록]`: 출력 형식 지정 | `ps -e`<br>`ps -u username`<br>`ps -o pid,comm,%cpu,%mem` |
| `jobs` | 현재 쉘 세션의 백그라운드 및 정지된 작업 목록 | `-l`: PID를 포함한 작업 목록 표시 | `jobs`<br>`jobs -l` |
| `kill` | 특정 프로세스에 시그널을 보내 종료 또는 제어 | `-s [시그널] [PID]`: 특정 시그널 전송<br>`-9 [PID]`: 프로세스를 강제 종료 | `kill 1234`<br>`kill -9 1234`<br>`kill -s SIGSTOP 1234` |


## top 명령어
top 명령어는 실시간으로 시스템의 상태와 실행 중인 프로세스들을 모니터링할 수 있는 도구입니다. CPU, 메모리 사용량 및 프로세스 목록을 요약하여 보여줍니다.
- 시스템의 상태를 전반적으로 가장 빠르게 파악 가능(CPU, Memory, Process)
- 옵션 없이 입력하면 interval 간격(기본 3초)으로 화면을 갱신하며 정보를 보여줌

## 주요 기능

| 기능 | 설명 |
| ---- | ---- |
| 실시간 프로세스 모니터링 | CPU, 메모리 사용량, 실행 중인 프로세스 정보 제공 |
| 프로세스 정렬 | CPU 사용량(`P`), 메모리 사용량(`M`), 프로세스 ID(`N`), 실행 시간(`T`) 등 다양한 기준으로 프로세스를 정렬 가능 |
| 특정 사용자 프로세스 필터링 | `-u` 옵션으로 특정 사용자의 프로세스만 표시 |
| 프로세스 종료 | `k` 키를 눌러 특정 PID를 입력해 프로세스 종료 가능 |
| 반복 실행 설정 | `-n` 옵션으로 지정된 횟수만큼 갱신 후 종료 |

## top 실행 전 옵션
- 순간의 정보를 확인하려면 -b 옵션 추가(batch 모드)
## top 실행 후 명령어
- shift + p : CPU 사용률 내림차순
- shit + m : 메모리 사용률 내림차순
- shift + t : 프로세스가 돌아가고 있는 시간 순
- k : kill. k 입력 후 PID 번호 작성. signal은 9
- f : sort field 선택 화면 -> q 누르면 RES순으로 정렬
- a : 메모리 사용량에 따라 정렬
- b : Batch 모드로 작동
- 1 : CPU Core별로 사용량 보여줌
## ps와 top의 차이점
- ps는 ps한 시점에 proc에서 검색한 cpu 사용량
- top은 proc에서 일정 주기로 합산해 cpu 사용율 출력-n : top 실행 주기 설정(반복 횟수)


## ps 명령어

ps 명령어는 현재 실행 중인 프로세스의 스냅샷을 제공합니다. 다양한 옵션을 통해 필요한 프로세스 정보를 필터링하고 포맷할 수 있습니다.

### 주요 기능

| 기능 | 설명 |
| ---- | ---- |
| 프로세스 목록 출력 | `ps -e`로 모든 실행 중인 프로세스를 표시 |
| 특정 프로세스 필터링 | `-u` 옵션을 사용하여 특정 사용자 프로세스만 표시 |
| 포맷 지정 | `-o` 옵션을 사용하여 출력 형식을 사용자 지정 가능 |

## ps 옵션
<img width="481" alt="image" src="https://github.com/hayoungya/-20214940/assets/170169296/57fdd194-e209-4313-bd2e-c41c8cf37811">

## ps 출력 항목
<img width="474" alt="image" src="https://github.com/hayoungya/-20214940/assets/170169296/21880e7a-217b-43e8-a774-b6ccac790269">

## jobs 명령어

jobs 명령어는 현재 쉘 세션에서 실행 중인 백그라운드 및 정지된 작업 목록을 표시합니다.

### 주요 기능

| 기능 | 설명 |
| ---- | ---- |
| 작업 목록 표시 | 현재 쉘에서 실행 중인 모든 작업을 나열 |
| 작업 상태 표시 | 각 작업의 현재 상태(실행 중, 정지 등)를 보여줌 |





