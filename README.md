# directed_graph_in_adjacency_matrix






[5:11 pm, 05/05/2023] Akshay Pawar: #include<stdio.h>
#define SIZE 10
int G[SIZE][SIZE]; // To store Graph
int nov; // To store no. of Vertices
int noe; // To store no. of edges
void accept()
{
int i,j,k;
printf("How many Vertices : ");
scanf("%d", &nov);
printf("How many Edges : ");
scanf("%d", &noe);
for(k=1; k<=noe; k++)
{
printf("Enter Edge (Vi,Vj) : ");
scanf("%d %d", &i,&j);
G[i][j] = 1;
}
}
void display()
{
int i,j;
printf("\nAdjacency Matrix\n");
printf("------------------\n");
for(i=0; i<nov; i++)
{
for(j=0; j<nov; j++)
{
[5:11 pm, 05/05/2023] Akshay Pawar: printf("%d ", G[i][j]);
}
printf("\n");
}
}
int sum_of_row(int i)
{
int j,sum;
sum = 0;
for(j=0; j<nov; j++)
{
sum = sum + G[i][j];
}
return sum;
}
int sum_of_cols(int j)
{
int i, sum;
sum = 0;
for( i=0; i<nov; i++)
{
sum = sum + G[i][j];
}
return sum;
}
void display_degree()
{
int v,indegree, outdegree, total;
printf("\nTotal Degree of Each Vertex :\n");
[5:11 pm, 05/05/2023] Akshay Pawar: for( v=0; v<nov; v++)
{
outdegree = sum_of_row(v);
indegree = sum_of_cols(v);
total = indegree + outdegree ;
printf("V%d : Indegree = %d OutDegree = %d Total Degree = %d \n", v, 
indegree, outdegree, total);
}
}
int main()
{
accept();
display();
display_degree();
}
OUTPUT
sachin@tca2009: $ gcc directed_adjacency_matrix.c 
sachin@tca2009: $ ./a.out
How many Vertices : 4
How many Edges : 5
Enter Edge (Vi,Vj) : 0 1
Enter Edge (Vi,Vj) : 1 3
Enter Edge (Vi,Vj) : 3 2
Enter Edge (Vi,Vj) : 0 2
Enter Edge (Vi,Vj) : 3 0
Adjacency Matrix
------------------
0 1 1 0 
0 0 0 1 
0 0 0 0 
1 0 1 0
