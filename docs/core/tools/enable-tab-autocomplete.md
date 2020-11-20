---
title: Habilitación de la finalización con tabulación
description: En este artículo se describe cómo habilitar la finalización con tabulación para la CLI de .NET en PowerShell, bash y zsh.
author: adegeo
ms.author: adegeo
ms.topic: how-to
ms.date: 11/03/2019
ms.openlocfilehash: 31bf5e74644680fc30ca5b79972fbed6367363e1
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634017"
---
# <a name="how-to-enable-tab-completion-for-the-net-cli"></a><span data-ttu-id="c9ade-103">Procedimiento para habilitar la finalización con tabulación para la CLI de .NET</span><span class="sxs-lookup"><span data-stu-id="c9ade-103">How to enable TAB completion for the .NET CLI</span></span>

<span data-ttu-id="c9ade-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="c9ade-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="c9ade-105">En este artículo se describe cómo configurar la finalización con tabulación para tres shells: PowerShell, Bash y zsh.</span><span class="sxs-lookup"><span data-stu-id="c9ade-105">This article describes how to configure tab completion for three shells, PowerShell, Bash, and zsh.</span></span> <span data-ttu-id="c9ade-106">En el caso de otros shells, consulte la documentación para saber cómo configurar la finalización con tabulación.</span><span class="sxs-lookup"><span data-stu-id="c9ade-106">For other shells, refer to their documentation on how to configure tab completion.</span></span>

<span data-ttu-id="c9ade-107">Una vez que se ha configurado, para desencadenar la finalización con tabulación para la CLI de .NET, escriba un comando `dotnet` en el shell y, después, presione el tabulador.</span><span class="sxs-lookup"><span data-stu-id="c9ade-107">Once set up, tab completion for the .NET CLI is triggered by typing a `dotnet` command in the shell, and then pressing the TAB key.</span></span> <span data-ttu-id="c9ade-108">La línea de comandos que se envía al comando `dotnet complete` y los resultados se procesan mediante el shell.</span><span class="sxs-lookup"><span data-stu-id="c9ade-108">The current command line is sent to the `dotnet complete` command, and the results are processed by your shell.</span></span> <span data-ttu-id="c9ade-109">Puede probar los resultados sin habilitar la finalización con tabulación si envía algo directamente al comando `dotnet complete`.</span><span class="sxs-lookup"><span data-stu-id="c9ade-109">You can test the results without enabling tab completion by sending something directly to the `dotnet complete` command.</span></span> <span data-ttu-id="c9ade-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c9ade-110">For example:</span></span>

```console
> dotnet complete "dotnet a"
add
clean
--diagnostics
migrate
pack
```

<span data-ttu-id="c9ade-111">Si ese comando no funciona, asegúrese de que está instalado el SDK de .NET Core 2.0 o una versión superior.</span><span class="sxs-lookup"><span data-stu-id="c9ade-111">If that command doesn't work, make sure that .NET Core 2.0 SDK or above is installed.</span></span> <span data-ttu-id="c9ade-112">Si está instalado, pero el comando sigue sin funcionar, asegúrese de que `dotnet` se resuelva como mínimo en la versión 2.0 del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c9ade-112">If it's installed, but that command still doesn't work, make sure that the `dotnet` command resolves to a version of .NET Core 2.0 SDK and above.</span></span> <span data-ttu-id="c9ade-113">Use el comando `dotnet --version` para ver en qué versión de `dotnet` se resuelve la ruta de acceso actual.</span><span class="sxs-lookup"><span data-stu-id="c9ade-113">Use the `dotnet --version` command to see what version of `dotnet` your current path is resolving to.</span></span> <span data-ttu-id="c9ade-114">Para obtener más información, vea [Selección de la versión de .NET Core que se va a usar](../versions/selection.md).</span><span class="sxs-lookup"><span data-stu-id="c9ade-114">For more information, see [Select the .NET version to use](../versions/selection.md).</span></span>

### <a name="examples"></a><span data-ttu-id="c9ade-115">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c9ade-115">Examples</span></span>

<span data-ttu-id="c9ade-116">Estos son algunos ejemplos de lo que proporciona la finalización con tabulación:</span><span class="sxs-lookup"><span data-stu-id="c9ade-116">Here are some examples of what tab completion provides:</span></span>

