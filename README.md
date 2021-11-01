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
      
# Git快適プロンプト(プロンプトHack)にする...zshバージョン
使用中のシェルを確認する <br>
  $ echo $SHELL <br>
  /bin/zsh or /bin/bash など <br>
指定のシェルを使用する <br>
  $ chsh -s <shell> <br>
  例 chsh -s /bin/zsh <br>

1. ~/.zshrc のバックアップをとる(あれば) <br>
  $ cp ~/.zshrc ~/.zshrc_yyyymmdd <br>
2. Oh My Zsh をインストールする(https://ohmyz.sh/) <br>
  アンインストール: $ rm -rf ~/.oh-my-zsh <br>
3. Powerlevel10kをcloneする <br>
  $ git clone https://github.com/romkatv/powerlevel10k.git ~/.oh-my-zsh/custom/themes/ <br>
4. ~/.zshrc に ZSH_THEME="powerlevel10k/powerlevel10k" を追加する <br>

  





  
