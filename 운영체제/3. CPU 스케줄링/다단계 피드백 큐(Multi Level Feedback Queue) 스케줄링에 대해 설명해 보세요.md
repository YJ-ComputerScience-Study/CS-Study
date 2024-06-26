## 다단계 피드백 큐(Multi Level Feedback Queue) 스케줄링에 대해 설명해 보세요.

**다단계 피드백 큐 스케줄링(MLFQ)** 은 다양한 우선순위를 가진 여러 개의 큐를 사용하여 프로세스를 관리하는 방식입니다. 선점 방식이고 프로세스의 우선순위를 동적으로 조절하며, 이전에 실행된 프로세스의 행동에 따라 우선순위를 변경합니다. 우선순위는 프로세스의 CPU 사용량이나 입출력 작업 등에 따라 조절하여, 프로세스의 처리율을 향상시킵니다. 또한, 각 큐에 RR 스케줄링을 적용해 각 우선순위의 프로세스가 공평하게 CPU를 할당받을 수 있도록 합니다.

다양한 종류의 프로세스들을 효율적으로 관리하고, 우선순위에 따라 공정한 CPU 할당을 제공해 시스템의 성능을 향상시키는 데 사용됩니다. 그러나, 구현이 복잡하고, 적절한 파라미터 설정이 필요하여 효과적인 조정이 중요합니다.

`#MLFQ`

`#동적우선순위기반선점방식`

`#공정한CPU할당`
