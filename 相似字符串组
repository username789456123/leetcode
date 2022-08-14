int find(int *f, int x) {
    return f[x] == x ? x : (f[x] = find(f, f[x]));
}

bool check(char *a, char *b, int len) {
    int num = 0;
    for (int i = 0; i < len; i++) {
        if (a[i] != b[i]) {
            num++;
            if (num > 2) {
                return false;
            }
        }
    }
    return true;
}

int numSimilarGroups(char **strs, int strsSize) {
    int n = strsSize;
    int m = strlen(strs[0]);
    int f[n];
    for (int i = 0; i < n; i++) {
        f[i] = i;
    }
    for (int i = 0; i < n; i++) {
        for (int j = i + 1; j < n; j++) {
            int fi = find(f, i), fj = find(f, j);
            if (fi == fj) {
                continue;
            }
            if (check(strs[i], strs[j], m)) {
                f[fi] = fj;
            }
        }
    }
    int ret = 0;
    for (int i = 0; i < n; i++) {
        if (f[i] == i) {
            ret++;
        }
    }
    return ret;
}
