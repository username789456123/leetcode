int cmp(const void *a, const void *b) {
    int *aa = (int*)a;
    int *bb = (int*)b;
    return aa[0] - bb[0];
}

char *str[] = {"Gold Medal","Silver Medal","Bronze Medal"};

char ** findRelativeRanks(int* score, int scoreSize, int* returnSize){
    int arr[scoreSize][2];
    /* 存储下标, 并从小到大排序 */
    for (int i = 0; i < scoreSize; i++) {
        arr[i][0] = -score[i]; /* 取负后从小到大排序 */
        arr[i][1] = i;
    }
    qsort(arr, scoreSize, sizeof(arr[0]), cmp);

    /* 从小到大进行输出, 输出到对应下标的字符串中 */
    char **res = (char**)malloc(sizeof(char*) * scoreSize);
    for (int i = 0; i < scoreSize; i++) {
        if (i < 3) {
            res[arr[i][1]] = str[i];
        } else {
            res[arr[i][1]] = (char*)malloc(sizeof(char) * 8);
            sprintf(res[arr[i][1]], "%d", i + 1);
        }
    }
    *returnSize = scoreSize;
    return res;
}
