5問CTF (Linux/PowerShell) 
==============================================
使用可能なコマンド(オプションは全て使用可): 
cat, cd, pwd, ls, find, ls, tree, touch/type nul>, sort

最終目標：各フォルダに隠れたフラグ (例 ctf{...}) を, 集める.

[stage1] はじめの一歩
フラグは flag1.txt の中にあります.
*ヒント*
lsはファイル, フォルダの一覧を出力し, catはファイルの中身を出力します.

[stage2] 隠しフォルダ
フラグは flag2.txt の中にあります.
*ヒント*
lsにはオプションがあります. 
ls -l は詳細を出力します.
ls -a は隠しフォルダも含めて出力します.
また, ls -la のように, オプションは同時に指定できます.

[stage3] 干し草の中の針を探す
フラグは flag3.txt の中にあります.
*ヒント*
findコマンドを使って, ファイルを探してください.
find . -name {ファイル名} のようにファイル名を指定できます.

[stage4] 深く深く
フラグを探してください.
*ヒント*
使うコマンドはtree, ls, cd, catです.

[stage5] 免許皆伝
散らばったフラグをかき集めてください. それぞれ "part_"から始まり, .txtで終わります.
find . -name {ファイル名}
cat $(find) で findコマンドを入力した結果を出力します.
cat | sort のように"|"で繋ぐことで, catの出力をsortすることができます.



[[トラブルシューティング]]

Q. オプションとは?
A. -（Windowsの tree は /）から始まる指定。例：ls -Force、tree /F

Q. コマンドとオプションの説明は?
A.

Linux: man ls / ls --help

PowerShell: Get-Help ls / ls -? / command --help

Q. Windowsで find . -name ... が動かない
A. find は テキスト検索用（find.exe）のため。代わりに
ls -Recurse -Filter 'file' または
ls -Recurse | Where-Object Name -like 'pattern'

Q. ls -la がPowerShellで通らない
A. PSは短縮オプション連結が不可。ls -Force（隠し表示）, ls -Recurse（再帰）など明示で。
 
