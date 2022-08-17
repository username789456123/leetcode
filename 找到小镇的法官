int findJudge(int n, int** trust, int trustSize, int* trustColSize){
    int* inDegrees = (int *)malloc(sizeof(int)*(n+1));
    int* outDegrees = (int *)malloc(sizeof(int)*(n+1));
    memset(inDegrees, 0, sizeof(int)*(n+1));
    memset(outDegrees, 0, sizeof(int)*(n+1));
    for (int i = 0; i < trustSize; ++i) {
        int x = trust[i][0], y = trust[i][1];
        ++inDegrees[y];
        ++outDegrees[x];
    }
    for (int i = 1; i <= n; ++i) {
        if (inDegrees[i] == n - 1 && outDegrees[i] == 0) {
            return i;
        }
    }
    return -1;
}
