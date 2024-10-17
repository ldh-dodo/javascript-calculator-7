# javascript-calculator-precourse


## 입출력 요구 사항

### 입력
- 구분자와 양수로 구성된 문자열

### 출력
- 덧셈 결과
```
결과 : 6
```

### 실행 결과 예시
```
덧셈할 문자열을 입력해 주세요.
1,2:3
결과 : 6
```

## 기능 요구 사항

1. **문자열 입력 안내 텍스트 출력 및 입력** 
    - `@woowacourse/mission-utils` 에서 제공하는 `Console` API를 사용하여 구현
    - `Console.readLineAsync()`와 `Console.print()`를 활용
    - 문자열 입력을 안내하는 텍스트는 [실행 결과 예시](#실행-결과-예시)를 참고
2. **커스텀 구분자 유무 판단 및 삭제**
    - 커스텀 구분자는 문자열 앞부분의 `"//"와 "\n"` 사이에 위치하는 문자를 커스텀 구분자로 사용
        - 예시 : "//;\n1;2;3"
    - 커스텀 구분자가 존재한다면 기본 구분자(: ,)에 추가하여 함께 관리하고, 기존 문자열에서 삭제한다.
        - 예시 : "//;\n1;2;3" -> "1;2;3"
3. **입력이 올바른지 확인**
    - 잘못된 값이 입력되었다면, 에러 메시지와 함께 `Error`를 발생시키고 애플리케이션을 종료한다
    - 올바른 입력은 [실행 결과 예시](#실행-결과-예시)를 참고
    - `입력 조건`은 다음과 같다.
        - 짝수 인덱스의 문자가 양수인지 검사한다.
        - 홀수 인덱스의 문자가 구분자에 포함되는지 검사한다.
        - 위의 조건이 충족되면 올바른 입력이라고 간주한다.
    - 양수가 하나만 입력되었을 때는 에러를 발생시켜야 할지, 덧셈 결과를 출력해야할지 고민해보기
        - 테스트 결과, 양수 하나일 때는 올바른 결과 반환
4. **양수 추출 후 덧셈**
    - 입력이 올바르다면, 양수는 문자열의 짝수 번째 인덱스에 위치. 이 양수들을 추출하여 더한다
    - ""가 입력되었을 때의 덧셈 결과는 0
5. **덧셈 결과 출력**
    - `Console.print()`를 활용
    - 덧셈 결과 출력은 [실행 결과 예시](#실행-결과-예시)를 참고