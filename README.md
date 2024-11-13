# jetson_dxl2

## 설명

https://github.com/lsy0727/jetson_dxl2/blob/13d4d718883f3235c22dc0f9635cba69d170a6f4/main.cpp#L7-L8

line 7 : ctrl_c_pressed : 프로그램을 종료하기 위한 변수 false로 선언
line 8 : ctrl_c_pressed를 true로 변경하는 함수

https://github.com/lsy0727/jetson_dxl2/blob/eb8fa17828736c3ca8081f48469a5db8215c1145/main.cpp#L15

시그널핸들러 - ctrl_c 입력시 발생

https://github.com/lsy0727/jetson_dxl2/blob/8bd72db4ff178794b1575aca70da88095a4ecdfb/main.cpp#L20-L33

line 20 : 키보드입력 여부 확인 (키보드 미입력시 while문 반복)

line 22 : 입력받은 키를 변수 c에 저장

line 25~30 : 입력받은 키에 따라 모터(바퀴) 제어

line 32 : 설정한 속도를 다이내믹셀 모터로 보냄

https://github.com/lsy0727/jetson_dxl2/blob/9a57f46aaac4499bb9aa8744c2d1992651728a8d/main.cpp#L34-L35

line 34 : ctrl+c 입력시 ctrl_c_pressed가 line 8, 10에 의해 true로 변경되고, while문이 종료

line 35 : 원활한 제어를 위한 딜레이 부여

https://github.com/lsy0727/jetson_dxl2/blob/35c7b12e2ad4d13b3b187e755f9f45b1ac59f0c7/main.cpp#L40

프로그램 종료시 장치를 닫음

## 실행 결과

![image](https://github.com/user-attachments/assets/d0ca7ba8-1c8f-41d9-b342-60f9606f41e4)

## 고찰
1. 정지명령(s키 입력)을 입력했을 때와 프로그램을 종료(ctrl+c 입력)했을 때 바퀴를 손으로 움직일 때 느껴지는 토크차이

-> s키로 정지했을 때는 손으로 움직이지 않고, ctrl+c를 입력했을 때는 적은 힘으로도 움직일 수 있음.

이유 : s키로 정지한 경우는 바퀴의 속도가 0으로 '제어'되고 있는 상태이고, ctrl+c로 입력한 경우는 프로그램이 완전히 종료되었기 때문에 아무런 제어도 되지 않는 상태임.

2. ctrl+c를 눌렀을 때 dxl1의 코드와 결과가 다른 이유

-> 이 코드는 키보드 입력시 버퍼에 쌓이지 않고 바로 처리되기 때문에 ctrl+c를 누르면 신호 바로 처리된다.
