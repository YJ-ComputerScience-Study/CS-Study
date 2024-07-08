# Array와 ArrayList의 차이점을 말해주세요.

1. **길이 조정 여부**
    
    Array는 **고정 길이**이고, 객체 생성 후에는 길이를 변경할 수 없습니다. 이에 반해 ArrayList는 **가변 길이**입니다. 초기화 시에 크기를 표시하지 않습니다. ArrayList size를 나타내는 capacity 변수가 존재하며 설정 값을 넘으면 배열 크기를 1.5배로 증가시킵니다.
    
2. **성능**
    
    Array는 초기화 시 메모리에 할당되는 반면, ArrayList는 데이터 추가나 삭제 시에 메모리를 재할당하기에 Array보다 속도가 느립니다.
    
3. **타입**
    
    Array는 primitive type과 Object 모두 저장 가능하지만, ArrayList는 primitive type을 저장할 수 없고 오로지 Object만 저장할 수 있습니다.
    
4. **다차원 여부**
    
    Array는 다차원이 가능하지만, ArrayList는 항상 단일 차원입니다.