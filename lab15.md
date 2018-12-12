以电脑代替人工，我们可以用以下代码实现 
int myMin(int array[4]) { 
int i; 
int Min = array[0]; 
for (i = 1; i < 4; i++) { 
if (array[i] < Min) Min = array[i]; 
} 
for (i = 0; i < 4; i++) { 
if (array[i] == Min) break; 
} 
return i; 
}

char whereToGo(int Hx, int Hy, int Fx, int Fy) { 
char direction[4] = { ‘W’, ‘A’, ‘S’, ‘D’ }; 
int distance[4] = { 0, 0, 0, 0 }; 
int result[4][2] = { { Hx, Hy - 1 },{ Hx - 1, Hy },{ Hx, Hy + 1 },{ Hx + 1, Hy } }; 
int i; 
for (i = 0; i < 4; i++) { 
if (map[result[i][1]][result[i][0]] != ‘*’ && map[result[i][1]][result[i][0]] != ‘X’) { 
distance[i] = abs(result[i][0] - Fx) + abs(result[i][1] - Fy); 
} 
else distance[i] = 9999; 
} 
int index_Min = myMin(distance); 
return direction[index_Min]; 
}   
