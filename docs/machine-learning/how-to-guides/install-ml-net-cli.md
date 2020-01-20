---
title: Cómo instalar la herramienta de la interfaz de la línea de comandos (CLI) de ML.NET
description: Obtenga información sobre cómo instalar, cambiar a una versión anterior y desinstalar la herramienta de la interfaz de la línea de comandos (CLI) de ML.NET.
ms.date: 12/18/2019
ms.openlocfilehash: 350122f2d2d2f03484ab6e272b482adf2094495c
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75739970"
---
# <a name="how-to-install-the-mlnet-command-line-interface-cli-tool"></a><span data-ttu-id="30764-103">Cómo instalar la herramienta de la interfaz de la línea de comandos (CLI) de ML.NET</span><span class="sxs-lookup"><span data-stu-id="30764-103">How to install the ML.NET Command-Line Interface (CLI) tool</span></span>

<span data-ttu-id="30764-104">Obtenga información sobre cómo instalar la CLI (interfaz de la línea de comandos) de ML.NET en Windows, Mac o Linux.</span><span class="sxs-lookup"><span data-stu-id="30764-104">Learn how to install the ML.NET CLI (command-line interface) on Windows, Mac, or Linux.</span></span>

<span data-ttu-id="30764-105">La CLI de ML.NET genera código fuente y modelos de ML.NET de buena calidad mediante el aprendizaje automático automatizado (AutoML) y un conjunto de datos de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="30764-105">The ML.NET CLI generates good quality ML.NET models and source code using automated machine learning (AutoML) and a training dataset.</span></span>

> [!NOTE]
> <span data-ttu-id="30764-106">Este tema hace referencia a la CLI de ML.NET y AutoML de ML.NET, que se encuentran actualmente en versión preliminar, por lo que el material está sujeto a cambios.</span><span class="sxs-lookup"><span data-stu-id="30764-106">This topic refers to ML.NET CLI and ML.NET AutoML, which are currently in Preview, and material may be subject to change.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="30764-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="30764-107">Pre-requisites</span></span>

- [<span data-ttu-id="30764-108">SDK de .NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="30764-108">.NET Core 2.2 SDK</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)

