bool* prefixesDivBy5(int* nums, int numsSize, int* returnSize) {
    *returnSize = numsSize;
    bool* answer = malloc(sizeof(bool) * numsSize);
    int prefix = 0;
    for (int i = 0; i < numsSize; i++) {
        prefix = ((prefix << 1) + nums[i]) % 5;
        answer[i] = prefix == 0;
    }
    return answer;
}
