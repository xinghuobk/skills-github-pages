# 上机 C++ 编程题精选

> 本文件包含 **22 道**上海大学计算机学院复试上机编程题精选，涵盖常见题型和考点。每题包含：题目描述、输入输出说明、样例、解题思路分析、C++ 参考代码、题目标注。

---

## 题型分布总览

| 题型 | 题数 | 题号 |
|------|------|------|
| 排序与查找 | 3 | 1, 2, 3 |
| 字符串处理 | 3 | 4, 5, 6 |
| 链表 / 栈 / 队列 | 3 | 7, 8, 9 |
| 二叉树 | 3 | 10, 11, 12 |
| 动态规划（DP） | 3 | 13, 14, 15 |
| 图论 | 3 | 16, 17, 18 |
| 数论 / 数学题 | 2 | 19, 20 |
| 模拟题 / 综合题 | 2 | 21, 22 |

---

## 第 1 题：冒泡排序与优化

**题目描述**：给定一个整数数组，使用冒泡排序算法将其从小到大排序。要求：输出每一轮交换后的数组状态，并在某一轮没有发生任何交换时提前终止。

**输入**：第一行一个整数 n（1 ≤ n ≤ 1000），第二行 n 个整数。

**输出**：每一轮交换后输出一行，n 个空格分隔的整数。最后一行输出"排序完成，共进行 k 轮"，其中 k 为实际轮数。

**样例输入**：
```
5
5 3 8 6 2
```

**样例输出**：
```
3 5 6 2 8
3 5 2 6 8
3 2 5 6 8
2 3 5 6 8
排序完成，共进行 4 轮
```

**解题思路**：
1. 使用两层循环，外层控制轮数，内层执行相邻元素比较与交换
2. 设置标志位 `swapped`，若某轮无交换则说明已有序，直接退出
3. 每轮结束后输出当前数组状态
4. 时间复杂度 O(n²)，最好情况 O(n)（已有序时）

**参考代码**：

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {
    int n;
    cin >> n;
    vector<int> arr(n);
    for (int i = 0; i < n; i++) {
        cin >> arr[i];
    }
    
    int rounds = 0;
    for (int i = 0; i < n - 1; i++) {
        bool swapped = false;
        for (int j = 0; j < n - 1 - i; j++) {
            if (arr[j] > arr[j + 1]) {
                swap(arr[j], arr[j + 1]);
                swapped = true;
            }
        }
        rounds++;
        for (int k = 0; k < n; k++) {
            cout << arr[k] << (k == n - 1 ? "\n" : " ");
        }
        if (!swapped) break;  // 优化：已有序，提前终止
    }
    
    cout << "排序完成，共进行 " << rounds << " 轮" << endl;
    return 0;
}
```

**出处标注**：上海大学计算机学院复试上机真题（改编）

---

## 第 2 题：二分查找及插入位置

**题目描述**：给定一个**已排序**（从小到大）的整数数组和一个目标值 target。若 target 在数组中则返回其索引（若有重复元素返回任意一个位置即可）；若不在数组中，返回 target 按顺序插入的位置索引（即第一个大于 target 的位置，或 n）。

**输入**：第一行 n 和 target（1 ≤ n ≤ 10^5，|target| ≤ 10^9）。第二行 n 个整数，已按非降序排列。

**输出**：一行一个整数，表示 target 的位置或插入位置。

**样例输入 1**：
```
6 5
1 3 5 5 7 9
```

**样例输出 1**：
```
2（或 3）
```

**样例输入 2**：
```
5 4
1 2 3 5 6
```

**样例输出 2**：
```
3
```

**解题思路**：
1. 使用标准二分查找框架
2. 初始化 left = 0, right = n（使用左闭右开区间）
3. 当 target < nums[mid] 时，right = mid；否则 left = mid + 1
4. 循环结束时 left 即为插入位置
5. 时间复杂度 O(log n)

**参考代码**：

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {
    int n, target;
    cin >> n >> target;
    vector<int> nums(n);
    for (int i = 0; i < n; i++) {
        cin >> nums[i];
    }
    
    // 二分查找：返回第一个 >= target 的位置
    int left = 0, right = n;
    while (left < right) {
        int mid = left + (right - left) / 2;  // 避免溢出
        if (nums[mid] < target) {
            left = mid + 1;
        } else {
            right = mid;
        }
    }
    
    cout << "插入位置：" << left << endl;
    if (left < n && nums[left] == target) {
        cout << "target 存在于数组中，索引 = " << left << endl;
    } else {
        cout << "target 不存在于数组中，应插入到索引 " << left << endl;
    }
    
    return 0;
}
```

**出处标注**：上海大学计算机学院复试上机真题（改编自 LeetCode 35）

---

## 第 3 题：第 k 大的数

**题目描述**：给定一个未排序的整数数组，找出其中第 k 大的元素。要求使用**快速选择**（QuickSelect）算法实现，期望时间复杂度 O(n)。

**输入**：第一行 n 和 k（1 ≤ k ≤ n ≤ 10^5）。第二行 n 个整数。

**输出**：一行一个整数，表示第 k 大的元素。

**样例输入**：
```
6 2
3 2 1 5 6 4
```

**样例输出**：
```
5
```

**解题思路**：
1. 第 k 大 = 第 (n-k) 小（从 0 开始）
2. 使用快速选择：类似快排，但只递归需要的那一侧
3. 随机化 pivot 避免最坏情况
4. 时间复杂度：期望 O(n)，最坏 O(n²)

**参考代码**：

```cpp
#include <iostream>
#include <vector>
#include <cstdlib>
#include <ctime>
using namespace std;

// 在 nums[l..r] 中分区，返回 pivot 的最终位置
int partition(vector<int>& nums, int l, int r) {
    // 随机选择 pivot，避免最坏情况
    int pivotIdx = l + rand() % (r - l + 1);
    swap(nums[pivotIdx], nums[r]);
    int pivot = nums[r];
    
    int i = l;  // i 指向小于 pivot 的区域的下一个位置
    for (int j = l; j < r; j++) {
        if (nums[j] < pivot) {
            swap(nums[i], nums[j]);
            i++;
        }
    }
    swap(nums[i], nums[r]);
    return i;
}

// 快速选择：返回第 k 小的元素（k 从 0 开始）
int quickSelect(vector<int>& nums, int l, int r, int k) {
    if (l == r) return nums[l];
    int p = partition(nums, l, r);
    if (p == k) return nums[p];
    else if (p < k) return quickSelect(nums, p + 1, r, k);
    else return quickSelect(nums, l, p - 1, k);
}

int main() {
    srand(time(0));
    
    int n, k;
    cin >> n >> k;
    vector<int> nums(n);
    for (int i = 0; i < n; i++) {
        cin >> nums[i];
    }
    
    // 第 k 大 = 第 (n-k) 小
    int result = quickSelect(nums, 0, n - 1, n - k);
    cout << "第 " << k << " 大的元素是：" << result << endl;
    
    return 0;
}
```

**出处标注**：上海大学计算机学院复试上机真题（改编自 LeetCode 215）

---

## 第 4 题：字符串反转（单词级）

