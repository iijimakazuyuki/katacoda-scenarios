Argo CDはUIから設定することもできますが、このコースでは宣言的な方法を取ります。

Argo CDを設定する前に、GitHubに自身のGitリポジトリを作成します。
もしGitHubアカウントを持っていなければ、GitHubのドキュメント [Getting started with your GitHub account Part 1: Configuring your GitHub account](https://docs.github.com/en/get-started/onboarding/getting-started-with-your-github-account#part-1-configuring-your-github-account) に従ってください。

サンプルリポジトリ `https://github.com/iijimakazuyuki/katacoda-argocd-sample` をフォークするか、サンプルリポジトリを参考にリポジトリを、次の次項に注意して作成します：

- `podinfo-application.yaml` ファイルのみが必要です。
- `README.md` と `LICENSE` は不要なファイルです。
- Argo CDは認証情報を用いてプライベートリポジトリにアクセスできますが、簡単のためにリポジトリをパブリックに設定します。

次は、Gitリポジトリとの自動同期を設定し、サンプルアプリケーションをデプロイします。
