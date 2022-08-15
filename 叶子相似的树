void dfs(struct TreeNode* node, int* seq, int* seqSize) {
    if (!node->left && !node->right) {
        seq[(*seqSize)++] = node->val;
    } else {
        if (node->left) {
            dfs(node->left, seq, seqSize);
        }
        if (node->right) {
            dfs(node->right, seq, seqSize);
        }
    }
}

bool leafSimilar(struct TreeNode* root1, struct TreeNode* root2) {
    int seq1[200], seq1Size = 0;
    if (root1) {
        dfs(root1, seq1, &seq1Size);
    }

    int seq2[200], seq2Size = 0;
    if (root2) {
        dfs(root2, seq2, &seq2Size);
    }
    if (seq1Size != seq2Size) {
        return false;
    }
    for (int i = 0; i < seq1Size; i++) {
        if (seq1[i] != seq2[i]) {
            return false;
        }
    }
    return true;
}