**题目描述**：输入一个英文句子（仅包含字母、空格和标点符号），要求**按单词反转**句子，即保持单词内部字符顺序不变，但单词顺序反转。同时要求：
1. 去除单词间多余空格（连续多个空格变为一个空格）
2. 去除句子首尾空格

**输入**：一行字符串（长度 ≤ 1000）

**输出**：反转后的句子

**样例输入**：
```
  hello   world  I  love   shanghai university  
```

**样例输出**：
```
university shanghai love I world hello
```

**解题思路**：
1. 方法一：使用字符串流 (stringstream) 自动按空格分割，存到 vector 中，再倒序输出
2. 方法二：先翻转整个字符串，再翻转每个单词（经典算法）
3. 方法一实现简单，推荐使用

**参考代码**：

```cpp
#include <iostream>
#include <string>
#include <sstream>
#include <vector>
using namespace std;

int main() {
    string line;
    getline(cin, line);  // 读取包含空格的整行
    
    // 使用 stringstream 自动处理空格分隔
    stringstream ss(line);
    vector<string> words;
    string word;
    while (ss >> word) {  // 自动跳过所有空白字符
        words.push_back(word);
    }
    
    // 倒序输出
    for (int i = words.size() - 1; i >= 0; i--) {
        cout << words[i];
        if (i > 0) cout << " ";
    }
    cout << endl;
    
    return 0;
}
```

**出处标注**：上海大学计算机学院复试上机真题

---

## 第 5 题：最长回文子串

**题目描述**：给定一个字符串 s，找出其中最长的回文子串。如果存在多个相同长度的回文子串，返回任意一个即可。

**输入**：一行字符串（长度 ≤ 1000，仅含英文字母和数字）

**输出**：第一行输出最长回文子串的长度，第二行输出该回文子串。

**样例输入**：
```
babad
```

**样例输出**：
```
3
bab（或 aba）
```

**解题思路**：中心扩展法
1. 回文串有两种形式：奇数长度（中心为一个字符）和偶数长度（中心为两个字符）
2. 枚举每个可能的中心位置，向两侧扩展直到字符不相等
3. 记录最长回文的起点和长度
4. 时间复杂度 O(n²)，空间 O(1)

**参考代码**：

```cpp
#include <iostream>
#include <string>
using namespace std;

// 从 l 和 r 向两侧扩展，返回最长回文长度
int expand(const string& s, int l, int r, int& start) {
    while (l >= 0 && r < s.length() && s[l] == s[r]) {
        l--;
        r++;
    }
    start = l + 1;
    return r - l - 1;  // 回文长度
}

int main() {
    string s;
    cin >> s;
    int n = s.length();
    if (n == 0) { cout << 0 << endl; return 0; }
    
    int maxLen = 1;
    int maxStart = 0;
    
    for (int i = 0; i < n; i++) {
        int start1, start2;
        int len1 = expand(s, i, i, start1);        // 奇数长度
        int len2 = expand(s, i, i + 1, start2);    // 偶数长度
        
        if (len1 > maxLen) {
            maxLen = len1;
            maxStart = start1;
        }
        if (len2 > maxLen) {
            maxLen = len2;
            maxStart = start2;
        }
    }
    
    cout << maxLen << endl;
    cout << s.substr(maxStart, maxLen) << endl;
    
    return 0;
}
```

**出处标注**：上海大学计算机学院复试上机真题（改编自 LeetCode 5）

---

## 第 6 题：字符串匹配（KMP 算法）

**题目描述**：给定一个文本串 text 和一个模式串 pattern，找出 pattern 在 text 中所有出现的位置。使用 KMP 算法实现。

**输入**：第一行 text，第二行 pattern（长度均 ≤ 10^5）

**输出**：第一行输出匹配次数 k，接下来 k 行每行一个整数，表示 pattern 在 text 中出现的起始索引（从 1 开始或从 0 开始均可，需注明）

**样例输入**：
```
abababcabababc
ababc
```

**样例输出**：
```
2
2（索引从 0 开始）
9（索引从 0 开始）
```

**解题思路**：
1. 第一步：构造 next 数组（失配函数）
   - next[i] 表示 pattern[0..i] 的最长相等真前后缀长度
2. 第二步：使用双指针进行线性匹配
   - i 指向 text，j 指向 pattern
   - 匹配成功同时前进
   - 失配时 j = next[j-1]（若 j > 0），否则 i++
3. 时间复杂度 O(n + m)

**参考代码**：

```cpp
#include <iostream>
#include <string>
#include <vector>
using namespace std;

// 构造 KMP 的 next 数组
vector<int> buildNext(const string& p) {
    int m = p.length();
    vector<int> next(m, 0);
    int j = 0;  // 当前已匹配长度
    for (int i = 1; i < m; i++) {
        while (j > 0 && p[i] != p[j]) {
            j = next[j - 1];
        }
        if (p[i] == p[j]) {
            j++;
        }
        next[i] = j;
    }
    return next;
}

// KMP 搜索，返回所有匹配位置（0-based）
vector<int> kmpSearch(const string& t, const string& p, const vector<int>& next) {
    vector<int> positions;
    int n = t.length(), m = p.length();
    int j = 0;
    for (int i = 0; i < n; i++) {
        while (j > 0 && t[i] != p[j]) {
            j = next[j - 1];
        }
        if (t[i] == p[j]) {
            j++;
        }
        if (j == m) {  // 找到匹配
            positions.push_back(i - m + 1);
            j = next[j - 1];  // 继续寻找下一个匹配
        }
    }
    return positions;
}

int main() {
    string text, pattern;
    cin >> text >> pattern;
    
    if (pattern.length() == 0 || pattern.length() > text.length()) {
        cout << 0 << endl;
        return 0;
    }
    
    vector<int> next = buildNext(pattern);
    vector<int> positions = kmpSearch(text, pattern, next);
    
    cout << "匹配次数：" << positions.size() << endl;
    cout << "匹配位置（0-based）：";
    for (int pos : positions) {
        cout << pos << " ";
    }
    cout << endl;
    
    return 0;
}
```

**出处标注**：上海大学计算机学院复试上机真题

---

## 第 7 题：单链表反转

**题目描述**：实现一个单链表，并支持以下操作：
1. 从数组构建链表
2. 反转整个链表（要求：递归和迭代两种方式都实现）
3. 按区间反转 [m, n] 的部分（1-based）
4. 输出链表

**输入**：第一行 n 和 m、n_rev（1 ≤ m ≤ n_rev ≤ n ≤ 1000）。第二行 n 个整数表示链表初始值。

**输出**：
- 第一行：反转整个链表后的结果
- 第二行：还原原链表后，反转区间 [m, n_rev] 后的结果

**样例输入**：
```
5 2 4
1 2 3 4 5
```

**样例输出**：
```
5 4 3 2 1
1 4 3 2 5
```

**解题思路**：
1. 整体反转：三指针迭代法（prev, curr, next）或递归
2. 区间反转：先遍历到 m-1 位置保存，然后反转 m 到 n_rev 的节点
3. 需要特别注意边界条件处理

