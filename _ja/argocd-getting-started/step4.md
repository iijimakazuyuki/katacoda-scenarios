Argo CDは `Application` リソースを記述することで、宣言的に設定できます。

次の設定ファイルを開きます：

`manifest-application.yaml`{{open}}

このファイルには、GitリポジトリのURLを含む次の行があります：

```
    repoURL: https://github.com/<名前>/<リポジトリ名>.git
```

`<名前>` をGitHubアカウントに、`<リポジトリ名>` を自身のリポジトリ名にそれぞれ書き換えます。

続いて、次のコマンドを実行して、Kubernetesにこのファイルを適用します：

`kubectl apply -f manifest-application.yaml`{{execute}}

Argo CDのダッシュボードに、`manifest` と `podinfo` というアプリケーションが表示されます。
PodinfoはオープンソースのWebアプリケーションです。 cf. `https://github.com/stefanprodan/podinfo`

ダッシュボードで `podinfo` が `Synced` かつ `Healthy` になるまで待ちます。
これは、podinfoのデプロイに成功したことになります。

podinfoのWeb UIにアクセスするため、次のコマンドを実行してポートを転送します：

`kubectl port-forward svc/podinfo 9898:9898 --address 0.0.0.0 &> /dev/null`{{execute}}

`Podinfo` タブを開くと、そのWeb UIが見られます。

<kbd>Ctrl</kbd>+<kbd>C</kbd> もしくは次のコマンドを実行して、ポート転送を停止します：

`^C`{{execute ctrl-seq}}

おめでとうございます！
KubernetesにArgo CDを用いてpodinfoをデプロイしました。
今では、設定はGitリポジトリにあり、Kubernetesはそこと同期されています。
次は、リポジトリに変更をプッシュして、新しいバージョンをデプロイします。
