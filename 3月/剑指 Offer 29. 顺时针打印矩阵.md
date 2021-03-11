#### [剑指 Offer 29. 顺时针打印矩阵](https://leetcode-cn.com/problems/shun-shi-zhen-da-yin-ju-zhen-lcof/)

难度简单

输入一个矩阵，按照从外向里以顺时针的顺序依次打印出每一个数字。

 

**示例 1：**

```
输入：matrix = [[1,2,3],[4,5,6],[7,8,9]]
输出：[1,2,3,6,9,8,7,4,5]
```

**示例 2：**

```
输入：matrix = [[1,2,3,4],[5,6,7,8],[9,10,11,12]]
输出：[1,2,3,4,8,12,11,10,9,5,6,7]
```

```c++
class Solution {
public:
    vector<int> spiralOrder(vector<vector<int>>& matrix) {
        vector<int> a;
        if(matrix.empty()){
            return a;
        }
        int r1 = 0;
        int rm = matrix.size()-1;
        int c1 = 0;
        int cm = matrix[0].size()-1;

        while(1){
            for(int i=c1;i<=cm;i++){
                a.push_back(matrix[r1][i]);
            }
            r1++;
            if(r1>rm){
                break;
            }
            for(int i=r1;i<=rm;i++){
                a.push_back(matrix[i][cm]);
            }
            cm--;
            if(cm<c1){
                break;
            }
            for(int i=cm;i>=c1;i--){
                a.push_back(matrix[rm][i]);
            }
            rm--;
            if(rm<r1){
                break;
            }
            for(int i=rm;i>=r1;i--){
                a.push_back(matrix[i][c1]);
            }
            c1++;
            if(c1>cm){
                break;
            }
        }
        return a;
	}
};
```