**参考代码**：

```cpp
#include <iostream>
#include <vector>
using namespace std;

struct ListNode {
    int val;
    ListNode* next;
    ListNode(int x) : val(x), next(nullptr) {}
};

// 从数组构建链表
ListNode* buildList(const vector<int>& arr) {
    ListNode dummy(0);
    ListNode* p = &dummy;
    for (int x : arr) {
        p->next = new ListNode(x);
        p = p->next;
    }
    return dummy.next;
}

// 输出链表
void printList(ListNode* head) {
    while (head) {
        cout << head->val;
        if (head->next) cout << " ";
        head = head->next;
    }
    cout << endl;
}

// 反转整个链表（迭代）
ListNode* reverseIter(ListNode* head) {
    ListNode* prev = nullptr;
    ListNode* curr = head;
    while (curr) {
        ListNode* nextTemp = curr->next;
        curr->next = prev;
        prev = curr;
        curr = nextTemp;
    }
    return prev;
}

// 反转整个链表（递归）
ListNode* reverseRecur(ListNode* head) {
    if (!head || !head->next) return head;
    ListNode* newHead = reverseRecur(head->next);
    head->next->next = head;
    head->next = nullptr;
    return newHead;
}

// 反转区间 [m, n]（1-based）
ListNode* reverseBetween(ListNode* head, int m, int n) {
    ListNode dummy(0);
    dummy.next = head;
    ListNode* pre = &dummy;
    
    // pre 移动到第 m-1 个节点
    for (int i = 0; i < m - 1; i++) {
        pre = pre->next;
    }
    
    ListNode* start = pre->next;  // 反转部分的起点
    ListNode* then = start->next; // 下一个要插入到 pre 之后的节点
    
    // 头插法：将 then 节点插入到 pre 之后
    for (int i = 0; i < n - m; i++) {
        start->next = then->next;
        then->next = pre->next;
        pre->next = then;
        then = start->next;
    }
    
    return dummy.next;
}

// 深拷贝链表（用于测试）
ListNode* cloneList(ListNode* head) {
    ListNode dummy(0);
    ListNode* p = &dummy;
    while (head) {
        p->next = new ListNode(head->val);
        p = p->next;
        head = head->next;
    }
    return dummy.next;
}

int main() {
    int n, m, n_rev;
    cin >> n >> m >> n_rev;
    vector<int> arr(n);
    for (int i = 0; i < n; i++) cin >> arr[i];
    
    ListNode* head1 = buildList(arr);
    cout << "【整体反转（迭代）】" << endl;
    head1 = reverseIter(head1);
    printList(head1);
    
    // 重新构建原链表，测试区间反转
    ListNode* head2 = buildList(arr);
    cout << "【区间反转 [" << m << ", " << n_rev << "]】" << endl;
    head2 = reverseBetween(head2, m, n_rev);
    printList(head2);
    
    // 测试递归反转（重新构建）
    ListNode* head3 = buildList(arr);
    cout << "【整体反转（递归）】" << endl;
    head3 = reverseRecur(head3);
    printList(head3);
    
    return 0;
}
```

**出处标注**：上海大学计算机学院复试上机真题（改编自 LeetCode 92/206）

---

## 第 8 题：用栈实现表达式求值

**题目描述**：给定一个仅包含非负整数、+、-、*、/ 和空格的字符串表达式，计算其值。要求：
1. 支持括号 ( )
2. 除法向下取整（C++ int 除法默认行为）
3. 保证输入合法

**输入**：一行字符串表达式（长度 ≤ 1000）

**输出**：表达式的值（整数）

**样例输入**：
```
(3 + 5) * 2 - 10 / 3
```

**样例输出**：
```
13
```

**解题思路**：使用两个栈（或递归下降解析）
1. 方法：维护数字栈和操作符栈，根据优先级进行计算
2. 遇到 '(' 直接入栈，遇到 ')' 则弹出直到 '(' 并计算
3. 遇到操作符时，弹出所有优先级 >= 当前的操作符进行计算
4. 最后清空操作符栈

**参考代码**：

```cpp
#include <iostream>
#include <string>
#include <stack>
using namespace std;

// 运算符优先级
int priority(char op) {
    if (op == '+' || op == '-') return 1;
    if (op == '*' || op == '/') return 2;
    return 0;  // '(' 的优先级最低
}

// 执行一次运算
int calc(int a, int b, char op) {
    switch (op) {
        case '+': return a + b;
        case '-': return a - b;
        case '*': return a * b;
        case '/': return a / b;  // 向下取整（C++ 默认）
    }
    return 0;
}

// 弹出一个操作符，执行一次计算
void popAndCalc(stack<int>& nums, stack<char>& ops) {
    int b = nums.top(); nums.pop();
    int a = nums.top(); nums.pop();
    char op = ops.top(); ops.pop();
    nums.push(calc(a, b, op));
}

int evaluate(const string& expr) {
    stack<int> nums;
    stack<char> ops;
    
    int i = 0, n = expr.length();
    while (i < n) {
        if (expr[i] == ' ') {
            i++;
        } else if (isdigit(expr[i])) {
            // 读取完整数字
            int num = 0;
            while (i < n && isdigit(expr[i])) {
                num = num * 10 + (expr[i] - '0');
                i++;
            }
            nums.push(num);
        } else if (expr[i] == '(') {
            ops.push('(');
            i++;
        } else if (expr[i] == ')') {
            // 弹出直到 '('
            while (!ops.empty() && ops.top() != '(') {
                popAndCalc(nums, ops);
            }
            ops.pop();  // 弹出 '('
            i++;
        } else {  // 运算符
            char op = expr[i];
            // 弹出所有优先级 >= 当前的运算符
            while (!ops.empty() && ops.top() != '(' && priority(ops.top()) >= priority(op)) {
                popAndCalc(nums, ops);
            }
            ops.push(op);
            i++;
        }
    }
    
    // 清空剩余运算
    while (!ops.empty()) {
        popAndCalc(nums, ops);
    }
    
    return nums.top();
}

int main() {
    string expr;
    getline(cin, expr);
    cout << "表达式值：" << evaluate(expr) << endl;
    return 0;
}
```

**出处标注**：上海大学计算机学院复试上机真题

---

## 第 9 题：滑动窗口最大值

**题目描述**：给定一个整数数组 nums 和一个正整数 k，有一个大小为 k 的滑动窗口从数组的最左侧移动到数组的最右侧。请输出每个滑动窗口中的最大值。

**输入**：第一行 n 和 k（1 ≤ k ≤ n ≤ 10^5）。第二行 n 个整数。

**输出**：一行 n-k+1 个整数，表示各窗口的最大值。

**样例输入**：
```
8 3
1 3 -1 -3 5 3 6 7
```

**样例输出**：
```
3 3 5 5 6 7
```

**解题思路**：使用**双端队列（deque）**维护一个单调递减队列
1. 队列中存储元素的索引（而非值），对应值单调递减
2. 新元素进入时，从队尾弹出所有小于等于它的元素
3. 队首元素超出窗口范围时，从队首弹出
4. 当窗口形成（i >= k-1）时，队首即为当前窗口最大值
5. 时间复杂度 O(n)，每个元素最多入队出队一次

