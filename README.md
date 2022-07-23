ansible-official-site-server
================================

公式サイト用サーバーの構成管理

必要ロール
---------------------

* [geerlingguy.certbot](https://galaxy.ansible.com/geerlingguy/certbot)
* [histudy/ansible-role-apt-backports](https://github.com/histudy/ansible-role-apt-backports)
* [histudy/ansible-role-nginx](https://github.com/histudy/ansible-role-nginx)  
* [histudy/ansible-role-common](https://github.com/histudy/ansible-role-common)
  * Debian Bullseye で構築するため [for-bullseye](https://github.com/histudy/ansible-role-common/tree/for-bullseye) ブランチを使用すること

以下のコマンドを実行すると、依存しているロールをインストールすることができます。

```sh
ansible-galaxy install -r requirements.yml
```

### 参考URL

* [GitHub Enterpriseなど社内リポジトリにあるansible roleリポジトリをinstallして利用する](https://qiita.com/yassan168/items/0fea8bbc80c39448d7fd)
