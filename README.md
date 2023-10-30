# mortor-board-release
모터 보드 릴리즈

# 생산 단계 설정 절차

## RS485 설정
RS485 통신 속도와 ID를 설정한다.

### rs485baud (rs485 통신 속도 설정)
> 설정 값 읽기:

    rs485baud

> 설정 값 쓰기:

    rs485baud [data]

data로 9600/14400/19200/38400/57600/115200 중 하나의 값을 설정한다.

### rs485id (rs485 ID 설정)
> 설정 값 읽기:

    rs485id

> 설정 값 쓰기:

    rs485id [id]

id로 0 ~ 255 사이의 값을 설정한다.

## 동작 전압 설정
줌 및 포커스 모터 출력 전압(0V ~ 12V)을 설정한다.

### zin1 (zoom wide 방향 모터 회전)
> 모터 회전:

    zin1 1

> 모터 정지:

    zin1 0

모터 회전 후 **반드시 정지**를 해야 한다.

### zin2 (zoom tele 방향 모터 회전)
> 모터 회전:

    zin2 1

> 모터 정지:

    zin2 0

모터 회전 후 **반드시 정지**를 해야 한다.

### zin1d (zin1 출력 설정: 0 ~ 101)
> 설정 값 읽기:

    zin1d

> 설정 값 쓰기:

    zin1d [data]

data로 0 ~ 101 사이의 값을 설정한다.

### zin2d (zin2 출력 설정: 0 ~ 101)
> 설정 값 읽기:

    zin2d

> 설정 값 쓰기:

    zin2d [data]

data로 0 ~ 101 사이의 값을 설정한다.

### fin1 (focus near 방향 모터 회전)
> 모터 회전:

    fin1 1

> 모터 정지:

    fin1 0

모터 회전 후 **반드시 정지**를 해야 한다.

### fin2 (focus far 방향 모터 회전)
> 모터 회전:

    fin2 1

> 모터 정지:

    fin2 0

모터 회전 후 **반드시 정지**를 해야 한다.

### fin1d (fin1 출력 설정)
> 설정 값 읽기:

    fin1d

> 설정 값 쓰기:

    fin1d [data]

data로 0 ~ 101 사이의 값을 설정한다.

### fin2d (fin2 출력 설정)
> 설정 값 읽기:

    fin2d

> 설정 값 쓰기:

    fin2d [data]

data로 0 ~ 101 사이의 값을 설정한다.


## 모터 동작 제한 설정
포텐셜 미터가 설치된 줌 및 포커스 모터의 이동 범위를 제한하는 설정을 한다.

포텐셜 미터가 설치되어 있지 않은 경우, 이 설정을 진행하면 오동작할 수 있다.

### zadc (zoom 포텐셜 미터 값을 읽는다.)
> zoom 포텐셜 미터 읽기:

    zadc
    
### fadc (focus 포텐셜 미터 값을 읽는다.)
> focus 포텐셜 미터 읽기:

    fadc

### wide (zoom wide 동작을 한다.)
> zoom wide 동작 (동작 전 zstop을 해야한다.):

    wide

### tele (zoom tele 동작을 한다.)
> zoom tele 동작 (동작 전 zstop을 해야한다.):

    tele

### zstop (zoom 모터를 중지 한다.)
> zoom 동작 중지:

    zstop

wide/tele 동작 후 **반드시 정지**를 해야 한다.

### near (focus near 동작을 한다.)
> focus near 동작 (동작 전 fstop을 해야한다.):

    near
    
### far (focus far 동작을 한다.)
> focus far 동작 (동작 전 fstop을 해야한다.):

    far

### fstop (focus 모터를 중지 한다.)
> focus 동작 중지:

    fstop

near/far 동작 후 **반드시 정지**를 해야 한다.

### [zwide]-[margine]-[zlwide]-[moving range]-[zltele]-[margine]-[ztele]
> 
    zoom 설정시 각 설정 항목에 대한 개념적인 위치 정보

### zlim (zoom 이동 범위 제한 사용 유무를 설정한다.)
> 설정 값 읽기:

    zlim

> 설정 값 쓰기:

    zlim [data]

data로 0(off) 또는 1(on) 중 하나의 값을 설정한다.

### zwide (최대 zoom wide 위치의 포텐셜 미터 값을 설정한다.)
> 설정 값 읽기:

    zwide

> 설정 값 쓰기:

    zwide [data]

data로 wide 동작(끝까지 이동)후 zadc의 출력 값을 설정한다.

### ztele (최대 zoom tele 위치의 포텐셜 미터 값을 설정한다.)
> 설정 값 읽기:

    ztele

> 설정 값 쓰기:

    ztele [data]

data로 tele 동작(끝까지 이동)후 zadc의 출력 값을 설정한다.

### zlwide (zoom wide의 제한된 포텐셜 미터 값을 설정한다.)
> 설정 값 읽기:

    zlwide

> 설정 값 쓰기:

    zlwide [data]

data로 wide 동작시 제한할 포텐셜 미터 값(zwide에서 margine 크기를 가감한)을 설정한다.


### zltele (zoom tele의 제한된 포텐셜 미터 값을 설정한다.)
> 설정 값 읽기:

    zltele

> 설정 값 쓰기:

    zltele [data]

data로 tele 동작시 제한할 포텐셜 미터 값(ztele에서 margine 크기를 가감한)을 설정한다.


### [fnear]-[margine]-[flnear]-[moving range]-[flfar]-[margine]-[ffar]
> 
    focus 설정시 각 설정 항목에 대한 개념적인 위치 정보

### flim (focus 이동 범위 제한 사용 유무를 설정한다.)
> 설정 값 읽기:

    flim

> 설정 값 쓰기:

    flim [data]

data로 0(off) 또는 1(on) 중 하나의 값을 설정한다.

### fnear (최대 focus near 위치의 포텐셜 미터 값을 설정한다.)
> 설정 값 읽기:

    fnear

> 설정 값 쓰기:

    fnear [data]

data로 near 동작(끝까지 이동)후 fadc의 출력 값을 설정한다.

### ffar (최대 focus far 위치의 포텐셜 미터 값을 설정한다.)
> 설정 값 읽기:

    ffar

> 설정 값 쓰기:

    ffar [data]

data로 far 동작(끝까지 이동)후 fadc의 출력 값을 설정한다.

### flnear (focus near의 제한된 포텐셜 미터 값을 설정한다.)
> 설정 값 읽기:

    flnear

> 설정 값 쓰기:

    flnear [data]

data로 near 동작시 제한할 포텐셜 미터 값(fnear에서 margine 크기를 가감한)을 설정한다.

### flfar (focus far의 제한된 포텐셜 미터 값을 설정한다.)
> 설정 값 읽기:

    flfar

> 설정 값 쓰기:

    flfar [data]

data로 far 동작시 제한할 포텐셜 미터 값(ffar에서 margine 크기를 가감한)을 설정한다.

