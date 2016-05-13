# BaserCMSValetDriver
Mac用の簡易PHP開発環境をセットアップするツールLaravel ValetのbaserCMS用カスタムドライバです。

## 使い方
詳細は[Valetのドキュメント](https://laravel.com/docs/5.2/valet#installation)参照

### 環境変数PATHを追加
~/.bash_profileや~/.bashrcに記述しておく

    export PATH=$HOME/.composer/vendor/bin:$PATH


### Valetに必要なツールをインストール
* Git
* Homebrew
* PHP5.6
* Composer


Homebrewをインストール

    /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

HomebrewでPHP5.6をインストール

    brew install homebrew/php/php56

Composerをグローバルインストール

    php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
    php -r "if (hash_file('SHA384', 'composer-setup.php') === '92102166af5abdb03f49ce52a40591073a7b859a86e8ff13338cf7db58a19f7844fbc0bb79b2773bf30791e935dbd938') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
    php composer-setup.php
    php -r "unlink('composer-setup.php');"
    mv composer.phar /usr/local/bin/composer

### Valetのインストール

ComposerでValetをグローバルで追加

    composer global require laravel/valet

Valetをインストール（ValetとDnsmasqを設定してValetのデーモンをシステムに登録）

    valet install

### Valetに親ディレクトリを登録

適当にディレクトリを作る

    cd ~/
    mkdir valet-sites

Valetにパスを登録

    cd valet-site/
    valet park

~/valet-site のサブディレクトリがそれぞれ {ディレクトリ名}.devというドメインでアクセスできるようになる。

### カスタムドライバ追加
このディレクトリのBaserCMSValetDriver.phpを~/.valet/Drivers/BaserCMSValetDriver.phpに配置

### baserCMSをクローン
    git clone https://github.com/baserproject/basercms
    cd basercms

### http://basercms.devにアクセス


## License
MIT License.
