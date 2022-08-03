#define HASH_FIND_LONG(head, findint, out) HASH_FIND(hh, head, findint, sizeof(long), out)
#define HASH_ADD_LONG(head, intfield, add) HASH_ADD(hh, head, intfield, sizeof(long), add)

struct HashTable {
    long key;
    UT_hash_handle hh;
};

void insert(struct HashTable** hashTable, long ikey) {
    struct HashTable* tmp;
    HASH_FIND_LONG(*hashTable, &ikey, tmp);
    if (tmp == NULL) {
        tmp = malloc(sizeof(struct HashTable));
        tmp->key = ikey;
        HASH_ADD_LONG(*hashTable, key, tmp);
    }
}

bool count(struct HashTable** hashTable, long ikey) {
    struct HashTable* tmp;
    HASH_FIND_LONG(*hashTable, &ikey, tmp);
    return tmp == NULL;
}

struct Heap {
    long* heap;
    int heapSize;
    bool (*cmp)(long, long);
};

void init(struct Heap* obj, int n, bool (*cmp)(long, long)) {
    obj->heap = malloc(sizeof(long) * (n + 1));
    obj->heapSize = 0;
    obj->cmp = cmp;
}

bool cmp1(long a, long b) {
    return a > b;
}

void swap(long* a, long* b) {
    long tmp = *a;
    *a = *b, *b = tmp;
}

void push(struct Heap* obj, long x) {
    int p = ++(obj->heapSize), q = p >> 1;
    obj->heap[p] = x;
    while (q) {
        if (!obj->cmp(obj->heap[q], obj->heap[p])) {
            break;
        }
        swap(&(obj->heap[q]), &(obj->heap[p]));
        p = q, q = p >> 1;
    }
}

void pop(struct Heap* obj) {
    swap(&(obj->heap[1]), &(obj->heap[(obj->heapSize)--]));
    int p = 1, q = p << 1;
    while (q <= obj->heapSize) {
        if (q + 1 <= obj->heapSize) {
            if (obj->cmp(obj->heap[q], obj->heap[q + 1])) {
                q++;
            }
        }
        if (!obj->cmp(obj->heap[p], obj->heap[q])) {
            break;
        }
        swap(&(obj->heap[q]), &(obj->heap[p]));
        p = q, q = p << 1;
    }
}

long top(struct Heap* obj) {
    return obj->heap[1];
}

bool empty(struct Heap* obj) {
    return obj->heapSize == 0;
}

int nthUglyNumber(int n) {
    int factors[3] = {2, 3, 5};
    struct HashTable* hashTable = NULL;
    insert(&hashTable, 1);
    struct Heap* heap = malloc(sizeof(struct Heap));
    init(heap, n * 3, cmp1);
    push(heap, 1);
    int ugly = 0;
    for (int i = 0; i < n; i++) {
        long curr = top(heap);
        pop(heap);
        ugly = (int)curr;
        for (int i = 0; i < 3; i++) {
            long next = curr * factors[i];
            if (count(&hashTable, next)) {
                insert(&hashTable, next);
                push(heap, next);
            }
        }
    }
    return ugly;
}
