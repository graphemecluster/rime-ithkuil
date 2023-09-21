日本語 ｜ [English](./README.md)

# イスクイルのための入力方式（IME）

一般的なキーボードでイスクイル III（Ithkuil）と IV（The New Ithkuil Language）を入力できる [RIME](https://rime.im) という入力エンジンのスキーマです。

キーシーケンスはなるべく直観的に入力できるようにデザインされています。例えば、<kbd>c</kbd><kbd>^</kbd><kbd>h</kbd> では ⟨čʰ⟩ を、<kbd>~</kbd> では下降上昇調の文字 ⟨ˇ⟩ を入力できます。詳細については[このマニュアル](https://laethiel.fr/ithkuil/manual.php)をご参照ください。

> [!NOTE]
> **注意**
> - イスクイル III で /d͡z/ を表す ⟨ż⟩ は <kbd>z</kbd><kbd>.</kbd> に割り当てられたため、イスクイル IV で使われる **⟨ẓ⟩ は <kbd>z</kbd><kbd>,</kbd> で入力してください**。
> - <kbd>-</kbd> を押すと高平板調の文字の ⟨ˉ⟩ が入力されます。音節を分けるための**ハイフンを入力するには <kbd>=</kbd> を押します**。入力されるのは non-breaking hyphen と呼ばれる文字であり、ここでの改行は禁止されています。すなわち、単語が行末にあってもここで折り返されることはありません。
> - 元の文字を入力するには同じキーを２回押します。また、最後のキーを３回押すと変換された文字と元の文字の両方が順に入力されます。

## インストール

まず、[ダウンロードページ](https://rime.im/download/)から RIME をインストールしてください。お使いのプラットフォームの下にある`〔下載〕`ボタンをクリックします。

インストールが完了したら、プラットフォームに合わせて以下の手順に従ってください。これにより、自動的にセットアップツールがダウンロードされ、スキーマファイルが変更されます。

> [!IMPORTANT]
> **重要**
>
> 以下のコマンドは候補選択メニューを非表示にする効果があります。既に RIME を使用している場合、実行は**自己判断**でお願いします。

### Windows

PowerShell で次のコマンドを実行してください：

```powershell
$bash = "$env:ProgramFiles\Git\bin\bash.exe"
if (!(Test-Path $bash)) {
  winget install --id Git.Git -e -s winget
}
Start-Process $bash -ArgumentList "-c 'curl -fsSL https://git.io/rime-install | bash -s -- graphemecluster/rime-ithkuil custom:clear_schema_list custom:add:schema=ithkuil custom:set:config=weasel,key=style/inline_preedit,value=true custom:set:config=weasel,key=style/preedit_type,value=preview custom:set:config=weasel,key=style/layout/margin_x,value=-1 custom:set:config=weasel,key=style/layout/margin_y,value=-1'"
```

最後に、<kbd>Windows</kbd> + <kbd>スペース</kbd> で入力方式を`小狼毫`に切り替え、`中`と書かれたアイコンを右クリックし、`重新部署 (R)` または `Redeploy` をクリックしてください。これにより、スキーマファイルへの変更は入力システムに適用されます。

### Mac

ターミナルで次のコマンドを実行してください：

```bash
curl -fsSL https://git.io/rime-install | bash -s -- graphemecluster/rime-ithkuil custom:clear_schema_list custom:add:schema=ithkuil custom:set:config=squirrel,key=style/inline_candidate,value=true custom:set:config=squirrel,key=style/alpha,value=0.00001
```

最後に、<kbd>Control</kbd> + <kbd>スペース</kbd> で入力方式を`鼠鬚管`に切り替え、入力ソースのコンテキストメニューを開き、`重新部署` または `Redeploy` をクリックしてください。これにより、スキーマファイルへの変更は入力システムに適用されます。
