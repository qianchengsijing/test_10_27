# test_10_27
#include <stdio.h>
typedef struct Linknode{
	int data;
	struct Linknode* next;
}Linknode;

#define MaxVertexNum 100
#define INFINITY 100
typedef struct VertexType
typedef struct EdgeType
typedef struct{
	VertexType vex[MaxVertexNum];
	EdgeType Edge[MaxVertexNum][MaxVertexNum];
	int vexnum,arcnum;
}MGraph;
typedef struct{
	Linknode* front,*rear;
}LinkQueue;
//图的广度优先遍历
bool visited[MAX_VERTEX_NUM]

void BFS(Graph G,int v){
	visit(v);
	visited[v] = true;
	EnQueue(Q,v);
	while(!IsEmpty(Q)){
		DeQueue(Q,v);
		for(w=FirstNeighbor(G,v);w>=0;w=NextNeighbor(G,v,w)){
			if(!visited[w]){
				visit(w);
				visited[w] = true;
				DeQueue(Q,w);
			}
		}
	}
}
//应对非连通图
bool visited[MAX_VERTEX_NUM]

void BFSTraverse(Graph G){
	for(int i=0;i<G.vexnum;i++){
		visited[i] = False;
	}
	InitQueue(Q);
	for(int i=0;i<G.vexnum;i++){
		if(!visited[i])
			BFS(G,i);
	}
}
void BFS(Graph G,int v){
	visit(v);
	visited[v] = true;
	EnQueue(Q,v);
	while(!IsEmpty(Q)){
		DeQueue(Q,v);
		for(w=FirstNeighbor(G,v);w>=0;w=NextNeighbor(G,v,w)){
			if(!visited[w]){
				visit(w);
				visited[w] = true;
				DeQueue(Q,w);
			}
		}
	}
}
//图的深度优先遍历
bool visited[Max_Vertex_Num]

//应对非连通图
void DFSTraverse(Graph G){
	for(v=0;v<G.vexnum;++v)
		visited[v] = false;
	for(v=0;v<G.vexnum;++v)
		if(!visited[v])
			DFS(G,v);
}
void DFS(Graph G,int v){
	visit(v);
	visited[v] = true;
	for(int w=FirstNeighbor(G,v);w>=0;w=NextNeighbor(G,v,w)){
		if(!visited[w])
			DFS(G,w);
	}
}
//DFS的深度优先遍历的非递归算法
void DFS_non_RS(AGraph& G,int v){
	int w;
	InitStack(S);
	for(int i=0;i<G.vexnum;++i)
		visited[i] = false;
	Push(S,v);
	visited[v] = true;
	while(!IsEmpty(S)){
		k = Pop(S);
		visit(k);
		for(w=FisitNeighbor(G,k);w>=0;w=NextNeighbor(G,k,w)){
			if(!visited[w]){
				Push(S,w);
				visited[w] = true;
			}
		}
	}
}
//计算单源最短路径（BFS算法)
void BFS_MIN_Distance(Graph G,int u){
	for(int i=0;i<G.vexnum;i++){
		d[i] = NuLL;
		path[i] = -1;
	}
	d[u] = 0;
	visited[u] = true;
	EnQueue(Q,u);
	while(!IsEmpty(Q)){
		DeQueue(Q,u);
		for(int w=FirstNeighbor(G,u);w>=0;w=NextNeighbor(G,u,w))
			if(!visited[w]){
			d[w] = d[u]+1;
			path[w] = u;
			visited[w] = true;
			DeQueue(Q,w);
			}
	}
}
//弗洛伊德算法
void Floyd(Graph G){
for(int k=0;k<n;k++){
	for(int i=0;i<n;i++){
		for(int j=0;j<n;j++){
			if(A[i][j] > A[i][k] + A[k][j]){
				A[i][j] = A[i][k] + A[k][j];
				path[i][j] = k;
			}
		}
	}
}
}
#define MaxVertexNum 100
typedef struct ArcNode{
	int adjvex;
	struct ArcNode* nextarc;
}ArcNode;

typedef struct VNode{
	VextexType data;
	ArcNode* firstarc;
}VNode,AdjList[MaxVertexNum];

typedef struct{
	AdjList vertices;
	int vexnum,arcnum;
}Graph;
//顺序查找
typedef struct{
	ElemType *elem;
	int Tablelen;
}SSTable;

int Search_Seq(SSTable ST,ElemType key){
	int i;
	for(i=0;i<ST.Tablelen && ST.elem[i] != key;i++)
		return i == ST.Tablelen ? -1: i;
}
//哨兵
int Search_Seq(SSTable ST,ElemType key){
	ST.elem[0] = key;
	int i;
	for(i = ST.Tablelen;ST.elem[i] != key;--i)
		return i;
}

//折半查找
int Binary_Search(SSTable L,ElemType key){
	int low = 0;
	int high = L.Tablelen-1;
	int mid;
	while(low<=high){
		int mid = (low+high)/2;
		if(L.elem[mid] == key)
			return mid;
		else if(L.elem[mid] > key)
			high = mid - 1;
		else
			low = mid + 1;
	}
	return -1;
}
//分块查找
typedef struct{
	ElemType MaxValue;
	int low,high;
}Index;

ElemType List[100];
