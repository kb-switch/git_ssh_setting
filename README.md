# my-second-repo
Git練習用

# SSHアクセス設定方法(2021/08/13以降->ローカルからGitHubへのアクセス方法)
1.SSHキーをローカルに作成 <br>
$ ssh-keygen -t ed25519 -C "<email>" <br>
  SSHキーが ~/.ssh/id_ed25519と、SSHキーが ~/.ssh/id_ed25519.pubに作成される <br>
$ eval "$(ssh-agent -s)" <br>
  ssh-agentを起動させる <br>
$ subl ~/.ssh/config <br>
  ~/.ssh/config ファイルを編集する <br>
  <ファイルの中身> <br>
    Host *
      AddKeysToAgent yes
      UseKeyChain yes
      IdentityFile ~/.ssh/id_ed25519 <br>
$ ssh-add -K ~/.ssh/id_ed25519 <br>
    SSHキーをssh-agentに登録する <br>

2.SSHキーをGitHubに登録 <br>
$ pbcopy < ~/.ssh/id_ed25519.pub <br>
  公開鍵をクリップボードにコピー <br>
<b>GitHub上で、Settings -> SSH and GPG keys -> New SSH key -> 公開鍵をペースト<b> <br>
      
