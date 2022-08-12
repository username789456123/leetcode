int networkDelayTime(int** times, int timesSize, int* timesColSize, int n, int k) {
    const int inf = 0x3f3f3f3f;
    int g[n][n];
    memset(g, 0x3f, sizeof(g));
    for (int i = 0; i < timesSize; i++) {
        int x = times[i][0] - 1, y = times[i][1] - 1;
        g[x][y] = times[i][2];
    }

    int dist[n];
    memset(dist, 0x3f, sizeof(dist));
    dist[k - 1] = 0;
    int used[n];
    memset(used, 0, sizeof(used));
    int ans = 0;
    for (int i = 0; i < n; ++i) {
        int x = -1;
        for (int y = 0; y < n; ++y) {
            if (!used[y] && (x == -1 || dist[y] < dist[x])) {
                x = y;
            }
        }
        used[x] = true;
        ans = fmax(ans, dist[x]);
        for (int y = 0; y < n; ++y) {
            dist[y] = fmin(dist[y], dist[x] + g[x][y]);
        }
    }

    return ans == inf ? -1 : ans;
}
