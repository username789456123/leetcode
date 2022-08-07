bool repeatedSubstringPattern(char* s) {
    int n = strlen(s);
    for (int i = 1; i * 2 <= n; ++i) {
        if (n % i == 0) {
            bool match = true;
            for (int j = i; j < n; ++j) {
                if (s[j] != s[j - i]) {
                    match = false;
                    break;
                }
            }
            if (match) {
                return true;
            }
        }
    }
    return false;
}
