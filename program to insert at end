#include <iostream>
using namespace std;

struct nod
{
    int info;
    struct nod* next;
};

typedef struct nod node;

class list
{
    node* f;

public:
    list()
    {
        f = NULL;
    }

    void insFront(int num)
    {
        node* p = new node;
        p->info = num;
        p->next = f;
        f = p;
    }

    void insRear(int num)
    {
        node* p = new node;
        p->info = num;
        p->next = NULL;

        if (f == NULL)
        {
            f = p;
        }
        else
        {
            node* temp = f;
            while (temp->next != NULL)
                temp = temp->next;

            temp->next = p;
        }
    }

    void insPos(int pos, int num)
    {
        if (pos <= 0)
        {
            cout << "\nInvalid position.\n";
            return;
        }

        if (pos == 1)
        {
            insFront(num);
            return;
        }

        node* p = new node;
        p->info = num;

        node* temp = f;
        int count = 1;

        while (temp != NULL && count < pos - 1)
        {
            temp = temp->next;
            count++;
        }

        if (temp == NULL)
        {
            cout << "\nPosition exceeds the length of the list.\n";
            return;
        }

        p->next = temp->next;
        temp->next = p;
    }

    void delFront()
    {
        node* temp = f;
        if (f == NULL)
            cout << "\nNo elements to delete.\n";
        else
        {
            cout << "\nThe deleted element is: " << f->info;
            f = f->next;
            delete temp;
            cout << "\nDeletion successful.\n";
        }
    }

    void delRear()
    {
        if (f == NULL)
        {
            cout << "\nNo elements to delete.\n";
            return;
        }

        if (f->next == NULL)
        {
            cout << "\nThe deleted element is: " << f->info;
            delete f;
            f = NULL;
            cout << "\nDeletion successful.\n";
            return;
        }

        node* temp = f;
        while (temp->next->next != NULL)
            temp = temp->next;

        cout << "\nThe deleted element is: " << temp->next->info;
        delete temp->next;
        temp->next = NULL;
        cout << "\nDeletion successful.\n";
    }

    void delPos(int pos)
    {
        if (pos <= 0)
        {
            cout << "\nInvalid position.\n";
            return;
        }

        if (pos == 1)
        {
            delFront();
            return;
        }

        node* temp = f;
        int count = 1;

        while (temp != NULL && count < pos - 1)
        {
            temp = temp->next;
            count++;
        }

        if (temp == NULL || temp->next == NULL)
        {
            cout << "\nPosition exceeds the length of the list.\n";
            return;
        }

        node* delNode = temp->next;
        temp->next = delNode->next;

        cout << "\nThe deleted element is: " << delNode->info;
        delete delNode;
        cout << "\nDeletion successful.\n";
    }

    void disp()
    {
        node* temp = f;
        if (f == NULL)
            cout << "\nList is empty.\n";
        else
        {
            cout << "\nElements in the list are: ";
            while (temp != NULL)
            {
                cout << temp->info << " ";
                temp = temp->next;
            }
        }
    }
};

int main()
{
    int num, ch = 1;
    list ob;
    cout << "\n!!!!!!!!!!! LINEAR LINK LIST !!!!!!!!!!!!!!!!\n";
    cout << "\n1] Insert at the front\n2] Insert at the rear\n3] Insert at a specific position\n4] Delete from the front\n5] Delete from the rear\n6] Delete from a specific position\n7] Display\n8] Exit";
    while (ch)
    {
        cout << "\nEnter your choice: ";
        cin >> ch;
        switch (ch)
        {
        case 1:
            cout << "\nEnter number to be inserted at the front: ";
            cin >> num;
            ob.insFront(num);
            ob.disp();
            break;
        case 2:
            cout << "\nEnter number to be inserted at the rear: ";
            cin >> num;
            ob.insRear(num);
            ob.disp();
            break;
        case 3:
            int pos;
            cout << "\nEnter position to insert: ";
            cin >> pos;
            cout << "Enter number to be inserted: ";
            cin >> num;
            ob.insPos(pos, num);
            ob.disp();
            break;
        case 4:
            ob.delFront();
            ob.disp();
            break;
        case 5:
            ob.delRear();
            ob.disp();
            break;
        case 6:
            cout << "\nEnter position to delete: ";
            cin >> pos;
            ob.delPos(pos);
            ob.disp();
            break;
        case 7:
            ob.disp();
            break;
        case 8:
            return 0;
        default:
            cout << "Invalid choice.\n";
            break;
        }
    }
    return 0;
}