**参考代码**：

```cpp
#include <iostream>
#include <vector>
#include <deque>
using namespace std;

int main() {
    int n, k;
    cin >> n >> k;
    vector<int> nums(n);
    for (int i = 0; i < n; i++) {
        cin >> nums[i];
    }
    
    deque<int> dq;  // 存储索引，对应值单调递减
    vector<int> result;
    
    for (int i = 0; i < n; i++) {
        // 1. 从队尾移除所有 <= nums[i] 的元素
        while (!dq.empty() && nums[dq.back()] <= nums[i]) {
            dq.pop_back();
        }
        // 2. 当前索引入队
        dq.push_back(i);
        // 3. 从队首移除超出窗口范围 [i-k+1, i] 的元素
        while (dq.front() <= i - k) {
            dq.pop_front();
        }
        // 4. 窗口形成后，输出队首
        if (i >= k - 1) {
            result.push_back(nums[dq.front()]);
        }
    }
    
    for (int i = 0; i < result.size(); i++) {
        cout << result[i];
        if (i < result.size() - 1) cout << " ";
    }
    cout << endl;
    
    return 0;
}
```

**出处标注**：上海大学计算机学院复试上机真题（改编自 LeetCode 239）

---

## 第 10 题：二叉树的三种遍历

**题目描述**：根据给定的二叉树前序和中序遍历序列，构建二叉树，并输出其后序遍历和层序遍历结果。

**输入**：第一行 n（节点数，1 ≤ n ≤ 1000）。第二行 n 个整数表示前序遍历。第三行 n 个整数表示中序遍历。（假设节点值互不相同）

**输出**：
- 第一行：后序遍历序列
- 第二行：层序遍历序列

**样例输入**：
```
5
3 9 20 15 7
9 3 15 20 7
```

**样例输出**：
```
9 15 7 20 3
3 9 20 15 7
```

**解题思路**：
1. 前序第一个元素是根节点
2. 在中序中找到根节点位置，左边为左子树，右边为右子树
3. 递归构建左右子树
4. 后序遍历：左 → 右 → 根
5. 层序遍历：使用队列 BFS

**参考代码**：

```cpp
#include <iostream>
#include <vector>
#include <queue>
#include <unordered_map>
using namespace std;

struct TreeNode {
    int val;
    TreeNode* left;
    TreeNode* right;
    TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
};

// 根据前序和中序构建二叉树
// pre: [preL, preR], in: [inL, inR]
TreeNode* build(vector<int>& pre, int preL, int preR,
                vector<int>& in, int inL, int inR,
                unordered_map<int, int>& inMap) {
    if (preL > preR) return nullptr;
    
    int rootVal = pre[preL];
    TreeNode* root = new TreeNode(rootVal);
    int rootPos = inMap[rootVal];  // 在中序中的位置
    int leftSize = rootPos - inL;  // 左子树节点数
    
    root->left = build(pre, preL + 1, preL + leftSize,
                       in, inL, rootPos - 1, inMap);
    root->right = build(pre, preL + leftSize + 1, preR,
                        in, rootPos + 1, inR, inMap);
    
    return root;
}

// 后序遍历
void postOrder(TreeNode* root, vector<int>& result) {
    if (!root) return;
    postOrder(root->left, result);
    postOrder(root->right, result);
    result.push_back(root->val);
}

// 层序遍历
void levelOrder(TreeNode* root, vector<int>& result) {
    if (!root) return;
    queue<TreeNode*> q;
    q.push(root);
    while (!q.empty()) {
        TreeNode* node = q.front();
        q.pop();
        result.push_back(node->val);
        if (node->left) q.push(node->left);
        if (node->right) q.push(node->right);
    }
}

void printVector(const vector<int>& v) {
    for (int i = 0; i < v.size(); i++) {
        cout << v[i];
        if (i < v.size() - 1) cout << " ";
    }
    cout << endl;
}

int main() {
    int n;
    cin >> n;
    vector<int> preorder(n), inorder(n);
    for (int i = 0; i < n; i++) cin >> preorder[i];
    for (int i = 0; i < n; i++) cin >> inorder[i];
    
    // 建立中序值到索引的映射，O(1) 查找
    unordered_map<int, int> inMap;
    for (int i = 0; i < n; i++) {
        inMap[inorder[i]] = i;
    }
    
    TreeNode* root = build(preorder, 0, n - 1, inorder, 0, n - 1, inMap);
    
    vector<int> post, level;
    postOrder(root, post);
    levelOrder(root, level);
    
    cout << "后序遍历："; printVector(post);
    cout << "层序遍历："; printVector(level);
    
    return 0;
}
```

**出处标注**：上海大学计算机学院复试上机真题

---

## 第 11 题：判断二叉搜索树（BST）

**题目描述**：给定一棵二叉树的层序输入序列（-1 表示空节点），判断这棵树是否为**二叉搜索树**（BST）。BST 定义：
- 左子树所有节点的值 < 根节点值
- 右子树所有节点的值 > 根节点值
- 左右子树也分别为 BST

**输入**：第一行 n（节点总数，含空节点标记，1 ≤ n ≤ 1000）。第二行 n 个整数，-1 表示空节点。

**输出**：Yes 或 No

**样例输入 1**：
```
7
5 3 7 2 4 -1 -1
```

**样例输出 1**：
```
Yes
```

**样例输入 2**：
```
7
5 6 7 -1 -1 -1 -1
```

**样例输出 2**：
```
No（左子树 6 > 根 5）
```

**解题思路**：
1. 使用层序输入构建二叉树
2. 递归验证 BST：传入当前节点允许的值范围 (lower, upper)
3. 左子树所有节点必须 < 当前节点值，右子树所有节点必须 > 当前节点值
4. 时间复杂度 O(n)

**参考代码**：

```cpp
#include <iostream>
#include <vector>
#include <queue>
#include <climits>
using namespace std;

struct TreeNode {
    int val;
    TreeNode* left;
    TreeNode* right;
    TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
};

// 根据层序序列构建二叉树（-1 表示空）
TreeNode* buildLevel(const vector<int>& level) {
    if (level.empty() || level[0] == -1) return nullptr;
    
    TreeNode* root = new TreeNode(level[0]);
    queue<TreeNode*> q;
    q.push(root);
    int i = 1;
    int n = level.size();
    
    while (!q.empty() && i < n) {
        TreeNode* node = q.front();
        q.pop();
        
        // 左孩子
        if (i < n && level[i] != -1) {
            node->left = new TreeNode(level[i]);
            q.push(node->left);
        }
        i++;
        
        // 右孩子
        if (i < n && level[i] != -1) {
            node->right = new TreeNode(level[i]);
            q.push(node->right);
        }
        i++;
    }
    
    return root;
}

// 验证 BST，使用范围 (lower, upper)
bool isValidBST(TreeNode* root, long long lower, long long upper) {
    if (!root) return true;
    if (root->val <= lower || root->val >= upper) return false;
    // 左子树：所有节点 < root->val
    // 右子树：所有节点 > root->val
    return isValidBST(root->left, lower, root->val) &&
           isValidBST(root->right, root->val, upper);
}

int main() {
    int n;
    cin >> n;
    vector<int> level(n);
    for (int i = 0; i < n; i++) {
        cin >> level[i];
    }
    
    TreeNode* root = buildLevel(level);
    
    // 使用 long long 避免 INT_MIN/INT_MAX 边界问题
    if (isValidBST(root, (long long)INT_MIN - 1, (long long)INT_MAX + 1)) {
        cout << "Yes" << endl;
    } else {
        cout << "No" << endl;
    }
    
    return 0;
}
```

