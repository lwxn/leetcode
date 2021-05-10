```c++
class Solution {
private:
    bool ans = false;
    int dr[4] = {-1,0,1,0};
    int dc[4] = {0,1,0,-1};
    bool vis[1100][1100] = {0};
public:
    bool exist(vector<vector<char>>& board, string word) {
        for(int i = 0;i<board.size();i++)
        {
            for(int j = 0;j<board[i].size();j++)
            {
                if(ans == true) return ans;
                if(board[i][j] == word[0] && !vis[i][j])
                {
                    vis[i][j] = 1;
                    dfs(board,word,1,i,j);
                    vis[i][j] = 0;
                }
                    
            }
        }
        return ans;
    }
    
    void dfs(vector<vector<char>>& board,string word,int count,int r,int c)
    {
        if(count == word.size())
        {
            cout<<"s"<<endl;
            ans = true;
        }
        for(int i = 0;i<4;i++)
        {
            int r1 = r + dr[i];
            int c1 = c + dc[i];
            if(!ans && r1>=0 && r1 <board.size() && c1 >=0 && c1 < board[0].size() && !vis[r1][c1] && word[count] == board[r1][c1])
            {
                vis[r1][c1] = 1;
                dfs(board,word,count+1,r1,c1);
                vis[r1][c1] = 0;
            }
            
        }
    }
};
```

