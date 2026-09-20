#include <iostream>
using namespace std;

struct node {
    int data;
    node *next;
};

node* create_node() {
    int num;
    cout << "Enter your number: ";
    cin >> num;
    
    node *p = new node;
    p->data = num;
    p->next = nullptr;
    return p;
}

node* add_tail(node *head) {
    node *p = create_node();
    
    if (head == nullptr) {
        return p;
    }
    
    node *temp = head;
    while (temp->next != nullptr) {
        temp = temp->next;
    }
    temp->next = p;
    return head;
}

void display(node *head) {
    node *temp = head;
    cout << "List: ";
    while (temp != nullptr) {
        cout << temp->data << " -> ";
        temp = temp->next;
    }
    cout << "NULL\n";
}

node* delete_first_node(node* h) {
    if(h == nullptr){
        cout << "List is already empty.\n";
        return nullptr;
    }
    node* p = h;
    h = h->next;
    delete p;
    cout << "First node deleted.\n";
    return h;
}

node* delete_middle(node* head) {
    if (head == nullptr) {
        cout << "List is empty.\n";
        return nullptr;
    }
    if (head->next == nullptr) {
        delete head;
        cout << "Middle (only) node deleted.\n";
        return nullptr;
    }
    
    node* slow = head;
    node* fast = head;
    node* prev = nullptr;
    
    while (fast != nullptr && fast->next != nullptr) {
        fast = fast->next->next;
        prev = slow;
        slow = slow->next;
    }
    
    prev->next = slow->next;
    delete slow;
    cout << "Middle node deleted.\n";
    return head;
}

node* delete_by_value(node* head, int target) {
    if (head == nullptr) {
        cout << "List is empty.\n";
        return nullptr;
    }
    if (head->data == target) {
        node* p = head;
        head = head->next;
        delete p;
        cout << "Element " << target << " deleted.\n";
        return head;
    }
    
    node* temp = head;
    while (temp->next != nullptr && temp->next->data != target) {
        temp = temp->next;
    }
    
    if (temp->next == nullptr) {
        cout << "Element " << target << " not found in the list.\n";
    } else {
        node* p = temp->next;
        temp->next = temp->next->next;
        delete p;
        cout << "Element " << target << " deleted.\n";
    }
    return head;
}



int linearSearch(int arr[], int size, int target) {
    for (int i = 0; i < size; i++) {
        if (arr[i] == target) return i;
    }
    return -1;
}

int binarySearch(int arr[], int size, int target) {
    int low = 0, high = size - 1;
    while (low <= high) {
        int mid = low + (high - low) / 2;
        if (arr[mid] == target) return mid;
        if (arr[mid] < target) low = mid + 1;
        else high = mid - 1;
    }
    return -1;
}

