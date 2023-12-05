# Assesment
//Medium 1
public class Solution {
    public TreeNode lowestCommonAncestor(TreeNode root, TreeNode p, TreeNode q) {
        if(root == null){
            return null;
        }
        if(p.val == q.val){
            return null;
        }
        if ((p.val == root.val) || (q.val == root.val)){
            return root;
        }if(((p.val < root.val) && (q.val > root.val)) || ((q.val < root.val) && (p.val > root.val))){
            return root;
        }if(p.val < root.val && q.val < root.val){
            return lowestCommonAncestor(root.left,p,q);
        }else{
            return lowestCommonAncestor(root.right,p,q);
        }
        
    }
}



//Easy 3
class Solution {
public:
    vector<vector<int>> generate(int numRows) {
        vector<vector<int>> f;
        f.push_back(vector<int>(1, 1));
        for (int i = 0; i < numRows - 1; ++i) {
            vector<int> g;
            g.push_back(1);
            for (int j = 0; j < f[i].size() - 1; ++j) {
                g.push_back(f[i][j] + f[i][j + 1]);
            }
            g.push_back(1);
            f.push_back(g);
        }
        return f;
    }
};


//Hard 2
def shortest_palindrome(s):
    i, j = 0, len(s) - 1


    while j >= 0 and s[i] != s[j]:
        j -= 1


    return s[j + 1:][::-1] + s


s1 = "aacecaaa"


print(shortest_palindrome(s1))
