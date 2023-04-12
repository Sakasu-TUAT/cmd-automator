# cmd-automator
pythonでc/c++, pythonの入力を自動化するよ

# How to Use 

## c/c++の場合

### c/c++側
#### 1. main関数で引数をとれるようにする

```
int main (int argc, char* argv[]){ 
```

#### 2. ファイル名の番号を引数で指定できるようにする
```
   fileName = "./6002/map" + string(argv[1]);
```
多分こんな感じ。stringとかはcの人はいい感じに変えといて。

こうすると実行時に
```
./a.out 1
```
のように`./a.out`のあとにスペース一つ開けてファイルの番号を指定すると、
そのファイルを読み込むことができるようになる。

#### 3. 出力したいデータを出力
取り敢えず、メモリを memory,　時間計算量を timeComplexity, ゴールまでの距離をdist　とした。
```
    printf("memory: ", %d, "\ttimeComplexity: ", %d, "\tdist: ", %d, memory, timeComplexity, dist[9][9]); 
```
こんな感じで出力できるようにする。

#### 4. コンパイル
`gcc test.c`みたいな感じでいつも通りコンパイルして、同じフォルダ内に`./a.out`があることを確認。

### Python側
#### 5. for i in range (0, 2):　の引数を変える
0~99にしたかったら`for i in range (0, 100):`に変更

#### 6. いよいよ実行
```
python result.py
```
で指定したフォルダが自動で読み込まれて結果が`output.py`に出力されているはず。
