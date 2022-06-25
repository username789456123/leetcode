int maximumWealth(int** accounts, int accountsSize, int* accountsColSize)
{
    int i,j,maxWealth = 0;
    int value[accountsSize];
    memset(value,0, sizeof(value));
    for(i =0; i < accountsSize; i++)
    {
        for(j = 0 ; j < accountsColSize[i] ; j++ )
        {
            value[i] +=  accounts[i][j];
        }
        maxWealth = fmax(maxWealth,value[i]);
    }
    return maxWealth;
}
