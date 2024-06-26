## HTTPS에서 사용하는 암호화 방식을 설명해 보세요.

HTTPS는 보안 계층의 암호화 프로토콜인 **SSL/TLS에서 암호화**가 이뤄집니다. 사용하는 암호화 방식으로는 대칭 키 암호화 방식과 공개 키 암호화 방식이 있습니다.

**대칭 키 암호화 방식**은 데이터의 송신자와 수신자 모두 대칭 키를 이용해 데이터를 암호화 및 복호화하는 방식입니다.

반면, **공개 키 암호화 방식**은 공개 키로 데이터를 암호화하고 비밀 키로 데이터를 복호화하는 방식입니다.

**SSL/TLS**에서는 **대칭 키로 데이터를 암호화**하는데, 이때 대칭 키가 공개되므로 데이터가 유출되는 것을 막기 위해 **대칭 키를 공개 키 암호화 방식으로 암호화**합니다.

`#HTTPS암호화는SSL/TLS에서이뤄져`

`#SSL/TLS는대칭키로데이터를암호화`

`#그런데이제대칭키를공개키암호화방식으로암호화하는..`

`#암호화방식둘다사용`

> SSL/TLS 암호화에서 대칭 키 암호화 방식과 공개 키 암호화 방식이 모두 사용됨을 숙지해야 함. 특히, 실제 데이터를 암호화 및 복호화하는 것은 대칭 키이고, 대칭 키를 보호하기 위해 공개 키 암호화 방식이 사용된다는 것을 언급하기!
