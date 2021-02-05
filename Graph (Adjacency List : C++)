//by Sushant Gaurav

#include <bits/stdc++.h>
#include <iostream>
#include <vector>
#include <queue>

using namespace std;

int visited[100] = {0};
int indegree[100]={0};
vector <int> graph[100];
vector <int> result;

void createGraph(vector <int> graph[] , int i , int j)              //list STL can be used as well
{
    graph[i].push_back(j);
    indegree[i]++;
    //graph[j].push_back(i);
}

//-----------------------------------------------------------------------------------------------------------------------------------

void display(vector<int> graph[], int v)
{
    for(int i=1 ; i<=v ; i++)
    {
        cout << i << "--->";
        vector<int> :: iterator it;
        for(it = graph[i].begin(); it != graph[i].end(); ++it)
            cout << *it << " ";
        cout << endl;
   }
}

//-----------------------------------------------------------------------------------------------------------------------------------

void DFS_iterative(int s)
{
    stack <int> stk;
    stk.push(s);
    visited[s] = 1;

    while(!stk.empty())
    {
        int node = stk.top();
        stk.pop();
        cout<<node<<"  ";

        //important -> checking first vector then second so on..
        for(int i=1 ; i<graph[node].size() ; i++)
        {
            if(!visited[ graph[node][i] ])
            {
                stk.push(graph[node][i]);
                visited[ graph[node][i] ] = 1;
            }
        }
    }
}

//-----------------------------------------------------------------------------------------------------------------------------------

void BFS(int s , int V)
{
    queue <int> q;
    cout<<s<<"   ";
    visited[s] = 1;
    q.push(s);
    while( !q.empty() )
    {
        int node = q.front();
        q.pop();
        for(int i=1 ; i<graph[node].size() ; i++)
        {
            if( !visited[ graph[node][i] ] )
            {
                cout<<graph[node][i]<<"  ";
                visited[ graph[node][i]  ] = 1;
                q.push( graph[node][i] );
            }
        }
    }
}

int main()
{
    int choice,V,e,i;
    cout<<"\nEnter the number of vertex : ";
    cin>>V;

    while(1)
    {
        cout<<"\n1. Create Graph"<<endl;
        cout<<"2. To view List-matrix"<<endl;
        cout<<"3. DFS Traversal"<<endl;
        cout<<"4. BFS Traversal"<<endl;
        cout<<"5. EXIT"<<endl;
        cout<<"Enter your choice"<<endl;
        cin>>choice;
        switch(choice)
        {
        case 1:
            {
                for(i=1 ; i<=V ; i++)
                {
                    while(1)
                    {
                        cout<<"Enter the edges from '"<<i<<"' or press -1 : ";
                        cin>>e;
                        if(e == -1)
                            break;
                        createGraph(graph , i , e);
                    }
                }
            break;
            }

        case 2:
            {
                display(graph , V);
                break;
            }

        case 3:
            {
                cout<<"Graph Traversal is : ";
                DFS_iterative(1);
                visited[100] = {0};
                break;
            }

        case 4:
            {
                cout<<"Graph Traversal is : ";
                BFS(1 , V);
                visited[100] = {0};
                break;
            }

        case 5:
        {
            exit(0);
            break;
        }

        default:
            cout<<"\nINVALID CHOICE..."<<endl;
        }
    }
    return 0;
}

