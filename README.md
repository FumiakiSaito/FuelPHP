# FuelPHP

## 環境構築

### fuelphpダウンロード
```
git clone --recursive git://github.com/fuel/fuel.git fuelphp
```

### パッケージアップデート

composer.phar自体を更新
```
php composer.phar self-update
```

パッケージを更新
```
php composer.phar update
```

※tokenを聞かれる場合はGitHubのAPI制限にひっかかっている  
メッセージに記載されているURLにブラウザでアクセスすることでtokenを作成することができる。


### 設定ファイル更新

bootstrap.php
```
 <?php
+// set default charset
+ini_set('default_charset', 'UTF-8');
+
```

config.php
```

         * Localization & internationalization settings
         */
        // 'language'           => 'en', // Default language
+       'language'           => 'ja', // Default language
        // 'language_fallback'  => 'en', // Fallback language when file isn't available for default language
        // 'locale'             => 'en_US', // PHP set_locale() setting, null to not set
+       'locale'             => null,

        /**
         * Internal string encoding charset
@@ -94,6 +96,8 @@ return array(
         */
        // 'server_gmt_offset'  => 0,
        // 'default_timezone'   => null,
+       'default_timezone' => 'Asia/Tokyo',
+

        /**
         * Logging Threshold.  Can be set to any of the following:
@@ -106,6 +110,7 @@ return array(
         * Fuel::L_ALL
         */
        // 'log_threshold'    => Fuel::L_WARNING,
+       'log_threshold'    => Fuel::L_ALL,
        // 'log_path'         => APPPATH.'logs/',
        // 'log_date_format'  => 'Y-m-d H:i:s',

@@ -121,6 +126,7 @@ return array(
                 * A salt to make sure the generated security tokens are not predictable
                 */
                // 'token_salt'            => 'put your salt value here to make the token more secure',
+               'token_salt'            => 'fuelphpnotesutodesu',

                /**
                 * Allow the Input class to use X headers when present
```
