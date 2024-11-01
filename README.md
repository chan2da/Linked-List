# Linked-List
* 링크드 리스트를 활용하는 예제를 가장 간단하게 만들어서 Github에 올리고 링크를 제출한다. * 팀원의 소감을 적는다.


링크드 리스트를 활용하는 예제 <코드>

#include <stdio.h>

#include <stdlib.h>

struct Node {
    
    int data;          

    struct Node* next;  

};

struct Node* createNode(int data) {
    
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node)); 
    
    newNode->data = data;
    
    newNode->next = NULL;
    
    return newNode;
}


void append(struct Node** head, int data) {
    
    struct Node* newNode = createNode(data);
    
    if (*head == NULL) { 
        
        *head = newNode;
        
        return;
    
    }

    
    struct Node* temp = *head;
    
    while (temp->next != NULL) { 
       
        temp = temp->next;
   
    }

    temp->next = newNode; 

}

void printList(struct Node* head) {
 
    struct Node* temp = head;
  
    while (temp != NULL) {
   
        printf("%d -> ", temp->data);
    
        temp = temp->next;
   
    }
  
    printf("NULL\n");

}



int main() {
  
    struct Node* head = NULL; 

   
    append(&head, 1); 
   
    append(&head, 2);
    
    append(&head, 3);

  
    printList(head); 

  
    return 0;

}


<설명>
코드 설명

Node 구조체 정의:

(data 변수는 노드가 저장할 정수형 데이터를 나타내고

next 포인터는 다음 노드를 가리킵니다.)



createNode 함수:

(malloc을 사용해 새로운 노드를 동적 할당합니다.

전달받은 데이터를 data에 저장하고 next는 NULL로 설정해 리스트의 끝을 표시합니다.)


append 함수:

(head 포인터를 이용해 리스트의 마지막에 새로운 노드를 추가합니다.

만약 리스트가 비어 있다면 새 노드를 head로 설정합니다.

비어 있지 않다면 temp를 사용해 리스트의 마지막 노드까지 이동한 후 새로운 노드를 추가합니다.)



printList 함수:

(head부터 시작해 각 노드의 data를 출력하면서 리스트의 끝까지 이동합니다.)


main 함수:

(append 함수로 숫자 1, 2, 3을 저장하는 노드를 순서대로 추가합니다.

printList 함수로 리스트를 출력합니다.)

<소감>

20240943 김윤찬

이 예제를 통해 링크드 리스트의 기본 구조와 작동 방식을 이해하게 되었습니다. 
특히 동적 메모리 할당과 포인터의 역할을 더 깊이 알 수 있었습니다. 
배열과는 달리 크기를 유동적으로 조정할 수 있어 매우 유용하며 
데이터 추가나 삭제 작업이 용이하다는 장점이 있습니다. 
이번 경험은 C언어의 자료 구조를 한층 더 깊이 이해하는 데 큰 도움이 되었으며
추후 더 복잡한 자료 구조와 알고리즘 학습에 대한 자신감을 얻게 되었습니다.

20240935 공민석 

C언어의 자료구조중 스택다음으로 링크드 리스트 라는것을 배웠는데 
처음에는 이해하기 어려웠지만 영상으로 한번 학습한후 
교수님께서 다시 설명주셔서 이해하기 쉬웠고 
여러 다른 자료구조에 관해서도 학습하고 도전하고 싶다

20240937 권예슬

이번 과제를 통해 링크드 리스트의 기본 구조와 노드 간의 연결 방식을 이해하게 되었습니다. 
노드를 추가하고 연결하는 과정을 배우면서 자료 구조의 유용성을 실감할 수 있었습니다. 
이 과제가 자료 구조에 대한 기초 이해를 높이는 데 큰 도움이 되었습니다.

20240938 권용현

이번에 배운 링크드 디스크에 대해서 여러가지 활용 방안에 대해 생각해보는 계기가 되었으며, C언어를 이용하여 링크드 리스크를 어떻게 활용할지, 혹은 어떠한 방식으로 조금 더 보는 입장에서 편하게 알아볼 수 있을지에 대해서 고민해보는 과정을 가질 수 있어서 좋았다. 이에 대해 배웠으니 앞으로 더 다양한 코드를 C언어를 통해 구현하고, 이해할 수 있을것이라 생각해 앞으로 배울 다양한것에 대해 기대된다.
