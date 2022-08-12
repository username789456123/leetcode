bool isSelfDividing(int num) {
    int temp = num;
    while (temp > 0) {
        int digit = temp % 10;
        if (digit == 0 || num % digit != 0) {
            return false;
        }
        temp /= 10;
    }
    return true;
}

int* selfDividingNumbers(int left, int right, int* returnSize){
    int * ans = (int *)malloc(sizeof(int) * (right - left + 1));
    int pos = 0;
    for (int i = left; i <= right; i++) {
        if (isSelfDividing(i)) {
            ans[pos++] = i;
        }
    }
    *returnSize = pos;
    return ans;
}
