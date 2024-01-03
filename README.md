class Solution {
public:
int solve(const std::string& s) {
        int count = 0;
        for (char c : s)
            count += c - '0';

        return count;
}       
    int numberOfBeams(vector<string>& bank) {
        int prevRowCount = 0;
        int total = 0;

        for (const std::string& row : bank) {
            int curRowCount = solve(row);
            if (curRowCount == 0)
                continue;

            total += curRowCount * prevRowCount;
            prevRowCount = curRowCount;
        }
        return total;
    }
};
