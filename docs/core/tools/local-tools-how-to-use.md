---
title: 'Tutorial: Instalación y uso de herramientas locales de .NET Core'
description: Aprenda a instalar y usar una herramienta de .NET como una herramienta local.
ms.date: 02/12/2020
ms.openlocfilehash: a4355886513040e2436bdbd87905e5baee2dd7a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "78156704"
---
# <a name="tutorial-install-and-use-a-net-core-local-tool-using-the-net-core-cli"></a><span data-ttu-id="2bd2d-103">Tutorial: Instalación y uso de una herramienta local de .NET Core mediante la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="2bd2d-103">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>

<span data-ttu-id="2bd2d-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="2bd2d-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

<span data-ttu-id="2bd2d-105">En este tutorial se enseña cómo instalar y usar una herramienta local.</span><span class="sxs-lookup"><span data-stu-id="2bd2d-105">This tutorial teaches you how to install and use a local tool.</span></span> <span data-ttu-id="2bd2d-106">Usará una herramienta que ha creado en el [primer tutorial de esta serie](global-tools-how-to-create.md).</span><span class="sxs-lookup"><span data-stu-id="2bd2d-106">You use a tool that you create in the [first tutorial of this series](global-tools-how-to-create.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2bd2d-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2bd2d-107">Prerequisites</span></span>

* <span data-ttu-id="2bd2d-108">Complete el [primer tutorial de esta serie](global-tools-how-to-create.md).</span><span class="sxs-lookup"><span data-stu-id="2bd2d-108">Complete the [first tutorial of this series](global-tools-how-to-create.md).</span></span>
* <span data-ttu-id="2bd2d-109">Instale el entorno de ejecución de .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="2bd2d-109">Install the .NET Core 2.1 runtime.</span></span>

  <span data-ttu-id="2bd2d-110">En este tutorial, instalará y usará una herramienta que tiene como destino .NET Core 2.1, por lo que debe tener ese entorno de ejecución instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="2bd2d-110">For this tutorial you install and use a tool that targets .NET Core 2.1, so you need to have that runtime installed on your machine.</span></span> <span data-ttu-id="2bd2d-111">Para instalar la versión 2.1 del entorno de ejecución, vaya a la [página de descarga de .NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1) y busque el vínculo de instalación del entorno de ejecución en la columna **Ejecutar aplicaciones: entorno de ejecución**.</span><span class="sxs-lookup"><span data-stu-id="2bd2d-111">To install the 2.1 runtime, go to the [.NET Core 2.1 download page](https://dotnet.microsoft.com/download/dotnet-core/2.1) and find the runtime installation link in the **Run apps - Runtime** column.</span></span>

## <a name="create-a-manifest-file"></a><span data-ttu-id="2bd2d-112">Crear un archivo de manifiesto</span><span class="sxs-lookup"><span data-stu-id="2bd2d-112">Create a manifest file</span></span>

<span data-ttu-id="2bd2d-113">Para instalar una herramienta solo para el acceso local (del directorio y los subdirectorios actuales), debe agregarse a un archivo de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="2bd2d-113">To install a tool for local access only (for the current directory and subdirectories), it has to be added to a manifest file.</span></span>

<span data-ttu-id="2bd2d-114">Desde la carpeta *microsoft.botsay*, suba un nivel hasta la carpeta *repository*:</span><span class="sxs-lookup"><span data-stu-id="2bd2d-114">From the *microsoft.botsay* folder, navigate up one level to the *repository* folder:</span></span>

```console
cd ..
```

<span data-ttu-id="2bd2d-115">Cree un archivo de manifiesto; para ello, ejecute el comando [dotnet new](dotnet-new.md):</span><span class="sxs-lookup"><span data-stu-id="2bd2d-115">Create a manifest file by running the [dotnet new](dotnet-new.md) command:</span></span>

```dotnetcli
dotnet new tool-manifest
```

<span data-ttu-id="2bd2d-116">En la salida se indica que el archivo se ha creado correctamente.</span><span class="sxs-lookup"><span data-stu-id="2bd2d-116">The output indicates successful creation of the file.</span></span>

```console
The template "Dotnet local tool manifest file" was created successfully.
```

<span data-ttu-id="2bd2d-117">El archivo *.config/dotnet-tools.json* aún no contiene ninguna herramienta:</span><span class="sxs-lookup"><span data-stu-id="2bd2d-117">The *.config/dotnet-tools.json* file has no tools in it yet:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {}
}
```

<span data-ttu-id="2bd2d-118">Las herramientas enumeradas en un archivo de manifiesto están disponibles en el directorio y los subdirectorios actuales.</span><span class="sxs-lookup"><span data-stu-id="2bd2d-118">The tools listed in a manifest file are available to the current directory and subdirectories.</span></span> <span data-ttu-id="2bd2d-119">El directorio actual es el que contiene el directorio *.config* con el archivo de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="2bd2d-119">The current directory is the one that contains the *.config* directory with the manifest file.</span></span>

<span data-ttu-id="2bd2d-120">Si se usa un comando de la CLI que hace referencia a una herramienta local, el SDK busca un archivo de manifiesto en el directorio actual y los directorios principales.</span><span class="sxs-lookup"><span data-stu-id="2bd2d-120">When you use a CLI command that refers to a local tool, the SDK searches for a manifest file in the current directory and parent directories.</span></span> <span data-ttu-id="2bd2d-121">Si encuentra un archivo de manifiesto, pero el archivo no incluye la herramienta a la que se hace referencia, continúa con la búsqueda en los directorios principales.</span><span class="sxs-lookup"><span data-stu-id="2bd2d-121">If it finds a manifest file, but the file doesn't include the referenced tool, it continues the search up through parent directories.</span></span> <span data-ttu-id="2bd2d-122">La búsqueda finaliza cuando encuentra la herramienta a la que se hace referencia o un archivo de manifiesto con `isRoot` establecido en `true`.</span><span class="sxs-lookup"><span data-stu-id="2bd2d-122">The search ends when it finds the referenced tool or it finds a manifest file with `isRoot` set to `true`.</span></span>

## <a name="install-botsay-as-a-local-tool"></a><span data-ttu-id="2bd2d-123">Instalación de botsay como una herramienta local</span><span class="sxs-lookup"><span data-stu-id="2bd2d-123">Install botsay as a local tool</span></span>

<span data-ttu-id="2bd2d-124">Instale la herramienta desde el paquete que ha creado en el primer tutorial:</span><span class="sxs-lookup"><span data-stu-id="2bd2d-124">Install the tool from the package that you created in the first tutorial:</span></span>

```dotnetcli
dotnet tool install --add-source ./microsoft.botsay/nupkg microsoft.botsay
```

<span data-ttu-id="2bd2d-125">Este comando agrega la herramienta al archivo de manifiesto que ha creado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="2bd2d-125">This command adds the tool to the manifest file that you created in the preceding step.</span></span> <span data-ttu-id="2bd2d-126">En la salida del comando se muestra el archivo de manifiesto en el que se encuentra la herramienta que acaba de instalar:</span><span class="sxs-lookup"><span data-stu-id="2bd2d-126">The command output shows which manifest file the newly installed tool is in:</span></span>

 ```console
 You can invoke the tool from this directory using the following command:
 'dotnet tool run botsay' or 'dotnet botsay'
 Tool 'microsoft.botsay' (version '1.0.0') was successfully installed.
 Entry is added to the manifest file /home/name/repository/.config/dotnet-tools.json
 ```

<span data-ttu-id="2bd2d-127">Ahora, el archivo *.config/dotnet-tools.json* tiene una herramienta:</span><span class="sxs-lookup"><span data-stu-id="2bd2d-127">The *.config/dotnet-tools.json* file now has one tool:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "microsoft.botsay": {
      "version": "1.0.0",
      "commands": [
        "botsay"
      ]
    }
  }
}
```

## <a name="use-the-tool"></a><span data-ttu-id="2bd2d-128">Usar la herramienta</span><span class="sxs-lookup"><span data-stu-id="2bd2d-128">Use the tool</span></span>

<span data-ttu-id="2bd2d-129">Para invocar la herramienta, ejecute el comando `dotnet tool run` desde la carpeta *repository*:</span><span class="sxs-lookup"><span data-stu-id="2bd2d-129">Invoke the tool by running the `dotnet tool run` command from the *repository* folder:</span></span>

```dotnetcli
dotnet tool run botsay hello from the bot
```

## <a name="restore-a-local-tool-installed-by-others"></a><span data-ttu-id="2bd2d-130">Restauración de una herramienta local instalada por otros usuarios</span><span class="sxs-lookup"><span data-stu-id="2bd2d-130">Restore a local tool installed by others</span></span>

<span data-ttu-id="2bd2d-131">Normalmente, una herramienta local se instala en el directorio raíz del repositorio.</span><span class="sxs-lookup"><span data-stu-id="2bd2d-131">You typically install a local tool in the root directory of the repository.</span></span> <span data-ttu-id="2bd2d-132">Después de insertar el archivo de manifiesto en el repositorio, otros desarrolladores pueden obtener el archivo de manifiesto más reciente.</span><span class="sxs-lookup"><span data-stu-id="2bd2d-132">After you check in the manifest file to the repository, other developers can get the latest manifest file.</span></span> <span data-ttu-id="2bd2d-133">Para instalar todas las herramientas enumeradas en el archivo de manifiesto, pueden ejecutar un único comando `dotnet tool restore`.</span><span class="sxs-lookup"><span data-stu-id="2bd2d-133">To install all of the tools listed in the manifest file, they can run a single `dotnet tool restore` command.</span></span>

1. <span data-ttu-id="2bd2d-134">Abra el archivo *.config/dotnet-tools.json* y reemplace el contenido con el siguiente código JSON:</span><span class="sxs-lookup"><span data-stu-id="2bd2d-134">Open the *.config/dotnet-tools.json* file, and replace the contents with the following JSON:</span></span>

   ```json
   {
     "version": 1,
     "isRoot": true,
     "tools": {
       "microsoft.botsay": {
         "version": "1.0.0",
         "commands": [
           "botsay"
         ]
       },
       "dotnetsay": {
         "version": "2.1.3",
         "commands": [
           "dotnetsay"
         ]
       }
     }
   }
   ```

1. <span data-ttu-id="2bd2d-135">Reemplace `<name>` con el nombre que ha usado para crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="2bd2d-135">Replace `<name>` with the name you used to create the project.</span></span>

1. <span data-ttu-id="2bd2d-136">Guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="2bd2d-136">Save your changes.</span></span>

   <span data-ttu-id="2bd2d-137">Cambiar esto tiene el mismo resultado que obtener la versión más reciente del repositorio después de que otra persona haya instalado el paquete `dotnetsay` en el directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="2bd2d-137">Making this change is the same as getting the latest version from the repository after someone else installed the package `dotnetsay` for the project directory.</span></span>

1. <span data-ttu-id="2bd2d-138">Ejecute el comando `dotnet tool restore`.</span><span class="sxs-lookup"><span data-stu-id="2bd2d-138">Run the `dotnet tool restore` command.</span></span>

   ```dotnetcli
   dotnet tool restore
   ```

   <span data-ttu-id="2bd2d-139">El comando genera una salida como la del siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2bd2d-139">The command produces output like the following example:</span></span>

   ```console
   Tool 'microsoft.botsay' (version '1.0.0') was restored. Available commands: botsay
   Tool 'dotnetsay' (version '2.1.3') was restored. Available commands: dotnetsay
   Restore was successful.
   ```

1. <span data-ttu-id="2bd2d-140">Compruebe que las herramientas están disponibles:</span><span class="sxs-lookup"><span data-stu-id="2bd2d-140">Verify that the tools are available:</span></span>

   ```dotnetcli
   dotnet tool list
   ```

   <span data-ttu-id="2bd2d-141">La salida es una lista de paquetes y comandos, similar al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2bd2d-141">The output is a list of packages and commands, similar to the following example:</span></span>

   ```console
   Package Id      Version      Commands       Manifest
   --------------------------------------------------------------------------------------------
   microsoft.botsay 1.0.0        botsay         /home/name/repository/.config/dotnet-tools.json
   dotnetsay        2.1.3        dotnetsay      /home/name/repository/.config/dotnet-tools.json
   ```

1. <span data-ttu-id="2bd2d-142">Pruebe las herramientas:</span><span class="sxs-lookup"><span data-stu-id="2bd2d-142">Test the tools:</span></span>

   ```dotnetcli
   dotnet tool run dotnetsay hello from dotnetsay
   dotnet tool run botsay hello from botsay
   ```

## <a name="update-a-local-tool"></a><span data-ttu-id="2bd2d-143">Actualización de una herramienta local</span><span class="sxs-lookup"><span data-stu-id="2bd2d-143">Update a local tool</span></span>

<span data-ttu-id="2bd2d-144">La versión instalada de la herramienta local `dotnetsay` es 2.1.3.</span><span class="sxs-lookup"><span data-stu-id="2bd2d-144">The installed version of local tool `dotnetsay` is 2.1.3.</span></span>  <span data-ttu-id="2bd2d-145">La versión más reciente es 2.1.4.</span><span class="sxs-lookup"><span data-stu-id="2bd2d-145">The latest version is 2.1.4.</span></span> <span data-ttu-id="2bd2d-146">Use el comando [dotnet tool update](dotnet-tool-update.md) para actualizar la herramienta a la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="2bd2d-146">Use the [dotnet tool update](dotnet-tool-update.md) command to update the tool to the latest version.</span></span>

```dotnetcli
dotnet tool update dotnetsay
```

<span data-ttu-id="2bd2d-147">En la salida se indica el nuevo número de versión:</span><span class="sxs-lookup"><span data-stu-id="2bd2d-147">The output indicates the new version number:</span></span>

```console
Tool 'dotnetsay' was successfully updated from version '2.1.3' to version '2.1.4'
(manifest file /home/name/repository/.config/dotnet-tools.json).
```

<span data-ttu-id="2bd2d-148">El comando update busca el primer archivo de manifiesto que contiene el identificador del paquete y lo actualiza.</span><span class="sxs-lookup"><span data-stu-id="2bd2d-148">The update command finds the first manifest file that contains the package ID and updates it.</span></span> <span data-ttu-id="2bd2d-149">Si no hay ningún identificador del paquete en ningún archivo de manifiesto que esté en el ámbito de la búsqueda, el SDK agrega una nueva entrada al archivo de manifiesto más cercano.</span><span class="sxs-lookup"><span data-stu-id="2bd2d-149">If there is no such package ID in any manifest file that is in the scope of the search, the SDK adds a new entry to the closest manifest file.</span></span> <span data-ttu-id="2bd2d-150">El ámbito de búsqueda va hacia los directorios principales hasta que se encuentra un archivo de manifiesto con `isRoot = true`.</span><span class="sxs-lookup"><span data-stu-id="2bd2d-150">The search scope is up through parent directories until a manifest file with `isRoot = true` is found.</span></span>

## <a name="remove-local-tools"></a><span data-ttu-id="2bd2d-151">Eliminación de las herramientas locales</span><span class="sxs-lookup"><span data-stu-id="2bd2d-151">Remove local tools</span></span>

<span data-ttu-id="2bd2d-152">Ejecute el comando [dotnet tool uninstall](dotnet-tool-uninstall.md) para quitar las herramientas instaladas:</span><span class="sxs-lookup"><span data-stu-id="2bd2d-152">Remove the installed tools by running the [dotnet tool uninstall](dotnet-tool-uninstall.md) command:</span></span>

```dotnetcli
dotnet tool uninstall microsoft.botsay
```

```dotnetcli
dotnet tool uninstall dotnetsay
```

## <a name="troubleshoot"></a><span data-ttu-id="2bd2d-153">Solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="2bd2d-153">Troubleshoot</span></span>

<span data-ttu-id="2bd2d-154">Si recibe un mensaje de error al seguir el tutorial, consulte [Solución de problemas de uso de herramientas de .NET Core](troubleshoot-usage-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2bd2d-154">If you get an error message while following the tutorial, see [Troubleshoot .NET Core tool usage issues](troubleshoot-usage-issues.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2bd2d-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="2bd2d-155">See also</span></span>

<span data-ttu-id="2bd2d-156">Para obtener más información, vea [Herramientas de .NET Core](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2bd2d-156">For more information, see [.NET Core tools](global-tools.md)</span></span>
