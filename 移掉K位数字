char* removeKdigits(char* num, int k) {
    int n = strlen(num), top = 0;
    char* stk = malloc(sizeof(char) * (n + 1));
    for (int i = 0; i < n; i++) {
        while (top > 0 && stk[top] > num[i] && k) {
            top--, k--;
        }
        stk[++top] = num[i];
    }
    top -= k;

    char* ans = malloc(sizeof(char) * (n + 1));
    int ansSize = 0;
    bool isLeadingZero = true;
    for (int i = 1; i <= top; i++) {
        if (isLeadingZero && stk[i] == '0') {
            continue;
        }
        isLeadingZero = false;
        ans[ansSize++] = stk[i];
    }
    if (ansSize == 0) {
        ans[0] = '0', ans[1] = 0;
    } else {
        ans[ansSize] = 0;
    }
    return ans;
}
