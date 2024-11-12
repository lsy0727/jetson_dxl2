# jetson_dxl2

# 설명

https://github.com/lsy0727/jetson_dxl2/blob/13d4d718883f3235c22dc0f9635cba69d170a6f4/main.cpp#L7-L8

line 7 : ctrl_c_pressed : 프로그램을 종료하기 위한 변수 false로 선언
line 8 : ctrl_c_pressed를 true로 변경하는 함수

https://github.com/lsy0727/jetson_dxl2/blob/eb8fa17828736c3ca8081f48469a5db8215c1145/main.cpp#L15

시그널핸들러 - ctrl_c 입력시 발생

https://github.com/lsy0727/jetson_dxl2/blob/8bd72db4ff178794b1575aca70da88095a4ecdfb/main.cpp#L20-L33

line 20 : 키보드입력 여부 확인 (키보드 미입력시 while문 반복)

line 22 : 입력받은 키를 변수 c에 저장

line 25~30 : 입력받은 키에 따라 모터(바퀴) 제어
