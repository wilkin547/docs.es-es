---
title: Habilitación de la finalización con tabulación
description: En este artículo se describe cómo habilitar la finalización con tabulación para la CLI de .NET en PowerShell, Bash, zsh y fish.
author: adegeo
ms.author: adegeo
ms.topic: how-to
ms.date: 11/03/2019
ms.openlocfilehash: b5b63166faa1762d9fa82a93aa70aebb33167630
ms.sourcegitcommit: 65af0f0ad316858882845391d60ef7e303b756e8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "99585564"
---
# <a name="how-to-enable-tab-completion-for-the-net-cli"></a>Procedimiento para habilitar la finalización con tabulación para la CLI de .NET

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores

En este artículo se describe cómo configurar la finalización con tabulación para cuatro shells: PowerShell, Bash, zsh y fish. En el caso de otros shells, consulte la documentación para saber cómo configurar la finalización con tabulación.

Una vez que se ha configurado, para desencadenar la finalización con tabulación para la CLI de .NET, escriba un comando `dotnet` en el shell y, después, presione el tabulador. La línea de comandos que se envía al comando `dotnet complete` y los resultados se procesan mediante el shell. Puede probar los resultados sin habilitar la finalización con tabulación si envía algo directamente al comando `dotnet complete`. Por ejemplo:

```console
> dotnet complete "dotnet a"
add
clean
--diagnostics
migrate
pack
```

Si ese comando no funciona, asegúrese de que está instalado el SDK de .NET Core 2.0 o una versión superior. Si está instalado, pero el comando sigue sin funcionar, asegúrese de que `dotnet` se resuelva como mínimo en la versión 2.0 del SDK de .NET Core. Use el comando `dotnet --version` para ver en qué versión de `dotnet` se resuelve la ruta de acceso actual. Para obtener más información, vea [Selección de la versión de .NET Core que se va a usar](../versions/selection.md).

### <a name="examples"></a>Ejemplos

Estos son algunos ejemplos de lo que proporciona la finalización con tabulación:

Entrada                                | se convierte en                                                                     | porque
:------------------------------------|:----------------------------------------------------------------------------|:--------------------------------
`dotnet a⇥`                          | `dotnet add`                                                                 | `add` es el primer subcomando, por orden alfabético.
`dotnet add p⇥`                      | `dotnet add --help`                                                          | La finalización con tabulación hace coincidir las subcadenas y `--help` aparece primero alfabéticamente.
`dotnet add p⇥⇥`                    | `dotnet add package`                                                          | Al presionar la tecla Tab una segunda vez aparece la siguiente sugerencia.
`dotnet add package Microsoft⇥`      | `dotnet add package Microsoft.ApplicationInsights.Web`                      | Los resultados se devuelven por orden alfabético.
`dotnet remove reference ⇥`          | `dotnet remove reference ..\..\src\OmniSharp.DotNet\OmniSharp.DotNet.csproj` | La finalización con tabulación es compatible con archivos de proyecto.

## <a name="powershell"></a>PowerShell

Para agregar finalización con tabulación a **PowerShell** para la CLI de .NET, cree o edite el perfil almacenado en la variable `$PROFILE`. Para obtener más información, vea [Cómo crear el perfil](/powershell/module/microsoft.powershell.core/about/about_profiles#how-to-create-a-profile) y [Los perfiles y la directiva de ejecución](/powershell/module/microsoft.powershell.core/about/about_profiles#profiles-and-execution-policy).

Agregue el código siguiente al perfil:

```powershell
# PowerShell parameter completion shim for the dotnet CLI
Register-ArgumentCompleter -Native -CommandName dotnet -ScriptBlock {
     param($commandName, $wordToComplete, $cursorPosition)
         dotnet complete --position $cursorPosition "$wordToComplete" | ForEach-Object {
            [System.Management.Automation.CompletionResult]::new($_, $_, 'ParameterValue', $_)
         }
 }
```

## <a name="bash"></a>Bash

Para agregar finalización con tabulación al shell de **bash** para la CLI de .NET, agregue el código siguiente al archivo `.bashrc`:

```bash
# bash parameter completion for the dotnet CLI

_dotnet_bash_complete()
{
  local word=${COMP_WORDS[COMP_CWORD]}

  local completions
  completions="$(dotnet complete --position "${COMP_POINT}" "${COMP_LINE}" 2>/dev/null)"
  if [ $? -ne 0 ]; then
    completions=""
  fi

  COMPREPLY=( $(compgen -W "$completions" -- "$word") )
}

complete -f -F _dotnet_bash_complete dotnet
```

## <a name="zsh"></a>zsh

Para agregar finalización con tabulación al shell de **zsh** para la CLI de .NET, agregue el código siguiente al archivo `.zshrc`:

```zsh
# zsh parameter completion for the dotnet CLI

_dotnet_zsh_complete()
{
  local completions=("$(dotnet complete "$words")")

  reply=( "${(ps:\n:)completions}" )
}

compctl -K _dotnet_zsh_complete dotnet
```

## <a name="fish"></a>fish

Para agregar la finalización con tabulación al shell de **fish** para la CLI de .NET, agregue el código siguiente al archivo `config.fish`:

```fish
complete -f -c dotnet -a "(dotnet complete)"
```
