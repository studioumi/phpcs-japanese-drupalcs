# PHP Coder Sniffer for Japanese Drupal project

[PHP Coder Sniffer](https://github.com/squizlabs/PHP_CodeSniffer) を Drupal の [Coder プロジェクト](https://www.drupal.org/project/coder)のルールセットを使用した際、ソースコードのコメントなどに日本語を使用した時に発生する警告を緩和するルールセットです。

## 使い方

Composer を使った一般的なグローバルインストールの方法を以下に解説します。

本パッケージを Composer を使ってインストールします。PHP Code Sniffer や Drupal Coder モジュールも依存関係にあるため自動的にインストールされます。

    $ composer global require studioumi/phpcs-japanese-drupal

初めて Composer でグローバルインストールした場合は `~/.composer/vendor/bin` ディレクトリにパスを通してください。

PHP Code Sniffer に Coder とこのプロジェクトのルールセットのインストールパスを設定します。

    $ phpcs --config-set installed_paths $HOME/.composer/vendor/drupal/coder/coder_sniffer,$HOME/.composer/vendor/studioumi/phpcs-japanese-drupal

インストールされているスタンダードの一覧を確認します。`Drupal` と `JapaneseDrupal` の名前があれば正常です。

    $ phpcs -i
    The installed coding standards are MySource, PEAR, PHPCS, PSR1, PSR2, Squiz, Zend, Drupal, DrupalPractice and JapaneseDrupal

以上で JapaneseDrupal のスタンダードが使用可能になります。以下は基本的な使い方の例です。

    $ phpcs --standard=JapaneseDrupal /PATH

デフォルトのルールセットを JapaneseDrupal に設定することで `--standard=JapaneseDrupal` のオプションを省略することができるようになります。好みに応じて設定してください。

    $ phpcs --config-set default_standard JapaneseDrupal

