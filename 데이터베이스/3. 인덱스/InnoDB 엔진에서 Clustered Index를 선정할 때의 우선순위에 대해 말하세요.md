# InnoDB 엔진에서 Clustered Index를 선정할 때의 우선순위에 대해 말하세요.

먼저 primary key가 있다면 1순위로 primary key를 클러스터링 인덱스로 선택합니다.

만약 primary key가 없다면, UNIQUE + NOT NULL 제약조건이 걸린 컬럼을 선택합니다.

두 경우 모두 없다면, “GEN_CLUST_INDEX”라는 컬럼을 내부적으로 추가한 후, 클러스터링 인덱스로 선택합니다. 이 컬럼은 증가되며 자동으로 유니크한 값을 가집니다. 이때, 이 컬럼은 쿼리에서 명시적으로 사용할 수는 없습니다.