void bubbleSort(int arr[], int n) {
    for (int i = 0; i < n - 1; i++) {
        for (int j = 0; j < n - 1 - i; j++) {
            if (arr[j] > arr[j + 1]) {
                int temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }
}

void insertionSort(int arr[], int n) {
    for (int i = 1; i < n; i++) {
        int key = arr[i];
        int j = i - 1;
        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j--;
        }
        arr[j + 1] = key;
    }
}

void printArray(int arr[], int size) {
    for (int i = 0; i < size; i++) {
        cout << arr[i] << " ";
    }
    cout << endl;
}


int main() {
    
    
    int mainChoice;
    do {
        
        cout << "\n-------- Main Menu -------\n";
        cout << "1. Arrays\n";
        cout << "2. Search Algorithm\n";
        cout << "3. Sort Algorithm\n";
        cout << "4. Linked list\n";
        cout << "5. Stack\n";
        cout << "6. Queue\n";
        cout << "7. Exit\n";
        cout << "Enter your choice: ";
        cin >> mainChoice;

        switch (mainChoice) {
            case 1: { 
                int subChoice;
                do {
                    cout << "\n--- Array Operations ---\n";
                    cout << "1. Create & Input Array Elements\n";
                    cout << "2. Back to Main Menu\n";
                    cout << "Choice: ";
                    cin >> subChoice;
                    if (subChoice == 1) {
                        int size;
                        cout << "Enter size of array: ";
                        cin >> size;
                        int arr[100];
                        cout << "Enter " << size << " elements:\n";
                        for (int i = 0; i < size; i++) {
                            cin >> arr[i];
                        }
                        cout << "Array elements are: ";
                        printArray(arr, size);
                    }
                } while (subChoice != 2);
                break;
            }

            case 2: { 
                int subChoice;
                do {
                    cout << "\n--- Search Menu ---\n";
                    cout << "1. Linear Search\n";
                    cout << "2. Binary Search (Requires Sorted Input)\n";
                    cout << "3. Back to Main Menu\n";
                    cout << "Choice: ";
                    cin >> subChoice;

                    if (subChoice == 1 || subChoice == 2) {
                        int n, target;
                        cout << "Enter size of array: ";
                        cin >> n;
                        int arr[100];
                        cout << "Enter " << n << " elements:\n";
                        for (int i = 0; i < n; i++) cin >> arr[i];

                        cout << "Enter target value to search: ";
                        cin >> target;

                        int index = -1;
                        if (subChoice == 1) {
                            index = linearSearch(arr, n, target);
                        } else {
                            bubbleSort(arr, n);
                            cout << "(Array was sorted automatically for Binary Search)\n";
                            index = binarySearch(arr, n, target);
                        }

                        if (index != -1) cout << "Target found at index: " << index << endl;
                        else cout << "Target not found.\n";
                    }
                } while (subChoice != 3);
                break;
            }

            case 3: { 
                int subChoice;
                do {
                    cout << "\n--- Sort Menu ---\n";
                    cout << "1. Bubble Sort\n";
                    cout << "2. Insertion Sort\n";
                    cout << "3. Back to Main Menu\n";
                    cout << "Choice: ";
                    cin >> subChoice;

                    if (subChoice == 1 || subChoice == 2) {
                        int size;
                        cout << "Enter size of array: ";
                        cin >> size;
                        int arr[100];
                        cout << "Enter " << size << " elements:\n";
                        for (int i = 0; i < size; i++) cin >> arr[i];

                        cout << "Array before sort:\n";
                        printArray(arr, size);

                        if (subChoice == 1) bubbleSort(arr, size);
                        else insertionSort(arr, size);

                        cout << "Sorted array:\n";
                        printArray(arr, size);
                    }
                } while (subChoice != 3);
                break;
            }

            case 4: { 
                node* head = nullptr;
                int subChoice;
                do {
                    cout << "\n--- Linked List Operations ---\n";
                    cout << "1. Add Node (Tail)\n";
                    cout << "2. Delete First Node\n";
                    cout << "3. Delete Middle Node\n";
                    cout << "4. Delete Specific Value\n";
                    cout << "5. Display List\n";
                    cout << "6. Back to Main Menu\n";
                    cout << "Choice: ";
                    cin >> subChoice;

                    if (subChoice == 1) {
                        head = add_tail(head);
                    } else if (subChoice == 2) {
                        head = delete_first_node(head);
                    } else if (subChoice == 3) {
                        head = delete_middle(head);
                    } else if (subChoice == 4) {
                        int val;
                        cout << "Enter the value you want to delete: ";
                        cin >> val;
                        head = delete_by_value(head, val);
                    } else if (subChoice == 5) {
                        display(head);
                    }
                } while (subChoice != 6);
                break;
            }

            case 5: { 
                int stack[100], top = -1, capacity = 100, subChoice;
                do {
                    cout << "\n--- Stack Operations ---\n";
                    cout << "1. Push\n";
                    cout << "2. Pop\n";
                    cout << "3. Peek\n";
                    cout << "4. Display\n";
                    cout << "5. Back to Main Menu\n";
                    cout << "Choice: ";
                    cin >> subChoice;

                    if (subChoice == 1) {
                        if (top >= capacity - 1) cout << "Stack Overflow!\n";
                        else {
                            int val;
                            cout << "Enter value: ";
                            cin >> val;
                            stack[++top] = val;
                        }
                    } else if (subChoice == 2) {
                        if (top < 0) cout << "Stack Underflow!\n";
                        else cout << "Popped: " << stack[top--] << endl;
                    } else if (subChoice == 3) {
                        if (top < 0) cout << "Stack is empty.\n";
                        else cout << "Top element: " << stack[top] << endl;
                    } else if (subChoice == 4) {
                        if (top < 0) cout << "Stack is empty.\n";
                        else {
                            cout << "Stack: ";
                            for (int i = top; i >= 0; i--) cout << stack[i] << " ";
                            cout << endl;
                        }
                    }
                } while (subChoice != 5);
                break;
            }

            case 6: { 
                int queue[100], front = 0, rear = -1, subChoice;
                do {
                    cout << "\n--- Queue Operations ---\n";
                    cout << "1. Enqueue\n";
                    cout << "2. Dequeue\n";
                    cout << "3. Display\n";
                    cout << "4. Back to Main Menu\n";
                    cout << "Choice: ";
                    cin >> subChoice;

                    if (subChoice == 1) {
                        if (rear >= 99) cout << "Queue Overflow!\n";
                        else {
                            int val;
                            cout << "Enter value: ";
                            cin >> val;
                            queue[++rear] = val;
                        }
                    } else if (subChoice == 2) {
                        if (front > rear) cout << "Queue Underflow!\n";
                        else cout << "Dequeued: " << queue[front++] << endl;
                    } else if (subChoice == 3) {
                        if (front > rear) cout << "Queue is empty.\n";
                        else {
                            cout << "Queue: ";
                            for (int i = front; i <= rear; i++) cout << queue[i] << " ";
                            cout << endl;
                        }
                    }
                } while (subChoice != 4);
                break;
            }

            case 7:
                cout << "Exiting program. Goodbye!\n";
                break;

            default:
                cout << "Invalid choice! Try again.\n";
        }
    } while (mainChoice != 7);

    return 0;
}
