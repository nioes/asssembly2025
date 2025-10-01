
**3.9.1 Short Answer (단답형 및 설명형)**

1. MOV, ADD, JMP
2. 호출 규약은 함수 호출 시 인자 전달, 스택 정리, 레지스터 보존에 대한 규칙이며, 어셈블리에서는
PROTO 지시어 사용 시 적용됩니다.
3. STACK 지시어를 사용하여 스택 세그먼트의 크기를 정의합니다.
4. 어셈블러는 번역 프로그램이고, 어셈블리 언어가 언어 자체를 의미하므로, 용어 혼동입니다.
5. 리틀 엔디안은 최하위 바이트를 낮은 주소에 저장하고, 빅 엔디안은 최상위 바이트를 낮은 주소에 저장합니다. 
6. 가독성 향상 및 유지보수 용이성 때문입니다.
7. 소스 파일은 작성 코드이고, 리스팅 파일은 어셈블러가 생성한 코드, 기계어, 주소 등의 정보가 담긴 파일입니다.
8. 데이터 레이블은 변수 주소(콜론 X), 코드 레이블은 명령어 주소(콜론 O)를 나타냅니다.
9. • True (참).
• 이유: 어셈블리 언어(MASM)를 포함한 대부분의 프로그래밍 언어에서, 레이블이나 변수 같은 식별자는 문자(알파벳) 또는 특정 특수 문자로 시작해야 하며, 숫자로 시작할 수 없습니다.
10. • False (거짓).
• 이유: MASM 어셈블러에서는 16진수를 나타낼 때 값 뒤에 ** h ** 를 붙여야 합니다 ( 3Ah 또는03Ah ). 0x 접두사는 C/C++ 같은 다른 언어의 표기법입니다.
11. • False (거짓).
• 이유: 지시어(Directives, 예: .DATA, DWORD )는 ** 어셈블 타임(Assemble Time) ** 에 어셈블러에게 코드를 처리하는 방법을 지시하는 것이며, 프로그램 실행 중인 런타임에는 아무런 동작도 하지 않습니다. 런타임에 실행되는 것은 명령어(Instructions)입니다.
12. • True (참).
• 이유: 대부분의 어셈블러(MASM 포함)에서 지시어와 명령어 니모닉은 대소문자를 구분하지 않습니다 (case-insensitive).
13.레이블, 니모닉, 피연산자, 주석
14. • True (참).
• 이유: MOV 는 "Move"를 뜻하는 약어(Mnemonic)로, CPU가 실행할 데이터 전송 작업을 나타내는 명령어의 이름입니다.
15. • True (참).
• 이유: 코드 레이블 뒤의 콜론( : )은 어셈블러에게 해당 위치가 명령어가 시작되는 지점임을 알려주는 필수 문법이며, 데이터 레이블은 단순히 메모리 주소를 나타내는 변수 이름이므로 콜론을 사용하지 않습니다.
16.COMMENT * 주석 내용 *
17. 변수 주소 변경 시 모든 코드를 수정해야 하는 유지보수 문제와 가독성 저하 때문입니다.
18. ** 종료 코드(Exit Code) ** 인 ** 32비트 부호 있는 정수(SDWORD) ** 입니다.
19. ENDP 지시어입니다.
20. 프로그램의 ** 진입점(Entry Point) ** 을 지정합니다.
21. 프로시저의 원형과 매개변수 타입을 정의하여 타입 검사를 가능하게 합니다.
22. • False (거짓).
• 이유: ** 어셈블러(Assembler) ** 가 소스 파일( .asm )을 컴파일하여 오브젝트 파일( .obj )을 생성합니다. 링커(Linker)는 이 오브젝트 파일을 라이브러리와 결합하여 실행 파일( .exe )을 만듭니다.
23. • True (참).
• 이유: 리스팅 파일( .1st )에는 어셈블러가 소스 코드를 기계어로 변환한 결과와 주소 정보가 포함되므로, 어셈블러가 생성합니다.
24.• True (참).
• 이유: ** 링커(Linker) ** 의 주요 역할 중 하나는 오브젝트 파일을 필요한 ** 링크 라이브러리(Link Library) ** 와 결합하여 최종적으로 실행 가능한 파일( .exe )을 생성하는 것입니다.
25. SDWORD
26. SWORD
27. QWORD
28. BYTE
29. TBYTE