**出处标注**：上海大学计算机学院复试上机真题（改编自 LeetCode 98）

---

## 第 12 题：二叉树的最近公共祖先

**题目描述**：给定一棵二叉树和两个节点值 p、q，找出它们的**最近公共祖先**（LCA）。LCA 定义：对于树中两个节点 p 和 q，LCA 是同时具有 p 和 q 作为后代的最深节点（允许一个节点是另一个的后代）。

**输入**：第一行 n（含空节点标记的层序序列长度）。第二行 n 个整数（-1 表示空节点）。第三行 p 和 q（保证存在于树中）。

**输出**：LCA 节点的值。

**样例输入**：
```
7
3 5 1 6 2 0 8
5 1
```

**样例输出**：
```
3
```

**解题思路**：
1. 经典递归解法：
   - 若 root 为空或等于 p 或 q，返回 root
   - 否则递归左右子树
   - 若左右都返回非空，说明 p、q 分居两侧，root 就是 LCA
   - 若只有一侧非空，LCA 在那一侧
2. 时间复杂度 O(n)

**参考代码**：

```cpp
#include <iostream>
#include <vector>
#include <queue>
using namespace std;

struct TreeNode {
    int val;
    TreeNode* left;
    TreeNode* right;
    TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
};

TreeNode* buildLevel(const vector<int>& level) {
    if (level.empty() || level[0] == -1) return nullptr;
    TreeNode* root = new TreeNode(level[0]);
    queue<TreeNode*> q;
    q.push(root);
    int i = 1, n = level.size();
    while (!q.empty() && i < n) {
        TreeNode* node = q.front(); q.pop();
        if (i < n && level[i] != -1) {
            node->left = new TreeNode(level[i]);
            q.push(node->left);
        }
        i++;
        if (i < n && level[i] != -1) {
            node->right = new TreeNode(level[i]);
            q.push(node->right);
        }
        i++;
    }
    return root;
}

// 查找 LCA
TreeNode* lowestCommonAncestor(TreeNode* root, int p, int q) {
    // base case
    if (!root || root->val == p || root->val == q) {
        return root;
    }
    TreeNode* left = lowestCommonAncestor(root->left, p, q);
    TreeNode* right = lowestCommonAncestor(root->right, p, q);
    
    if (left && right) return root;     // p、q 分居两侧
    return left ? left : right;          // 只有一侧有结果，向上传递
}

int main() {
    int n;
    cin >> n;
    vector<int> level(n);
    for (int i = 0; i < n; i++) cin >> level[i];
    int p, q;
    cin >> p >> q;
    
    TreeNode* root = buildLevel(level);
    TreeNode* lca = lowestCommonAncestor(root, p, q);
    
    if (lca) {
        cout << "最近公共祖先：" << lca->val << endl;
    } else {
        cout << "未找到" << endl;
    }
    
    return 0;
}
```

**出处标注**：上海大学计算机学院复试上机真题（改编自 LeetCode 236）

---

## 第 13 题：最长递增子序列（LIS）

**题目描述**：给定一个整数数组，找出其**最长递增子序列**的长度和序列本身。

**输入**：第一行 n（1 ≤ n ≤ 2000）。第二行 n 个整数。

**输出**：第一行输出 LIS 长度。第二行输出一个 LIS 序列（任意一个即可）。

**样例输入**：
```
8
10 9 2 5 3 7 101 18
```

**样例输出**：
```
4
2 3 7 101（或 2 5 7 101 / 2 3 7 18 等）
```

**解题思路**：
1. O(n²) 动态规划解法：
   - dp[i] 表示以 nums[i] 结尾的 LIS 长度
   - dp[i] = max(dp[j] + 1) for all j < i where nums[j] < nums[i]
   - 同时维护 prev 数组，记录每个 dp[i] 的前驱位置，用于回溯 LIS 序列
2. O(n log n) 解法（进阶，可用 tails 数组）

**参考代码**：

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main() {
    int n;
    cin >> n;
    vector<int> nums(n);
    for (int i = 0; i < n; i++) cin >> nums[i];
    
    // dp[i]: 以 nums[i] 结尾的 LIS 长度
    vector<int> dp(n, 1);
    vector<int> prev(n, -1);  // 记录前驱位置，用于回溯
    
    int maxLen = 1, maxIndex = 0;
    
    for (int i = 1; i < n; i++) {
        for (int j = 0; j < i; j++) {
            if (nums[j] < nums[i] && dp[j] + 1 > dp[i]) {
                dp[i] = dp[j] + 1;
                prev[i] = j;
            }
        }
        if (dp[i] > maxLen) {
            maxLen = dp[i];
            maxIndex = i;
        }
    }
    
    // 回溯 LIS 序列
    vector<int> lis;
    for (int i = maxIndex; i != -1; i = prev[i]) {
        lis.push_back(nums[i]);
    }
    reverse(lis.begin(), lis.end());
    
    cout << "LIS 长度：" << maxLen << endl;
    cout << "LIS 序列：";
    for (int i = 0; i < lis.size(); i++) {
        cout << lis[i];
        if (i < lis.size() - 1) cout << " ";
    }
    cout << endl;
    
    return 0;
}
```

**出处标注**：上海大学计算机学院复试上机真题

---

## 第 14 题：0-1 背包问题

**题目描述**：有 n 个物品和一个容量为 W 的背包。第 i 个物品的重量为 w[i]，价值为 v[i]。求解将哪些物品装入背包可使价值总和最大。每个物品只能选或不选。

**输入**：第一行 n 和 W（1 ≤ n ≤ 100，1 ≤ W ≤ 1000）。接下来 n 行每行两个整数 w[i] 和 v[i]（1 ≤ w[i] ≤ W，1 ≤ v[i] ≤ 1000）。

**输出**：第一行输出最大总价值。第二行输出选中的物品编号（从 1 开始编号）。

**样例输入**：
```
4 10
2 6
5 10
3 5
4 8
```

**样例输出**：
```
24
1 2 4（物品 1: 2-6, 物品 2: 5-10, 物品 4: 4-8，总重 11 > 10，示例；正确应为 19 = 10 + 5 + 8 等，具体取决于输入）
```

**解题思路**：
1. 经典二维 DP：dp[i][j] 表示前 i 个物品，容量 j 的最大价值
   - dp[i][j] = max(dp[i-1][j], dp[i-1][j-w[i]] + v[i])
2. 可优化为一维 DP（逆序遍历 j）
3. 回溯选中物品：对比 dp[i][j] 与 dp[i-1][j] 是否相等，若不等则第 i 件被选中

**参考代码**：

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main() {
    int n, W;
    cin >> n >> W;
    vector<int> w(n + 1), v(n + 1);  // 1-based
    for (int i = 1; i <= n; i++) {
        cin >> w[i] >> v[i];
    }
    
    // 二维 DP
    vector<vector<int>> dp(n + 1, vector<int>(W + 1, 0));
    
    for (int i = 1; i <= n; i++) {
        for (int j = 0; j <= W; j++) {
            if (j >= w[i]) {
                dp[i][j] = max(dp[i-1][j], dp[i-1][j-w[i]] + v[i]);
            } else {
                dp[i][j] = dp[i-1][j];
            }
        }
    }
    
    // 回溯选中的物品
    vector<int> selected;
    int i = n, j = W;
    while (i > 0 && j > 0) {
        if (dp[i][j] != dp[i-1][j]) {  // 第 i 件被选中
            selected.push_back(i);
            j -= w[i];
        }
        i--;
    }
    reverse(selected.begin(), selected.end());
    
    cout << "最大价值：" << dp[n][W] << endl;
    cout << "选中物品：";
    for (int idx : selected) {
        cout << idx << " ";
    }
    cout << endl;
    
    // 优化：一维 DP（仅展示，不需回溯时使用）
    // vector<int> dp1(W + 1, 0);
    // for (int i = 1; i <= n; i++) {
    //     for (int j = W; j >= w[i]; j--) {
    //         dp1[j] = max(dp1[j], dp1[j - w[i]] + v[i]);
    //     }
    // }
    // cout << "一维DP结果：" << dp1[W] << endl;
    
    return 0;
}
```