- <span data-ttu-id="30764-109">(Opcional) [Visual Studio 2017 o 2019](https://visualstudio.microsoft.com/vs/)</span><span class="sxs-lookup"><span data-stu-id="30764-109">(Optional) [Visual Studio 2017 or 2019](https://visualstudio.microsoft.com/vs/)</span></span>

<span data-ttu-id="30764-110">Puede ejecutar los proyectos del código de C# generado con Visual Studio presionando la tecla `F5` o con `dotnet run` (CLI de .NET Core).</span><span class="sxs-lookup"><span data-stu-id="30764-110">You can run the generated C# code projects with Visual Studio by pressing the `F5` key or with `dotnet run` (.NET Core CLI).</span></span>

<span data-ttu-id="30764-111">Nota: Si después de instalar el [SDK de .NET Core 2.2](https://dotnet.microsoft.com/download/dotnet-core/2.2) el comando `dotnet tool` no funciona, cierre la sesión de Windows y vuelva a iniciarla.</span><span class="sxs-lookup"><span data-stu-id="30764-111">Note: If after installing [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download/dotnet-core/2.2) the `dotnet tool` command is not working, sign out from Windows and sign in again.</span></span>

## <a name="install"></a><span data-ttu-id="30764-112">Instalar</span><span class="sxs-lookup"><span data-stu-id="30764-112">Install</span></span>

<span data-ttu-id="30764-113">La CLI de ML.NET se instala como cualquier otra herramienta global de dotnet.</span><span class="sxs-lookup"><span data-stu-id="30764-113">The ML.NET CLI is installed like any other dotnet Global Tool.</span></span> <span data-ttu-id="30764-114">Use el comando de la CLI de .NET Core de `dotnet tool install`.</span><span class="sxs-lookup"><span data-stu-id="30764-114">You use the `dotnet tool install` .NET Core CLI command.</span></span>

<span data-ttu-id="30764-115">En el ejemplo siguiente se muestra cómo instalar la CLI de ML.NET en la ubicación de la fuente de NuGet predeterminada:</span><span class="sxs-lookup"><span data-stu-id="30764-115">The following example shows how to install the ML.NET CLI in the default NuGet feed location:</span></span>

```dotnetcli
dotnet tool install -g mlnet
```

<span data-ttu-id="30764-116">Si la herramienta no se puede instalar (es decir, si no está disponible con la fuente de NuGet predeterminada), se muestran mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="30764-116">If the tool can't be installed (that is, if it is not available at the default NuGet feed), error messages are displayed.</span></span> <span data-ttu-id="30764-117">Verifique que se comprueban las fuentes que esperaba.</span><span class="sxs-lookup"><span data-stu-id="30764-117">Check that the feeds you expected are being checked.</span></span>

<span data-ttu-id="30764-118">Si la instalación es correcta, se muestra un mensaje similar al siguiente con el comando que se usa para llamar a la herramienta y la versión instalada:</span><span class="sxs-lookup"><span data-stu-id="30764-118">If installation is successful, a message is displayed showing the command used to call the tool and the version installed, similar to the following example:</span></span>

```console
You can invoke the tool using the following command: mlnet
Tool 'mlnet' (version 'X.X.X') was successfully installed.
```

<span data-ttu-id="30764-119">Para confirmar que la instalación se realizó correctamente, escriba el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="30764-119">You can confirm the installation was successful by typing the following command:</span></span>

```console
mlnet
```

<span data-ttu-id="30764-120">Debería ver la Ayuda de los comandos disponibles para la herramienta de mlnet, como el comando "auto-train".</span><span class="sxs-lookup"><span data-stu-id="30764-120">You should see the help for available commands for the mlnet tool such as the 'auto-train' command.</span></span>

## <a name="install-a-specific-release-version"></a><span data-ttu-id="30764-121">Instalar una versión de lanzamiento específica</span><span class="sxs-lookup"><span data-stu-id="30764-121">Install a specific release version</span></span>

<span data-ttu-id="30764-122">Si está intentando instalar una versión preliminar o una versión específica de la herramienta, puede especificar el [marco](../../standard/frameworks.md) con el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="30764-122">If you're trying to install a pre-release version or a specific version of the tool, you can specify the [framework](../../standard/frameworks.md) using the following format:</span></span>

```dotnetcli
dotnet tool install -g mlnet --framework <FRAMEWORK>
```

<span data-ttu-id="30764-123">También puede comprobar si el paquete está instalado correctamente. Para ello, escriba el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="30764-123">You can also check if the package is properly installed by typing the following command:</span></span>

```dotnetcli
dotnet tool list -g
```

## <a name="uninstall-the-cli-package"></a><span data-ttu-id="30764-124">Desinstalar el paquete de la CLI</span><span class="sxs-lookup"><span data-stu-id="30764-124">Uninstall the CLI package</span></span>

<span data-ttu-id="30764-125">Escriba el siguiente comando para desinstalar el paquete de la máquina local:</span><span class="sxs-lookup"><span data-stu-id="30764-125">Type the following command to uninstall the package from your local machine:</span></span>

```dotnetcli
dotnet tool uninstall mlnet -g
```

## <a name="update-the-cli-package"></a><span data-ttu-id="30764-126">Actualizar el paquete de la CLI</span><span class="sxs-lookup"><span data-stu-id="30764-126">Update the CLI package</span></span>

<span data-ttu-id="30764-127">Escriba el siguiente comando para actualizar l paquete de la máquina local:</span><span class="sxs-lookup"><span data-stu-id="30764-127">Type the following command to update the package from your local machine:</span></span>

```dotnetcli
dotnet tool update -g mlnet
```

## <a name="set-up-cli-suggestions-tab-based-auto-completion"></a><span data-ttu-id="30764-128">Configure las sugerencias de la CLI (finalización automática basada en tabulación)</span><span class="sxs-lookup"><span data-stu-id="30764-128">Set up CLI suggestions (tab-based auto-completion)</span></span>

<span data-ttu-id="30764-129">Puesto que la CLI de ML.NET se basa en `System.CommandLine`, tiene compatibilidad integrada para la finalización con tabulación.</span><span class="sxs-lookup"><span data-stu-id="30764-129">Since the ML.NET CLI is based on `System.CommandLine`, it has built-in support for tab completion.</span></span>

<span data-ttu-id="30764-130">En la siguiente animación se muestra un ejemplo de cómo funciona la finalización con tabulación automática:</span><span class="sxs-lookup"><span data-stu-id="30764-130">An example of how tab auto completion works is shown in the following animation:</span></span>

![imagen](./media/cli-tab-completion.gif)

<span data-ttu-id="30764-132">La "finalización automática basada en tabulación" (sugerencias de parámetro) funciona en *Windows PowerShell* y *bash de macOS/Linux*, pero no funcionará en *Windows CMD*.</span><span class="sxs-lookup"><span data-stu-id="30764-132">'Tab-based auto-completion' (parameter suggestions) works on *Windows PowerShell* and *macOS/Linux bash* but it won't work on *Windows CMD*.</span></span>

<span data-ttu-id="30764-133">Para habilitarla, en la versión preliminar actual, el usuario final debe realizar algunos pasos una vez por cada shell, los cuales se describen a continuación.</span><span class="sxs-lookup"><span data-stu-id="30764-133">To enable it, in the current preview version, the end user has to take a few steps once per shell, outlined below.</span></span> <span data-ttu-id="30764-134">Una vez que se realizó esta acción, las finalizaciones funcionarán para todas las aplicaciones escritas con `System.CommandLine`, como la CLI de ML.NET.</span><span class="sxs-lookup"><span data-stu-id="30764-134">Once this is done, completions will work for all apps written using `System.CommandLine` such as the ML.NET CLI.</span></span>

<span data-ttu-id="30764-135">En el equipo donde desea habilitar la finalización, deberá hacer dos cosas.</span><span class="sxs-lookup"><span data-stu-id="30764-135">On the machine where you'd like to enable completion, you'll need to do two things.</span></span>

1. <span data-ttu-id="30764-136">Instale la herramienta global `dotnet-suggest` mediante la ejecución del comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="30764-136">Install the `dotnet-suggest` global tool by running the following command:</span></span>

    ```dotnetcli
    dotnet tool install dotnet-suggest -g
    ```

2. <span data-ttu-id="30764-137">Agregue el script de correcciones de compatibilidad (shim) adecuado a su perfil de shell.</span><span class="sxs-lookup"><span data-stu-id="30764-137">Add the appropriate shim script to your shell profile.</span></span> <span data-ttu-id="30764-138">Es posible que deba crear un archivo de perfil de shell.</span><span class="sxs-lookup"><span data-stu-id="30764-138">You may have to create a shell profile file.</span></span> <span data-ttu-id="30764-139">El script de correcciones de compatibilidad (shim) reenvía las solicitudes de finalización desde el shell a la herramienta `dotnet-suggest`, que delega a la aplicación basada en `System.CommandLine` adecuada.</span><span class="sxs-lookup"><span data-stu-id="30764-139">The shim script will forward completion requests from your shell to the `dotnet-suggest` tool, which delegates to the appropriate `System.CommandLine`-based app.</span></span>

    - <span data-ttu-id="30764-140">Para bash, agregue el contenido de [dotnet-suggest-shim.bash](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.bash) a `~/.bash_profile`.</span><span class="sxs-lookup"><span data-stu-id="30764-140">For bash, add the contents of [dotnet-suggest-shim.bash](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.bash) to `~/.bash_profile`.</span></span>

    - <span data-ttu-id="30764-141">Para PowerShell, agregue el contenido del [dotnet-suggest-shim.ps1](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.ps1) al perfil de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="30764-141">For PowerShell, add the contents of [dotnet-suggest-shim.ps1](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.ps1) to your PowerShell profile.</span></span> <span data-ttu-id="30764-142">Puede encontrar la ruta de acceso prevista para el perfil de PowerShell ejecutando el comando siguiente en la consola:</span><span class="sxs-lookup"><span data-stu-id="30764-142">You can find the expected path to your PowerShell profile by running the following command in your console:</span></span>

    ```console
    echo $profile
    ```

<span data-ttu-id="30764-143">(Para otros shells, [busque](https://github.com/dotnet/System.CommandLine/issues?q=is%3Aissue+is%3Aopen+label%3A%22shell+suggestion%22) o abra una [incidencia](https://github.com/dotnet/System.CommandLine/issues).)</span><span class="sxs-lookup"><span data-stu-id="30764-143">(For other shells, [look for](https://github.com/dotnet/System.CommandLine/issues?q=is%3Aissue+is%3Aopen+label%3A%22shell+suggestion%22) or open an [issue](https://github.com/dotnet/System.CommandLine/issues).)</span></span>

## <a name="installation-directory"></a><span data-ttu-id="30764-144">Directorio de instalación</span><span class="sxs-lookup"><span data-stu-id="30764-144">Installation directory</span></span>

<span data-ttu-id="30764-145">La CLI de ML.NET puede instalarse en el directorio predeterminado o en una ubicación específica.</span><span class="sxs-lookup"><span data-stu-id="30764-145">The ML.NET CLI can be installed in the default directory or in a specific location.</span></span> <span data-ttu-id="30764-146">Los directorios predeterminados son:</span><span class="sxs-lookup"><span data-stu-id="30764-146">The default directories are:</span></span>

| <span data-ttu-id="30764-147">SO</span><span class="sxs-lookup"><span data-stu-id="30764-147">OS</span></span>          | <span data-ttu-id="30764-148">Ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="30764-148">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="30764-149">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="30764-149">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="30764-150">Windows</span><span class="sxs-lookup"><span data-stu-id="30764-150">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="30764-151">Estas ubicaciones se agregan a la ruta de acceso del usuario cuando se ejecuta el SDK por primera vez, permitiendo así llamar directamente a las herramientas globales allí instaladas.</span><span class="sxs-lookup"><span data-stu-id="30764-151">These locations are added to the user's path when the SDK is first run, so Global Tools installed there can be called directly.</span></span>

<span data-ttu-id="30764-152">Nota: Las herramientas globales son específicas del usuario, no de la máquina.</span><span class="sxs-lookup"><span data-stu-id="30764-152">Note: the Global Tools are user-specific, not machine global.</span></span> <span data-ttu-id="30764-153">Específica del usuario significa que no se puede instalar una herramienta global que está disponible para todos los usuarios de la máquina.</span><span class="sxs-lookup"><span data-stu-id="30764-153">Being user-specific means you cannot install a Global Tool that is available to all users of the machine.</span></span> <span data-ttu-id="30764-154">La herramienta solo está disponible para cada perfil de usuario en el que se instaló la herramienta.</span><span class="sxs-lookup"><span data-stu-id="30764-154">The tool is only available for each user profile where the tool was installed.</span></span>

<span data-ttu-id="30764-155">Las herramientas globales también pueden instalarse en un directorio específico.</span><span class="sxs-lookup"><span data-stu-id="30764-155">Global Tools can also be installed in a specific directory.</span></span> <span data-ttu-id="30764-156">Cuando se instalan en un directorio específico, el usuario debe incluir el directorio en la ruta de acceso a fin de asegurarse de que el comando está disponible. Hay dos maneras de hacerlo: llamar al comando con el directorio especificado, o llamar a la herramienta desde el directorio especificado.</span><span class="sxs-lookup"><span data-stu-id="30764-156">When installed in a specific directory, the user must ensure the command is available, by including that directory in the path, by calling the command with the directory specified, or calling the tool from within the specified directory.</span></span>
<span data-ttu-id="30764-157">En este caso, la CLI de .NET Core no agrega esta ubicación automáticamente a la variable de entorno PATH.</span><span class="sxs-lookup"><span data-stu-id="30764-157">In this case, the .NET Core CLI doesn't add this location automatically to the PATH environment variable.</span></span>

## <a name="see-also"></a><span data-ttu-id="30764-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="30764-158">See also</span></span>

- [<span data-ttu-id="30764-159">Información general sobre la CLI de ML.NET</span><span class="sxs-lookup"><span data-stu-id="30764-159">ML.NET CLI overview</span></span>](../automate-training-with-cli.md)
- [<span data-ttu-id="30764-160">Tutorial: Análisis de opiniones mediante la CLI de ML.NET</span><span class="sxs-lookup"><span data-stu-id="30764-160">Tutorial: Analyze sentiment with the ML.NET CLI</span></span>](../tutorials/sentiment-analysis-cli.md)
- [<span data-ttu-id="30764-161">Guía de referencia de comandos de entrenamiento automático de la CLI de ML.NET</span><span class="sxs-lookup"><span data-stu-id="30764-161">ML.NET CLI auto-train command reference guide</span></span>](../reference/ml-net-cli-reference.md)
- [<span data-ttu-id="30764-162">Telemetría en la CLI de ML.NET</span><span class="sxs-lookup"><span data-stu-id="30764-162">Telemetry in ML.NET CLI</span></span>](../resources/ml-net-cli-telemetry.md)
