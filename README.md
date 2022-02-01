## 概要
dcm4cheコアライブラリの文字化け修正版です。  

## セットアップ済み dcm4chee-arc-light への文字化け対策版の導入

- 導入しているバージョンに合わせて、文字化け対策版の`dcm4che-core-*_modmojibake.jar`(以降`対策版jar`)をダウンロード  

- `wildfly-*/modules/org/dcm4che/core/main/`フォルダに`対策版jar`ファイルを置く  
※動かなかったときのために元々の jar ファイルは残しておいた方がいいです  

- `wildfly-*/modules/org/dcm4che/core/main/module.xml` をエディタで開き `<resource-root path="dcm4che-core-*.jar"/>` と書いてある部分を、新しく置いたファイルを示すように変更する  
例: `<resource-root path="dcm4che-core-5.24.1.jar"/>` → `<resource-root path="dcm4che-core-5.24.1_modmojibake.jar"/>`

- wildfly を停止して再び起動

- 以降、新しく受信したdicomでは文字化けしないはず

5.18.0 と 5.25.1 でしか動作テストしてません。

5.12.0よりも前のバージョンはビルドエラーを直すのが手間で用意してません。

[詳しくはこちら](https://itr-tert.github.io/note/2022-01--dcm4che.html)

## Source Code
https://github.com/itr-tert/dcm4che  
上流: https://github.com/dcm4che/dcm4che


## LICENSE
MPL 1.1/GPL 2.0/LGPL 2.1

* MPL 1.1  
https://github.com/dcm4che/dcm4che/blob/master/LICENSE.txt  
http://www.mozilla.org/MPL/1.1/  

* GPL 2.0  
https://www.gnu.org/licenses/old-licenses/gpl-2.0.en.html

* LGPL 2.1  
https://www.gnu.org/licenses/old-licenses/lgpl-2.1.en.html