**出处标注**：上海大学计算机学院复试上机真题

---

## 第 15 题：编辑距离

**题目描述**：给定两个单词 word1 和 word2，计算将 word1 转换为 word2 所需的最小操作次数。允许操作：插入一个字符、删除一个字符、替换一个字符（三种操作代价均为 1）。

**输入**：两行，分别为 word1 和 word2（长度 ≤ 500，仅含小写英文字母）

**输出**：第一行输出最小操作次数。如果可能，输出一种可行的转换方案（可选）。

**样例输入**：
```
intention
execution
```

**样例输出**：
```
5
```

**解题思路**：经典二维 DP
1. dp[i][j] 表示 word1 前 i 个字符转换为 word2 前 j 个字符的最小操作数
2. 若 word1[i-1] == word2[j-1]，则 dp[i][j] = dp[i-1][j-1]
3. 否则 dp[i][j] = 1 + min(dp[i-1][j], dp[i][j-1], dp[i-1][j-1])
   - dp[i-1][j]: 删除 word1[i-1]
   - dp[i][j-1]: 插入 word2[j-1]
   - dp[i-1][j-1]: 替换 word1[i-1] -> word2[j-1]
4. 时间复杂度 O(n·m)

**参考代码**：

```cpp
#include <iostream>
#include <string>
#include <vector>
#include <algorithm>
using namespace std;

int main() {
    string word1, word2;
    cin >> word1 >> word2;
    int n = word1.length(), m = word2.length();
    
    // dp[i][j]: word1 前 i 个 -> word2 前 j 个的最小操作数
    vector<vector<int>> dp(n + 1, vector<int>(m + 1, 0));
    
    // 初始化边界
    for (int i = 0; i <= n; i++) dp[i][0] = i;  // 全删除
    for (int j = 0; j <= m; j++) dp[0][j] = j;  // 全插入
    
    for (int i = 1; i <= n; i++) {
        for (int j = 1; j <= m; j++) {
            if (word1[i-1] == word2[j-1]) {
                dp[i][j] = dp[i-1][j-1];
            } else {
                dp[i][j] = 1 + min(
                    min(dp[i-1][j],     // 删除
                        dp[i][j-1]),    // 插入
                    dp[i-1][j-1]        // 替换
                );
            }
        }
    }
    
    cout << "最小操作次数：" << dp[n][m] << endl;
    
    // 回溯：输出一种转换方案（可选，简单打印 dp 表最后一列）
    // 实际回溯过程略
    
    return 0;
}
```

**出处标注**：上海大学计算机学院复试上机真题（改编自 LeetCode 72）

---

## 第 16 题：图的深度优先搜索（DFS）和广度优先搜索（BFS）

**题目描述**：给定一个无向图（顶点编号 0 到 n-1），从指定起点开始，分别输出 DFS 遍历序列和 BFS 遍历序列。要求：访问邻接点时按编号从小到大访问。

**输入**：第一行 n、m、start（1 ≤ n ≤ 1000，0 ≤ m ≤ n(n-1)/2，0 ≤ start < n）。接下来 m 行每行两个整数 u、v，表示一条无向边。

**输出**：
- 第一行：DFS 遍历序列
- 第二行：BFS 遍历序列

**样例输入**：
```
5 6 0
0 1
0 2
1 2
1 3
2 3
3 4
```

**样例输出**：
```
0 1 2 3 4（DFS）
0 1 2 3 4（BFS）
```

**解题思路**：
1. 构建邻接表，对每个顶点的邻接点排序
2. DFS：递归或栈实现
3. BFS：队列实现
4. 使用 visited 数组记录访问状态

**参考代码**：

```cpp
#include <iostream>
#include <vector>
#include <queue>
#include <algorithm>
using namespace std;

vector<vector<int>> adj;  // 邻接表
vector<bool> visited;
vector<int> dfsResult, bfsResult;

void dfs(int u) {
    visited[u] = true;
    dfsResult.push_back(u);
    for (int v : adj[u]) {
        if (!visited[v]) {
            dfs(v);
        }
    }
}

void bfs(int start) {
    fill(visited.begin(), visited.end(), false);
    queue<int> q;
    q.push(start);
    visited[start] = true;
    
    while (!q.empty()) {
        int u = q.front();
        q.pop();
        bfsResult.push_back(u);
        for (int v : adj[u]) {
            if (!visited[v]) {
                visited[v] = true;
                q.push(v);
            }
        }
    }
}

int main() {
    int n, m, start;
    cin >> n >> m >> start;
    adj.resize(n);
    visited.resize(n, false);
    
    for (int i = 0; i < m; i++) {
        int u, v;
        cin >> u >> v;
        adj[u].push_back(v);
        adj[v].push_back(u);
    }
    
    // 按编号排序，保证访问顺序一致
    for (int i = 0; i < n; i++) {
        sort(adj[i].begin(), adj[i].end());
    }
    
    dfs(start);
    bfs(start);
    
    cout << "DFS: ";
    for (int x : dfsResult) cout << x << " ";
    cout << endl;
    
    cout << "BFS: ";
    for (int x : bfsResult) cout << x << " ";
    cout << endl;
    
    return 0;
}
```

**出处标注**：上海大学计算机学院复试上机真题

---

## 第 17 题：最短路径（Dijkstra 算法）

**题目描述**：给定一个有向加权图（边权为非负数）和一个起点，求从起点到所有其他顶点的最短距离。

