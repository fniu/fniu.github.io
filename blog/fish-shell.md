# Fish Shell

I have found the fish shell very interesting, especially its inline autosuggestion feature.

## Use fish on Linux

It is very easy to install and use fish on Linux. One configuration one might be wanting to do is to change the color of the autosuggestion. To do that, simply add the following in config file `~/.config/fish/config.fish`:

```shell
if status is-interactive
    set -g fish_color_autosuggestion 009900
end
```



## Use fish-like stuff on Powershell

To get the similar experience `fish` provides, one can use the `PSReadLine` module, see its github [link]([PowerShell/PSReadLine: A bash inspired readline implementation for PowerShell (github.com)](https://github.com/PowerShell/PSReadLine)). I also like to enable the Emacs key bindings in `PSReadLine`. To import this module and also set up the desired configuration, one can edit its profile file, which typically located in `C:\Users\<username>\Documents\PowerShell\Microsoft.PowerShell_profile.ps1`. I myself add the following lines in the profile file:

```powershell
Import-Module PSReadLine

$PSReadLineOptions = @{
    EditMode = "Emacs"
    HistorySearchCursorMovesToEnd = $True
    PredictionSource = "HistoryAndPlugin"
    Colors = @{
        "InlinePrediction" = "#009900"
    }
}
Set-PSReadLineOption @PSReadLineOptions
```