**3.9.2 Algorithm Workbench (알고리즘 작업대)**
1. VAL_DEC = 25
   VAL_BIN = 11001b
   VAL_OCT = 31o
   VAL_HEX = 19h

3. 가능합니다. 프로그램은 여러 코드 및 데이터 세그먼트를 가질 수 있습니다.
4. myBigEndian DB 12h, 34h, 56h, 78h ; (예시: 12345678h 저장 시)
5. 할 수 있습니다. 어셈블러는 음수를 2의 보수로 저장하며, 이는 어셈블러가 강력한 타입 검사를 하지 않음을 의미합니다.

6. .CODE
main PROC
ADD EAX, 5   ; 명령어 1
ADD EDX, 5   ; 명령어 2
main ENDP
END main

차이점: 두 명령어 모두 3바이트 길이지만, 두 번째 바이트(C0 대 C2)가 다릅니다.

이유: 83h는 **'정수를 레지스터/메모리에 더하라'**는 Opcode(명령 코드)이고, 세 번째 바이트 05h는 더할 값(5)입니다. 중간 바이트(C0 또는 C2)는 ModR/M 바이트로, 어떤 레지스터(EAX 또는 EDX)에 연산을 수행할지 지정하는 코드입니다. 즉, 명령어 자체는 같지만, 대상 레지스터가 다르기 때문에 기계어 코드가 달라집니다.
6. ABh, 89h, 67h, 45h
7..DATA? ; 초기화되지 않은 데이터 세그먼트
  dArray DW 120 DUP(?)


8..DATA
  charArray BYTE 'a', 'b', 'c', 'd', 'e'

9.minVal SDWORD -2147483648

10.wArray WORD 10, 20, 30
   
11. favColor BYTE "Blue", 0

12. dArray SDWORD 50 DUP(?)

13. myString BYTE 500 DUP("TEST")

14. bArray BYTE 20 DUP(0)

15. Lowest Address: 21h, Next: 43h, Next: 65h, Highest Address: 87h


**3.10 Programming Exercises**

1. Integer Expression Calculation

• 핵심: ADD EAX, EBX → ADD ECX, EDX → SUB EAX, ECX 순서로 계산합니다.

2. Symbolic Integer Constants

• 핵심:.CONST 섹션에서 SUN = 0 와 같이 상수를 정의하고,. DATA 섹션에서 weekArray DWORD SUN, MON, ... 와 같이 배열을 초기화합니다.

3. Data Definitions

• 핵심: Table 3-2의 모든 타입을 .DATA 에 정의하고 적절한 값으로 초기화합니다. (예: varSDWORD SDWORD -100, varREAL4 REAL4 1.23 ).

4. Symbolic Text Constants
• 핵심: .CONST 섹션에서 MSG_HELLO EQU <"Hello"> 와 같이 문자열 리터럴 상수를 정의하고, .DATA 에서 helloString BYTE MSG_HELLO, 0 와 같이 사용합니다.

5. Listing File for AddTwoSum

• 핵심: AddTwoSum 코드를 어셈블러로 컴파일하여 .1st 파일을 생성한 후, 파일 내의 각 명령어에 해당하는 16진수 바이트 코드를 Opcode, 피연산자 등으로 분석합니다.

6. AddVariables Program

• 핵심: DWORD → QWORD 및 EAX → RAX 로 변경.

• 오류/해결: 32비트 환경에서 64비트 레지스터 사용 시 오류가 발생하며, 64비트 어셈블러 환경을
사용하도록 변경하여 해결해야 합니다.
