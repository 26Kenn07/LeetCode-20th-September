# LeetCode-20th-September
class Solution {
public:
    int findLength(vector<int>& nums1, vector<int>& nums2) {
        int a = nums1.size(), b = nums2.size();
        vector<vector<int>> dp(a, vector<int>(b, 0));
        int ans = 0;
        for (int i = 0; i < a; i++) {
            for (int j = 0; j < b; j++) {
                if (nums1[i] == nums2[j]) {
                    if (i == 0 || j == 0)
                    {
                        dp[i][j] = 1;
                    }
                    else 
                    {
                        dp[i][j] = dp[i-1][j-1] + 1;
                    }
                    ans = max(ans, dp[i][j]);
                        
                }
            }
        }
        return ans;
    }
};
