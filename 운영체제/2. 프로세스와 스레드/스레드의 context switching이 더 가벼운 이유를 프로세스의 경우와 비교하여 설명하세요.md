# 스레드의 context switching이 더 가벼운 이유를 프로세스의 경우와 비교하여 설명하세요.

서로 다른 프로세스는 서로 다른 메모리 주소 공간을 가집니다. 하지만, 같은 프로세스에 속하는 서로 다른 스레드는 소속된 프로세스의 스택 영역을 제외한 모든 메모리 주소 공간을 공유합니다.

프로세스 컨텍스트 스위칭의 경우에는 새로 실행되는 프로세스가 기존에 실행되는 프로세스의 메모리 주소 공간에 침범하면 안 되기 때문에

1. 실행 중이었던 프로세스의 상태를 백업하고,
2. cache를 비우고,
3. TLB를 비우고,
4. MMU 설정을 변경

하는 작업을 거치게 됩니다.

반면, 스레드 컨텍스트 스위칭의 경우에는 메모리 주소 공간이 바뀌지 않기 때문에 cache와 TLB를 비우고 MMU 설정을 변경하는 작업은 수행하지 않습니다. 따라서 스레드 컨텍스트 스위칭은 프로세스 컨텍스트 스위칭에 비해 상대적으로 빨리 끝나는 가벼운 작업이 됩니다.

