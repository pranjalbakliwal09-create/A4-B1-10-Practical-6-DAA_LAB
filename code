#include <stdio.h>
#define MAX 20
#define INF 999999

int main()
{
    int n, i, j, k, l;
    float p[MAX], q[MAX];
    float w[MAX][MAX], c[MAX][MAX];
    float min, sum;
    int key[MAX];

    printf("Enter number of keys:");
    scanf("%d", &n);

    printf("Enter %d keys:\n", n);
    for (i = 1; i <= n; i++) {
        scanf("%d", &key[i]);
    }

    printf("Enter %d (p[i]):\n", n);
    for (i = 1; i <= n; i++) {
        scanf("%f", &p[i]);
    }

    printf("Enter %d  (q[i]):\n", n + 1);
    for (i = 0; i <= n; i++) {
        scanf("%f", &q[i]);
    }

    
    for (i = 0; i <= n; i++) {
        c[i][i] = 0;
        w[i][i] = q[i];
    }

    for (l = 1; l <= n; l++) {
        for (i = 0; i <= n - l; i++) {
            j = i + l;
            w[i][j] = w[i][j - 1] + p[j] + q[j];
            min = INF;
            for (k = i + 1; k <= j; k++) {
                sum = c[i][k - 1] + c[k][j];
                if (sum < min)
                    min = sum;
            }
            c[i][j] = w[i][j] + min;
        }
    }

    printf("Minimum Expected Search Cost for Optimal BST = %.4f\n", c[0][n]);
    return 0;
}
