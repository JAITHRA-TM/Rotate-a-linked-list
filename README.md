# Rotate-a-linked-list
Node *rotate(Node *head, int k) {
     // Write your code here.
     if(head == NULL || k == 0){
          return head;
     }
     int cnt = 0;
     Node *temp = head;
     while(temp){
          cnt++;
          temp = temp->next;
     }
     temp = head;
     while(temp->next){
          temp = temp->next;
     }
               temp->next = head;

     k = k % cnt;
     for (int i = 0; i < cnt - k; i++) {
          temp = temp->next;
     }
          head = temp->next;
          temp->next = NULL;
     
      return head;
}
