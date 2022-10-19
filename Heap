#include <iostream>

using namespace std;

class Heap
{
private:
    int maxsize;
    int *heap;
    int size = 0;

    void swap(int i, int j)
    {
        int temp = heap[i];
        heap[i] = heap[j];
        heap[j] = temp;
    }

public:
    Heap(int size) : maxsize(size), heap(new int[maxsize + 1]) {}

    void display()
    {
        for (int i = 1; i <= size; i++)
            cout << heap[i] << " ";
        cout << endl;
    }

    bool push(int val)
    {
        if (size == maxsize)
        {
            cout << "Heap is full!" << endl;
            return false;
        }
        size++;
        heap[size] = val;
        int currnode = size;
        while (currnode > 1 && heap[currnode] < heap[currnode / 2])
        {
            swap(currnode, currnode / 2);
            currnode /= 2;
        }
        return true;
    }

    int pop()
    {
        if (size == 0)
        {
            cout << "Heap is empty!" << endl;
            return -1;
        }

        int val = heap[1];
        heap[1] = heap[size];
        size--;

        int currnode = 1, left, right;
        while (currnode <= size / 2)
        {
            left = 2 * currnode;
            right = left + 1;

            if (heap[left] < heap[right] && heap[left] < heap[currnode])
            {
                swap(currnode, left);
                currnode = left;
            }

            else if (heap[right] < heap[left] && heap[right] < heap[currnode])
            {
                swap(currnode, right);
                currnode = right;
            }

            else
                break;
        }

        return val;
    }

    void clear()
    {
        size = 0;
    }

    void destroy()
    {
        delete[] heap;
        size = 0;
        maxsize = 0;
    }
};

int main(void)
{
    Heap heap(10);
    heap.push(10);
    heap.push(8);
    heap.push(2);
    heap.push(1);
    heap.push(7);
    heap.push(6);
    heap.push(3);
    heap.push(9);
    heap.push(4);
    heap.push(5);

    cout << heap.pop() << endl;
    cout << heap.pop() << endl;
    cout << heap.pop() << endl;
    cout << heap.pop() << endl;
    cout << heap.pop() << endl;
    cout << heap.pop() << endl;
    cout << heap.pop() << endl;
    cout << heap.pop() << endl;
    cout << heap.pop() << endl;
    cout << heap.pop() << endl;
    heap.display();
    heap.destroy();
    return 0;
}
