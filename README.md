# Input Method for Ithkuil and The New Ithkuil Language

This is a simplistic [RIME](https://rime.im) schema that inputs characters used in Ithkuil (III) and The New Ithkuil Language (IV) with ASCII keys.

The input keys are mostly intuitive, e.g. typing <kbd>c</kbd><kbd>^</kbd><kbd>h</kbd> yields ⟨čʰ⟩ while <kbd>~</kbd> produces the character for falling-rising tone, ⟨ˇ⟩. For details, refer to [this manual](https://laethiel.fr/ithkuil/manual.php).

> [!NOTE]
> - Since Ithkuil use ⟨ż⟩ for /d͡z/, which is inputted by <kbd>z</kbd><kbd>.</kbd>, **type <kbd>z</kbd><kbd>,</kbd> to produce ⟨ẓ⟩** in The New Ithkuil Language.
> - Typing <kbd>-</kbd> yields the character for high tone, ⟨ˉ⟩. To produce **a hyphen** specified for syllabification, **type <kbd>=</kbd>**. The result character is a non-breaking hyphen, which means a word won’t wrap at it even if the word falls at the end of a line.
> - To produce the original character, input the character twice. Tripling the last character of the input results in a transformed character plus the original character.

## Installation

First, install RIME from [the download page of RIME](https://rime.im/download/). Click on the `〔下載〕` button that matches your platform.

After completing the installation, follow the instruction corresponding to your platform below. This automatically downloads the setup tool and modifies the schema files for you.

> [!IMPORTANT]
> The following commands prevent the candidate selection menu from appearing. If you’re already using RIME, you may **not** want to execute them.

### Windows

Execute the following command in your PowerShell:

```powershell
$bash = "$env:ProgramFiles\Git\bin\bash.exe"
if (!(Test-Path $bash)) {
  winget install --id Git.Git -e -s winget
}
Start-Process $bash -ArgumentList "-c 'curl -fsSL https://git.io/rime-install | bash -s -- graphemecluster/rime-ithkuil custom:clear_schema_list custom:add:schema=ithkuil custom:set:config=weasel,key=style/inline_preedit,value=true custom:set:config=weasel,key=style/preedit_type,value=preview custom:set:config=weasel,key=style/layout/margin_x,value=-1 custom:set:config=weasel,key=style/layout/margin_y,value=-1'"
```

Finally, switch the input method to `小狼毫` with <kbd>Windows</kbd> + <kbd>Space</kbd>, right-click the `中` icon, then click `重新部署 (R)` (Redeploy), which applies the changes to the schema files to the IME.

### Mac

Execute the following command in your Terminal:

```bash
curl -fsSL https://git.io/rime-install | bash -s -- graphemecluster/rime-ithkuil custom:clear_schema_list custom:add:schema=ithkuil custom:set:config=squirrel,key=style/inline_candidate,value=true custom:set:config=squirrel,key=style/alpha,value=0.00001
```

Finally, switch the input method to `鼠鬚管` with the <kbd>🌐</kbd> key, open the input method context menu, then click `重新部署` (Redeploy), which applies the changes to the schema files to the IME.
