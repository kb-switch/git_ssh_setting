# my-second-repo
Git練習用

# SSHアクセス設定方法(2021/08/13以降->ローカルからGitHubへのアクセス方法)
1.SSHキーをローカルに作成 <br>
$ ssh-keygen -t ed25519 -C "<email>"
  SSHキーが ~/.ssh/id_ed25519と、SSHキーが ~/.ssh/id_ed25519.pubに作成される
$ eval "$(ssh-agent -s)"
  ssh-agentを起動させる
$ subl ~/.ssh/config
  ~/.ssh/config ファイルを編集する
  <ファイルの中身>
    Host *
      AddKeysToAgent yes
      UseKeyChain yes
      IdentityFile ~/.ssh/id_ed25519
$ ssh-add -K ~/.ssh/id_ed25519
    SSHキーをssh-agentに登録する

2.SSHキーをGitHubに登録
$ pbcopy < ~/.ssh/id_ed25519.pub
  公開鍵をクリップボードにコピー
GitHub上で、Settings -> SSH and GPG keys -> New SSH key -> 公開鍵をペースト
      
