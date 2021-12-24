---
title: '[BOJ] 15591 MooTube(Silver)'
categories:
  - Algorithm
tags:
  - Java
  - Graph
  - BOJ

comments: true 
---
### 그래프 탐색 예제

## 문제
<a href = "https://www.acmicpc.net/problem/15591"> https://www.acmicpc.net/problem/15591 </a>
<br/>

## 문제 풀이

``` java
package Baekjoon.Graph;

import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.ArrayList;
import java.util.LinkedList;
import java.util.Queue;
import java.util.StringTokenizer;

/**
 * Created by kyeahen.
 * Title : 15591 MooTube (Silver)
 * Category : 그래프, 그래프 탐색
 * Date: 2021/06/02
 */
public class BJ_15591 {

    static class Edge {
        int v;
        int cost;

        Edge(int v, int cost) {
            this.v = v;
            this.cost = cost;
        }
    }

    static int N, Q;
    static ArrayList<Edge>[] graph;
    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));

        StringTokenizer st = new StringTokenizer(br.readLine());
        N = Integer.parseInt(st.nextToken());
        Q = Integer.parseInt(st.nextToken());

        graph = new ArrayList[N + 1];

        for (int i = 1; i <= N; i++) {
            graph[i] = new ArrayList<>();
        }

        for (int i = 0; i < N - 1; i++) {
            st = new StringTokenizer(br.readLine());
            int p = Integer.parseInt(st.nextToken());
            int q = Integer.parseInt(st.nextToken());
            int r = Integer.parseInt(st.nextToken());

            graph[p].add(new Edge(q, r));
            graph[q].add(new Edge(p, r));
        }

        StringBuilder sb = new StringBuilder();
        for (int i = 0; i < Q; i++) {
            st = new StringTokenizer(br.readLine());
            int k = Integer.parseInt(st.nextToken());
            int v = Integer.parseInt(st.nextToken());

            int count = 0;
            Queue<Integer> q = new LinkedList<>();
            boolean[] visited = new boolean[N + 1];

            visited[v] = true;
            q.offer(v);

            while (!q.isEmpty()) {
                int num = q.poll();
                ArrayList<Edge> list = graph[num];

                for (Edge edge : list) {
                    if (visited[edge.v]) { continue; }
                    if (edge.cost < k) { continue; } //K 이상인 모든 동영상 추천

                    count++;
                    q.offer(edge.v);
                    visited[edge.v] = true;
                }
            }

            sb.append(count).append("\n");
        }

        System.out.println(sb.toString());
    }
}
```

## TMI

**21/06/02: 알고리즘 스터디 문제 풀이🤓**
