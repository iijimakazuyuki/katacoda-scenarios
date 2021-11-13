Kubernetesと同期されているGitリポジトリを開いて、`podinfo-application.yaml` を編集します。
GitHubのWeb UIから編集することができます。

PodinfoはHelmチャートを用いてデプロイされています。
Helmチャートの設定は、`spec.source.helm.values` に記述されています。

`ui.color` と `ui.message` を編集し、Gitリポジトリにプッシュします.
Argo CD が変更を検知し、Kubernetesと同期を取ります。
`Refresh` をクリックすることで、手動で変更を検知させることもできます。

同期が完了するまで待ちます。
同期のステータスはArgo CDのダッシュボードで見られます。

podinfoのWeb UIにアクセスするため、次のコマンドを実行してポートを転送します：

`kubectl port-forward svc/podinfo 9898:9898 --address 0.0.0.0 &> /dev/null`{{execute}}

`Podinfo` タブを開いて、Web UIが変わったことを確認します。

すばらしい！
今や最新の設定と履歴がリポジトリで見ることができ、Gitから簡単に更新することができます。
プルリクエストを使ってアプリケーションをデプロイすることもできます。
