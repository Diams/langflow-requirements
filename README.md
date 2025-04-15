# langflow-requirements

Langflow の依存関係が壊れすぎていて怒りのあまり作った。

## なにこれ？

Langflow をバカ正直に

```
pip install langflow
```

しようとすると、色々な不運に見舞われるので、そんな不幸な人をできる限り救うためのリポジトリ

## 実施環境

|        |            |
| ------ | ---------- |
| OS     | Windows 11 |
| Python | 3.12.3     |
| pip    | 25.0.1     |

## 作り方

1. `pip install langflow==<入れたいバージョン>`する
2. そもそも pip が正常完了しなかったり、`langflow run`とかでエラーが出る
3. ブチキレる
4. 一旦頭を冷やすためにお～いお茶を飲む
5. DockerHub から Langflow の特定のバージョンのコンテナイメージを`pull`する
6. `pull`したコンテナを`docker run`して立ち上げる
7. `docker exec`でコンテナに入る
8. `ls .env/bin/lib/python3.12/site-packages`で中身を見て地道にどのバージョンの何がインストールされているのかを確認する
9. ↑ の情報を基に`requirements.txt`を作る
10. `pip install -r requirements.txt`する
11. `langflow run`を叩いてみる
12. 上手くいったら歓喜の舞を躍りながら`pip freeze > requirements.txt`する