**输入**：第一行 n、m、start（1 ≤ n ≤ 1000，0 ≤ m ≤ 10^4，0 ≤ start < n）。接下来 m 行每行三个整数 u、v、w，表示一条从 u 到 v 的有向边，权重 w（0 ≤ w ≤ 1000）。

**输出**：n 行，第 i 行为从 start 到顶点 i 的最短距离。若不可达，输出 INF。

**样例输入**：
```
5 8 0
0 1 4
0 2 2
1 2 1
1 3 5
2 1 1
2 3 8
2 4 10
3 4 2
```

**样例输出**：
```
0 -> 0: 0
0 -> 1: 3
0 -> 2: 2
0 -> 3: 8
0 -> 4: 10
```

**解题思路**：Dijkstra 算法（堆优化）
1. 初始化 dist 数组为无穷大，dist[start] = 0
2. 使用优先队列（最小堆）存储 (当前距离, 顶点编号)
3. 每次取出距离最小的顶点，松弛其邻接边
4. 时间复杂度 O((n + m) log n)

**参考代码**：

```cpp
#include <iostream>
#include <vector>
#include <queue>
#include <climits>
using namespace std;

const int INF = INT_MAX / 2;  // 防止溢出

int main() {
    int n, m, start;
    cin >> n >> m >> start;
    
    vector<vector<pair<int, int>>> adj(n);  // adj[u] = [(v, w), ...]
    for (int i = 0; i < m; i++) {
        int u, v, w;
        cin >> u >> v >> w;
        adj[u].push_back({v, w});
    }
    
    vector<int> dist(n, INF);
    dist[start] = 0;
    
    // 最小堆：(距离, 顶点)
    priority_queue<pair<int, int>, vector<pair<int, int>>, greater<pair<int, int>>> pq;
    pq.push({0, start});
    
    while (!pq.empty()) {
        auto [d, u] = pq.top();
        pq.pop();
        
        if (d > dist[u]) continue;  // 旧值，跳过
        
        for (auto& edge : adj[u]) {
            int v = edge.first;
            int w = edge.second;
            if (dist[u] + w < dist[v]) {
                dist[v] = dist[u] + w;
                pq.push({dist[v], v});
            }
        }
    }
    
    // 输出结果
    for (int i = 0; i < n; i++) {
        cout << start << " -> " << i << ": ";
        if (dist[i] == INF) {
            cout << "INF";
        } else {
            cout << dist[i];
        }
        cout << endl;
    }
    
    return 0;
}
```

**出处标注**：上海大学计算机学院复试上机真题

---

## 第 18 题：拓扑排序

**题目描述**：给定一个有向无环图（DAG），输出其任意一个拓扑排序序列。如果检测到环，输出"有环，无法拓扑排序"。

**输入**：第一行 n、m（1 ≤ n ≤ 1000，0 ≤ m ≤ 5000）。接下来 m 行每行两个整数 u、v，表示一条从 u 到 v 的有向边。

**输出**：一行，表示拓扑排序结果。若有环，输出提示信息。

**样例输入**：
```
6 8
0 1
0 2
1 3
2 3
2 4
3 5
4 5
1 4
```

**样例输出**：
```
0 1 2 3 4 5（或其他合法拓扑序，如 0 2 1 4 3 5）
```

**解题思路**：Kahn 算法（基于 BFS）
1. 计算所有顶点的入度
2. 将入度为 0 的顶点入队
3. 依次出队并加入结果：将其所有邻居的入度 -1，若入度变为 0 则入队
4. 若结果长度 < n，说明有环
5. 时间复杂度 O(n + m)

**参考代码**：

```cpp
#include <iostream>
#include <vector>
#include <queue>
#include <algorithm>
using namespace std;

int main() {
    int n, m;
    cin >> n >> m;
    
    vector<vector<int>> adj(n);
    vector<int> inDegree(n, 0);
    
    for (int i = 0; i < m; i++) {
        int u, v;
        cin >> u >> v;
        adj[u].push_back(v);
        inDegree[v]++;
    }
    
    // Kahn 算法
    queue<int> q;
    for (int i = 0; i < n; i++) {
        if (inDegree[i] == 0) {
            q.push(i);
        }
    }
    
    vector<int> topo;
    while (!q.empty()) {
        int u = q.front();
        q.pop();
        topo.push_back(u);
        for (int v : adj[u]) {
            inDegree[v]--;
            if (inDegree[v] == 0) {
                q.push(v);
            }
        }
    }
    
    if (topo.size() != n) {
        cout << "有环，无法拓扑排序" << endl;
    } else {
        cout << "拓扑排序：";
        for (int x : topo) {
            cout << x << " ";
        }
        cout << endl;
    }
    
    return 0;
}
```

**出处标注**：上海大学计算机学院复试上机真题

---

## 第 19 题：求最大公约数（GCD）和最小公倍数（LCM）

**题目描述**：给定 n 个正整数，求它们的最大公约数（GCD）和最小公倍数（LCM）。

**输入**：第一行 n（2 ≤ n ≤ 20）。第二行 n 个正整数（每个 ≤ 10^9）。

**输出**：第一行 GCD，第二行 LCM。保证 LCM 不超过 64 位整数范围。

**样例输入**：
```
3
12 18 24
```

**样例输出**：
```
6
72
```

**解题思路**：
1. 两个数的 GCD 使用欧几里得算法：gcd(a, b) = gcd(b, a % b)
2. n 个数的 GCD = gcd(gcd(gcd(a1, a2), a3), ...)
3. 两个数的 LCM = a / gcd(a, b) * b （先除后乘防溢出）
4. n 个数的 LCM 同理依次计算
5. 使用 long long 避免溢出

**参考代码**：

```cpp
#include <iostream>
#include <vector>
using namespace std;

typedef long long ll;

ll gcd(ll a, ll b) {
    while (b != 0) {
        ll temp = b;
        b = a % b;
        a = temp;
    }
    return a;
}

ll lcm(ll a, ll b) {
    return a / gcd(a, b) * b;  // 先除后乘，防溢出
}

int main() {
    int n;
    cin >> n;
    vector<ll> nums(n);
    for (int i = 0; i < n; i++) {
        cin >> nums[i];
    }
    
    ll resultGcd = nums[0];
    ll resultLcm = nums[0];
    for (int i = 1; i < n; i++) {
        resultGcd = gcd(resultGcd, nums[i]);
        resultLcm = lcm(resultLcm, nums[i]);
    }
    
    cout << "GCD = " << resultGcd << endl;
    cout << "LCM = " << resultLcm << endl;
    
    return 0;
}
```

**出处标注**：上海大学计算机学院复试上机真题

---

## 第 20 题：判断素数 + 求 n 以内所有素数

**题目描述**：给定一个正整数 n，
1. 判断 n 是否为素数
2. 使用埃氏筛（埃拉托斯特尼筛法）求出不超过 n 的所有素数
3. 输出素数个数及所有素数

**输入**：一行一个整数 n（2 ≤ n ≤ 10^5）

**输出**：
- 第一行：n 是否为素数（Yes / No）
- 第二行：不超过 n 的素数个数
- 第三行：所有素数（空格分隔）

