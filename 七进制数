char * convertToBase7(int num){
    if (num == 0) {
        return "0";
    }
    bool negative = num < 0;
    num = abs(num);
    char * digits = (char *)malloc(sizeof(char) * 32);
    int pos = 0;
    while (num > 0) {
        digits[pos++] = num % 7 + '0';
        num /= 7;
    }
    if (negative) {
        digits[pos++] = '-';
    }
    for (int l = 0, r = pos - 1; l < r; l++, r--) {
        char c = digits[l];
        digits[l] = digits[r];
        digits[r] = c;
    }
    digits[pos] = '\0';
    return digits;
}
