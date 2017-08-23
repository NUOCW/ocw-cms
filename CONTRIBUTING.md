Contributing Guidelines
=======================


Table of Contents
-----------------

1. [Outline](#outline)
1. [環境整備](#環境整備)
  * [Bootstrap](#bootstrap)
  * [ローカル設定ファイル](#ローカル設定ファイル)
1. [コーディング規約](#コーディング規約)


Outline
-------

1. このリポジトリを**[フォーク][Fork]**して自分のから手元に**クローン**する.
2. どのブランチをベースにコミットするか決めてトピックブランチを作成する: `git checkout -b <topic branch> <base branch>`
    * バグ修正: `master`, `release-*` or `staging`.
    * 新機能: `development`
3. プロジェクトのbootstrap処理を行う: `composer install`
4. コードと必要なテストを追加し, 既存のテストを壊さないことを確認する.
5. フォークしたリポジトリにプッシュし, 分岐元のブランチに対して[マージリクエスト][merge-request]を発行する.
6. コードがレビューされるのを待つ.


簡単なガイドは以上で, 以下では詳細について記述します.


環境整備
--------

ocw-cmsは以下の環境を想定して開発を行っています.

* PHP `^7.1.0`
* Symfony `^3.0.0`
* MariaDB `^10.1.0`


### Bootstrap

リポジトリのクローン, ブランチの切り替えなどの後に[Composer]を用いてパッケージのインストールを行ってください.
```
$ composer install
```


### ローカル設定ファイル

ocw-cmsではSymfonyフレームワークを利用しており, データベースのパラメータなどローカルの設定は[app/config/parameters.yml](app/config/parameters.yml)に記述します.


コーディング規約
----------------

PHPコードの規約は[Symfony 3][Symfony Coding Standards]のコーディング規約に準拠するよう記述してください.
スペックの規約は例外として[phpSpecの規約][phpSpec PHPCS]に従うようにしてください.

| File | Standard  |
| ---- | --------- |
| `src/**/*.php`  | [Symfony 3][Symfony Coding Standards] |
| `spec/**/*.php` | [phpSpec][phpSpec PHPCS] |


[fork]:https://gitlab.ocw.media.nagoya-u.ac.jp/NUOCW/ocw-cms/forks/new
[merge-request]:https://gitlab.ocw.media.nagoya-u.ac.jp/NUOCW/ocw-cms/merge_requests/new
[composer]:https://getcomposer.org/
[phpSpec PHPCS]:https://github.com/kmcculloch/phpspec-code-sniffer
[Symfony Coding Standards]:http://symfony.com/doc/current/contributing/code/standards.html