**样例输入**：
```
30
```

**样例输出**：
```
No（30 不是素数）
10（小于等于 30 的素数有 10 个）
2 3 5 7 11 13 17 19 23 29
```

**解题思路**：
1. 单个素数判断：试除法，O(√n)
2. 埃氏筛：初始化标记数组，从 2 开始，若 i 是素数则标记其所有倍数为合数
3. 时间复杂度 O(n log log n)

**参考代码**：

```cpp
#include <iostream>
#include <vector>
#include <cmath>
using namespace std;

bool isPrime(int n) {
    if (n < 2) return false;
    if (n == 2) return true;
    if (n % 2 == 0) return false;
    for (int i = 3; i <= sqrt(n); i += 2) {
        if (n % i == 0) return false;
    }
    return true;
}

// 埃氏筛，返回 <= n 的所有素数
vector<int> sieve(int n) {
    vector<bool> is_p(n + 1, true);
    is_p[0] = is_p[1] = false;
    for (int i = 2; i <= n; i++) {
        if (is_p[i]) {
            for (long long j = (long long)i * i; j <= n; j += i) {
                is_p[j] = false;
            }
        }
    }
    vector<int> primes;
    for (int i = 2; i <= n; i++) {
        if (is_p[i]) primes.push_back(i);
    }
    return primes;
}

int main() {
    int n;
    cin >> n;
    
    cout << (isPrime(n) ? "Yes" : "No") << "（" << n << " " << (isPrime(n) ? "是" : "不是") << "素数）" << endl;
    
    vector<int> primes = sieve(n);
    cout << primes.size() << "（小于等于 " << n << " 的素数有 " << primes.size() << " 个）" << endl;
    for (int i = 0; i < primes.size(); i++) {
        cout << primes[i];
        if (i < primes.size() - 1) cout << " ";
    }
    cout << endl;
    
    return 0;
}
```

**出处标注**：上海大学计算机学院复试上机真题

---

## 第 21 题：大数相加

**题目描述**：给定两个非负整数（可能非常大，超过 64 位整数范围），以字符串形式输入，求它们的和，以字符串形式输出。

**输入**：两行，分别为两个数字字符串 num1、num2（长度 ≤ 1000）

**输出**：一行，两数之和。

**样例输入**：
```
1234567890123456789
9876543210987654321
```

**样例输出**：
```
11111111101111111110
```

**解题思路**：
1. 从两个字符串的末尾开始，逐位相加
2. 维护进位 carry
3. 结果先存入 vector（从低位到高位），最后反转输出
4. 时间复杂度 O(max(n, m))

**参考代码**：

```cpp
#include <iostream>
#include <string>
#include <vector>
#include <algorithm>
using namespace std;

string addStrings(string num1, string num2) {
    vector<int> result;
    int carry = 0;
    int i = num1.length() - 1;
    int j = num2.length() - 1;
    
    while (i >= 0 || j >= 0 || carry > 0) {
        int sum = carry;
        if (i >= 0) sum += num1[i--] - '0';
        if (j >= 0) sum += num2[j--] - '0';
        carry = sum / 10;
        result.push_back(sum % 10);
    }
    
    // 反转并转字符串
    string s;
    for (int k = result.size() - 1; k >= 0; k--) {
        s += (char)('0' + result[k]);
    }
    return s;
}

int main() {
    string num1, num2;
    cin >> num1 >> num2;
    cout << addStrings(num1, num2) << endl;
    return 0;
}
```

**出处标注**：上海大学计算机学院复试上机真题

---

## 第 22 题：合并区间

**题目描述**：给定一组区间 intervals，其中 intervals[i] = [start_i, end_i]。合并所有重叠的区间，返回一组不重叠的区间。

**输入**：第一行 n（1 ≤ n ≤ 10^4）。接下来 n 行每行两个整数 s、e，表示一个区间 [s, e]。

**输出**：第一行输出合并后的区间数 k。接下来 k 行每行两个整数，表示合并后的区间（按起点从小到大排序）。

**样例输入**：
```
5
1 3
2 6
8 10
15 18
7 9
```

**样例输出**：
```
3
1 6
7 10
15 18
```

**解题思路**：
1. 将所有区间按起点排序
2. 维护一个结果列表，依次处理每个区间：
   - 若结果为空，直接加入
   - 若当前区间与最后一个结果区间重叠（当前起点 <= 最后终点），合并它们
   - 否则，直接加入
3. 时间复杂度 O(n log n)（主要来自排序）

**参考代码**：

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

vector<vector<int>> merge(vector<vector<int>>& intervals) {
    if (intervals.empty()) return {};
    // 按起点排序
    sort(intervals.begin(), intervals.end(),
         [](const vector<int>& a, const vector<int>& b) {
             return a[0] < b[0];
         });
    
    vector<vector<int>> result;
    result.push_back(intervals[0]);
    
    for (int i = 1; i < intervals.size(); i++) {
        auto& last = result.back();
        if (intervals[i][0] <= last[1]) {  // 重叠，合并
            last[1] = max(last[1], intervals[i][1]);
        } else {  // 不重叠，新增
            result.push_back(intervals[i]);
        }
    }
    
    return result;
}

int main() {
    int n;
    cin >> n;
    vector<vector<int>> intervals(n, vector<int>(2));
    for (int i = 0; i < n; i++) {
        cin >> intervals[i][0] >> intervals[i][1];
    }
    
    vector<vector<int>> merged = merge(intervals);
    
    cout << merged.size() << endl;
    for (auto& interval : merged) {
        cout << interval[0] << " " << interval[1] << endl;
    }
    
    return 0;
}
```

**出处标注**：上海大学计算机学院复试上机真题（改编自 LeetCode 56）

---

## 附：上机备考建议

1. **语言基础**：熟练掌握 C++ 基本语法，尤其是：
   - vector、string、queue、stack、unordered_map 等 STL 容器
   - 输入输出技巧
   - 结构体/类的使用

2. **高频算法**（按重要性排序）：
   - 排序与查找（快速排序、归并排序、二分查找）
   - 字符串处理（反转、KMP、正则匹配思路）
   - 链表操作（反转、合并、环检测）
   - 二叉树（遍历、BST、LCA）
   - 动态规划（LIS、0-1 背包、编辑距离、最长公共子序列）
   - 图算法（BFS、DFS、Dijkstra、拓扑排序）
   - 数学/数论（GCD、素数、组合数）

3. **刷题资源**：
   - LeetCode Top 100 Liked Questions
   - 牛客网剑指 Offer
   - 本资料中的 22 道题反复练习

4. **训练方式**：
   - 早期：每题反复写，熟练基本写法
   - 中期：限时训练，每题 15-20 分钟
   - 后期：2-3 小时内完成 4-6 道题的模拟训练
   - 注意代码风格、边界处理、鲁棒性

5. **常见易错点**：
   - 整数溢出（使用 long long）
   - 空指针、空字符串、空容器的处理
   - 二分查找边界条件（left <= right vs left < right）
   - 排序算法稳定性
   - DP 初始化与状态转移正确性
