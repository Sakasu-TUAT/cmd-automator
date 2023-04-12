# cmd-automator
pythonでc/c++, pythonの入力と結果の出力を自動化するよ

# How to Use 
### 0. 環境の準備
・幅優先探索や深さ優先探索のプログラムを作成

・githubのアカウントを作成してこのリポジトリをクローン 

or 

view code内の`result.py`だけコピペ


## c/c++側
自分で作成した幅優先探索や深さ優先探索のプログラムに変更を加える

### 1. main関数で引数をとれるようにする
```
int main (int argc, char* argv[]){ 
```
### 2. ファイル名の番号を引数で指定できるようにする
  
```
    FILE *fp; // FILE型構造体
	char fileName[] = "./6002/map";
    strcat(fileName, argv[1]);
```
多分こんな感じ。fopenの前にこれで名前を変えておく。

こうすると実行時に
```
./a.out 1
```
のように`./a.out`のあとにスペース一つ開けてファイルの番号を指定すると、
そのファイルを読み込むことができるようになる。


### 3. 出力したいデータを出力
取り敢えず、メモリを memory,　時間計算量を timeComplexity, ゴールまでの距離をdist　とした。
```
    printf("memory: ", %d, "\ttimeComplexity: ", %d, "\tdist: ", %d, memory, timeComplexity, dist[9][9]); 
```
こんな感じで出力できるようにする。
出力したいデータは適宜変更してください。

### 4. コンパイル
`gcc test.c`みたいな感じでいつも通りコンパイルして、同じフォルダ内に`./a.out`があることを確認。

## Python側
`result.py`を変更する
### 5. 読み込みたいファイルを指定
0~99のファイルを読み込みたかったら`for i in range (0, 100):`に変更

### 6. いよいよ実行
```
python result.py
```
で指定したフォルダが自動で読み込まれて結果が`output.py`に出力されているはず。

