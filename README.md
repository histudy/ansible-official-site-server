ansible-official-site-server
================================

公式サイト用サーバーの構成管理

前提条件
---------------------

本リポジトリの内容を理容するにはAnsibleが必要です。  
以下のインストールガイドを参照し、Ansibleのインストールを行ってください。

[Installation Guide](https://docs.ansible.com/ansible/latest/installation_guide/index.html)

必要なロール
---------------------

* [wate/ansible-role-common](https://github.com/wate/ansible-role-common)
* [geerlingguy.certbot](https://galaxy.ansible.com/geerlingguy/certbot)
* [wate/ansible-role-nginx](https://github.com/wate/ansible-role-nginx)  

### ロールのインストール

以下のコマンドを実行すると、サーバーの構築に必要なロールをインストールできます。

```sh
ansible-galaxy install -r requirements.yml -p roles
```

### ロールの更新

以下のコマンドを実行すると、ロールを最新の状態に更新できます。

```sh
ansible-galaxy install -r requirements.yml -p roles --force
```

実行方法
---------------------

以下のコマンドを実行し、定義内容に合わせサーバーの構築が行われます。

```sh
ansible-playbook playbook.yml
```

参考URL
---------------------

* [GitHub Enterpriseなど社内リポジトリにあるansible roleリポジトリをinstallして利用する](https://qiita.com/yassan168/items/0fea8bbc80c39448d7fd)

Tips
---------------------

[ansible-cmdb](https://ansible-cmdb.readthedocs.io/en/latest/)を利用すると変数の定義内容やホストの情報をHTMLで出力することができます。

変数の定義内容やサーバーの情報を出力するには、以下のコマンドを実行します。

```sh
mkdir out
ansible -m setup --tree out/ all
ansible-cmdb -i hosts.ini out/ >overview.html
rm -fr out
```