<span data-ttu-id="c9ade-117">Entrada</span><span class="sxs-lookup"><span data-stu-id="c9ade-117">Input</span></span>                                | <span data-ttu-id="c9ade-118">se convierte en</span><span class="sxs-lookup"><span data-stu-id="c9ade-118">becomes</span></span>                                                                     | <span data-ttu-id="c9ade-119">porque</span><span class="sxs-lookup"><span data-stu-id="c9ade-119">because</span></span>
:------------------------------------|:----------------------------------------------------------------------------|:--------------------------------
`dotnet a⇥`                          | `dotnet add`                                                                 | <span data-ttu-id="c9ade-120">`add` es el primer subcomando, por orden alfabético.</span><span class="sxs-lookup"><span data-stu-id="c9ade-120">`add` is the first subcommand, alphabetically.</span></span>
`dotnet add p⇥`                      | `dotnet add --help`                                                          | <span data-ttu-id="c9ade-121">La finalización con tabulación hace coincidir las subcadenas y `--help` aparece primero alfabéticamente.</span><span class="sxs-lookup"><span data-stu-id="c9ade-121">Tab completion matches substrings and `--help` comes first alphabetically.</span></span>
`dotnet add p⇥⇥`                    | `dotnet add package`                                                          | <span data-ttu-id="c9ade-122">Al presionar la tecla Tab una segunda vez aparece la siguiente sugerencia.</span><span class="sxs-lookup"><span data-stu-id="c9ade-122">Pressing tab a second time brings up the next suggestion.</span></span>
`dotnet add package Microsoft⇥`      | `dotnet add package Microsoft.ApplicationInsights.Web`                      | <span data-ttu-id="c9ade-123">Los resultados se devuelven por orden alfabético.</span><span class="sxs-lookup"><span data-stu-id="c9ade-123">Results are returned alphabetically.</span></span>
`dotnet remove reference ⇥`          | `dotnet remove reference ..\..\src\OmniSharp.DotNet\OmniSharp.DotNet.csproj` | <span data-ttu-id="c9ade-124">La finalización con tabulación es compatible con archivos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="c9ade-124">Tab completion is project file aware.</span></span>

## <a name="powershell"></a><span data-ttu-id="c9ade-125">PowerShell</span><span class="sxs-lookup"><span data-stu-id="c9ade-125">PowerShell</span></span>

<span data-ttu-id="c9ade-126">Para agregar finalización con tabulación a **PowerShell** para la CLI de .NET, cree o edite el perfil almacenado en la variable `$PROFILE`.</span><span class="sxs-lookup"><span data-stu-id="c9ade-126">To add tab completion to **PowerShell** for the .NET CLI, create or edit the profile stored in the variable `$PROFILE`.</span></span> <span data-ttu-id="c9ade-127">Para obtener más información, vea [Cómo crear el perfil](/powershell/module/microsoft.powershell.core/about/about_profiles#how-to-create-a-profile) y [Los perfiles y la directiva de ejecución](/powershell/module/microsoft.powershell.core/about/about_profiles#profiles-and-execution-policy).</span><span class="sxs-lookup"><span data-stu-id="c9ade-127">For more information, see [How to create your profile](/powershell/module/microsoft.powershell.core/about/about_profiles#how-to-create-a-profile) and [Profiles and execution policy](/powershell/module/microsoft.powershell.core/about/about_profiles#profiles-and-execution-policy).</span></span>

<span data-ttu-id="c9ade-128">Agregue el código siguiente al perfil:</span><span class="sxs-lookup"><span data-stu-id="c9ade-128">Add the following code to your profile:</span></span>

```powershell
# PowerShell parameter completion shim for the dotnet CLI
Register-ArgumentCompleter -Native -CommandName dotnet -ScriptBlock {
     param($commandName, $wordToComplete, $cursorPosition)
         dotnet complete --position $cursorPosition "$wordToComplete" | ForEach-Object {
            [System.Management.Automation.CompletionResult]::new($_, $_, 'ParameterValue', $_)
         }
 }
```

## <a name="bash"></a><span data-ttu-id="c9ade-129">Bash</span><span class="sxs-lookup"><span data-stu-id="c9ade-129">bash</span></span>

<span data-ttu-id="c9ade-130">Para agregar finalización con tabulación al shell de **bash** para la CLI de .NET, agregue el código siguiente al archivo `.bashrc`:</span><span class="sxs-lookup"><span data-stu-id="c9ade-130">To add tab completion to your **bash** shell for the .NET CLI, add the following code to your `.bashrc` file:</span></span>

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

## <a name="zsh"></a><span data-ttu-id="c9ade-131">zsh</span><span class="sxs-lookup"><span data-stu-id="c9ade-131">zsh</span></span>

<span data-ttu-id="c9ade-132">Para agregar finalización con tabulación al shell de **zsh** para la CLI de .NET, agregue el código siguiente al archivo `.zshrc`:</span><span class="sxs-lookup"><span data-stu-id="c9ade-132">To add tab completion to your **zsh** shell for the .NET CLI, add the following code to your `.zshrc` file:</span></span>

```zsh
# zsh parameter completion for the dotnet CLI

_dotnet_zsh_complete()
{
  local completions=("$(dotnet complete "$words")")

  reply=( "${(ps:\n:)completions}" )
}

compctl -K _dotnet_zsh_complete dotnet
```
