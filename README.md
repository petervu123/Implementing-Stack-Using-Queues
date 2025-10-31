class MyStack {
public:
    MyStack() {
        
    }
    queue<int> line1;
    queue<int> line2;

    void push(int x) {
        line2.push(x);

        while (!line1.empty()) {
            int temp = line1.front();
            line1.pop();
            line2.push(temp);
        }
        while (!line2.empty()) {
            int temp = line2.front();
            line2.pop();
            line1.push(temp);
        }
    }
    
    int pop() {
        int info = line1.front();
        line1.pop();
        return info;
    }
    
    int top() {
        return line1.front();
    }
    
    bool empty() {
        if(line1.empty()) {
            return true;
        }
        else {
            return false;
        }
    }
};

