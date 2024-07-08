# thread-safe�� �÷��� Ŭ�������� ������ �������?

thread-safe�� Collection���� ũ�� **Synchronized Collection**�� **Concurrent Collection**�� �����մϴ�.

### Synchronized Collection (����ȭ �÷���)

���������� �޼��忡 **synchronized Ű����**�� �ɷ� �ֱ� ������ �� ���� �� �����常 ������ �� ����� �����մϴ�.

| �÷��� ���� | �÷��� |
| --- | --- |
| List | Vector |
| Map | HashTable |
| Collections.synchronizedXXX | synchronizedHashMap, HashSet, ArrayList��.. |

### Concurrent Collection (���� �÷���)

**������ �����ϴ� ��θ� �Ϸ�ȭ**���� ������ �������� Ȯ���մϴ�.


| �÷��� ���� | �÷��� |
| --- | --- |
| List | CopyOnWriteArrayList |
| Map | ConcurrentMap, ConcurrentHashMap |
| Set | CopyOnWriteArraySet |
| SortedMap | ConcurrentSkipListMap |
| SortedSet | ConcurrentSkipListSet |
| Queue | BlockingQueue, ConcurrentLinkedQueue |

---

#### �߰� ����

##### ConcurrentHashMap

����ȭ �÷��ǿ����� ��� ���꿡�� **�� �ϳ��� ��**�� ����Ͽ� �� ������ �ϳ��� �����常�� �ش� �÷����� ����� �� �ֵ��� �Ͽ����ϴ�.

ConcurrentHashMap�� **Lock Striping**�� ����Ͽ�, ����ȭ �÷��ǿ� ���� **���� ���ü�**�� �����մϴ�.

- Lock Striping: �÷��� �����͸� ���� ���� ������ ������, �� �������� Ư�� ���� ����ϵ��� �ϴ� ��
    - ���� ������ ���� �ʴ� �۾��� ���� ������ �Ͼ�� �����Ƿ� ���� �����忡�� ���� ���� ����, �� ȹ���� ���� ��� �ð� ����

##### CopyOnWriteArrayList

���� �۾� �� **����� ��**�� ����մϴ�. �÷��� ���� ����Ǵ� �������� ���� �迭�� �ִ� ����� ���纻�� ���� �����, �� ���纻�� ���� �۾� ���� �� ���� �迭�� �����մϴ�.

�б� �۾��� ���� �ɸ��� �ʽ��ϴ�.