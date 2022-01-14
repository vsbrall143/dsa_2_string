# dsa_2_string
Operations on Strings


#include <stdio.h>
#include <stdlib.h>

int i, m, c, k, j, flag = 0;
char rep[50], str[100], pat[50], ans[100];

void stringmatch()
{
    int m = c = j = i = 0;
    while (str[c] != '\0')
    {
        if (str[m] == pat[i])                          //occurance found
        {
            i++;
            m++;
            if (pat[i] == '\0')                         //string match
            {
                flag = 1;
                for (k = 0;rep[k]!= '\0'; k++, j++)        //copy replacement stering to the answer string
                {
                    ans[j] = rep[k];
                    i = 0;
                    c = m;
                }
            }
        }
        else                                            //mismatch
        {
            ans[j] = str[c];                                //printing the main string to the answer string
            c++;
            j++;
            i = 0;
            m = c;
        }
    }
    ans[j] = '\0';
}
void main()
{
    printf("enter the main string\n");
    gets(str);
    printf("enter the pattern string\n");
    gets(pat);
    printf("enter the replacement string\n");
    gets(rep);

    stringmatch();
    if (flag == 1)
    {
        printf("\nthe answer string is \n %s", ans);
    }
    else
    {
        printf("\nthe pattern string not found");
    }
}
