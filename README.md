//Implement a stack using the queue data structure

#include <iostream>
#include <queue>
#include <vector>
#include <cstdlib>
using namespace std;
 

class Stack
{
    queue<int> q1, q2;
 
public:
    void push(int data)
    {
        while (!q1.empty())
        {
            q2.push(q1.front());
            q1.pop();
        }
        q1.push(data);

  while (!q2.empty())
        {
            q1.push(q2.front());
            q2.pop();
        }
    }
 
  int pop()
    {
        if (q1.empty())
        {
            cout << "Underflow!!";
            exit(0);
        }
 
   int front = q1.front();
     q1.pop();
 
   return front;
    }
};
 
int main()
{
    vector<int> keys = { 1, 2, 3, 4, 5 };
 
   Stack s;
    for (int key: keys) {
        s.push(key);
    }
 
   for (int i = 0; i <= keys.size(); i++) {

    
   cout << s.pop() << endl;
    }
 
   return 0;
}



    Output
 5
 4
 3
 2
 1
 Underflow!!
