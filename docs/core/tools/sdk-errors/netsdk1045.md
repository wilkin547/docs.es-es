---
title: 'NETSDK1045: El SDK de .NET actual no es compatible con "versión más reciente" como destino.'
description: Obtenga información sobre el error NETSDK1045 del SDK de .NET, que se produce cuando las herramientas de compilación no pueden encontrar la versión solicitada del SDK de .NET.
ms.topic: error-reference
ms.date: 02/12/2021
f1_keywords:
- NETSDK1045
ms.openlocfilehash: 900402ae01f945b1096170ea4fc79d00ea789b62
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100488253"
---
# <a name="netsdk1045-the-current-net-sdk-does-not-support-newer-version-as-a-target"></a><span data-ttu-id="b94d9-103">NETSDK1045: El SDK de .NET actual no es compatible con "versión más reciente" como destino.</span><span class="sxs-lookup"><span data-stu-id="b94d9-103">NETSDK1045: The current .NET SDK does not support 'newer version' as a target.</span></span>

<span data-ttu-id="b94d9-104">**Este artículo se aplica a: ✔️** SDK de .NET Core 2.1.100 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="b94d9-104">**This article applies to:** ✔️ .NET Core 2.1.100 SDK and later versions</span></span>

<span data-ttu-id="b94d9-105">Este error se produce cuando las herramientas de compilación no pueden encontrar la versión del SDK de .NET necesaria para compilar un proyecto.</span><span class="sxs-lookup"><span data-stu-id="b94d9-105">This error occurs when the build tools can't find the version of the .NET SDK that's needed to build a project.</span></span> <span data-ttu-id="b94d9-106">Esto se suele deber a un problema de instalación o configuración del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b94d9-106">This is typically due to a .NET Core SDK installation or configuration issue.</span></span> <span data-ttu-id="b94d9-107">El mensaje de error es similar al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b94d9-107">The full error message is similar to the following example:</span></span>

> <span data-ttu-id="b94d9-108">NETSDK1045: El SDK de .NET actual no es compatible con "versión más reciente" como destino.</span><span class="sxs-lookup"><span data-stu-id="b94d9-108">NETSDK1045: The current .NET SDK does not support 'newer version' as a target.</span></span> <span data-ttu-id="b94d9-109">Seleccione "versión anterior" u otra inferior como destino, o bien use una versión del SDK de .NET que admita "versión más reciente".</span><span class="sxs-lookup"><span data-stu-id="b94d9-109">Either target 'older version' or lower, or use a .NET SDK version that supports 'newer version'.</span></span>

<span data-ttu-id="b94d9-110">En las secciones siguientes se describen algunas de las posibles razones de este error.</span><span class="sxs-lookup"><span data-stu-id="b94d9-110">The following sections describe some of the possible reasons for this error.</span></span> <span data-ttu-id="b94d9-111">Compruebe cada una de ellas y vea cuál es la correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b94d9-111">Check each one and see which one applies to you.</span></span> <span data-ttu-id="b94d9-112">Tenga en cuenta que, al realizar cambios en el entorno o en los archivos de configuración, es posible que tenga que reiniciar ventanas de comandos, Visual Studio o la máquina para que los cambios surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="b94d9-112">Keep in mind that when making changes to the environment or the configuration files, you might have to restart command windows, restart Visual Studio, or reboot your machine, for your changes to take effect.</span></span>

## <a name="net-sdk-version"></a><span data-ttu-id="b94d9-113">Versión de SDK de .NET</span><span class="sxs-lookup"><span data-stu-id="b94d9-113">.NET SDK version</span></span>

<span data-ttu-id="b94d9-114">Abra el archivo del proyecto (.csproj, .vbproj o .fsproj) y compruebe la plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="b94d9-114">Open the project file (.csproj, .vbproj, or .fsproj) and check the target framework.</span></span> <span data-ttu-id="b94d9-115">Esta es la versión de la plataforma que la aplicación intenta usar.</span><span class="sxs-lookup"><span data-stu-id="b94d9-115">This is the version of the framework that your app is trying to use.</span></span>

```xml
<TargetFramework>netcoreapp3.0</TargetFramework>
```

<span data-ttu-id="b94d9-116">Asegúrese de que la versión de .NET que aparece en la lista está instalada en la máquina.</span><span class="sxs-lookup"><span data-stu-id="b94d9-116">Make sure that the version of .NET listed is installed on the machine.</span></span> <span data-ttu-id="b94d9-117">Puede enumerar las versiones instaladas con el comando siguiente (abra un Símbolo del sistema para desarrolladores y ejecútelo):</span><span class="sxs-lookup"><span data-stu-id="b94d9-117">You can list the installed versions by using the following command (open a Developer Command Prompt and run this command):</span></span>

```dotnetcli
dotnet --list-sdks
```

### <a name="x86-or-x64-architecture"></a><span data-ttu-id="b94d9-118">Arquitectura x86 o x64</span><span class="sxs-lookup"><span data-stu-id="b94d9-118">x86 or x64 architecture</span></span>

<span data-ttu-id="b94d9-119">Cada versión del SDK de .NET está disponible en la arquitectura x86 y x64.</span><span class="sxs-lookup"><span data-stu-id="b94d9-119">Each version of the .NET SDK is available in both x86 and x64 architecture.</span></span> <span data-ttu-id="b94d9-120">Es posible que el proyecto intente encontrar el SDK de .NET para la arquitectura equivocada, o bien que no esté instalado el SDK de .NET para la arquitectura que necesita el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b94d9-120">The project might be trying to find the .NET SDK for the wrong architecture, or the .NET SDK for the architecture your project needs might not be installed.</span></span> <span data-ttu-id="b94d9-121">Busque en las carpetas de instalación la arquitectura que necesita.</span><span class="sxs-lookup"><span data-stu-id="b94d9-121">Check the installation folders for the architecture you need.</span></span> <span data-ttu-id="b94d9-122">Por ejemplo, en Windows, la versión x86 del SDK de .NET se instala en *C:\Archivos de programa (x86)\dotnet*, y la versión x64, en *C:\Archivos de programa\dotnet*.</span><span class="sxs-lookup"><span data-stu-id="b94d9-122">For example, on Windows, the x86 version of the .NET SDK is installed in *C:\Program Files (x86)\dotnet* and the x64 version is installed in *C:\Program Files\dotnet*.</span></span> <span data-ttu-id="b94d9-123">Vea [Cómo comprobar que .NET Core ya está instalado](../../install/how-to-detect-installed-versions.md) y elija el sistema operativo para averiguar cómo detectar lo que está instalado en la máquina.</span><span class="sxs-lookup"><span data-stu-id="b94d9-123">See [How to check that .NET is already installed](../../install/how-to-detect-installed-versions.md) and choose your operating system to find out how to detect what's installed on your machine.</span></span>

<span data-ttu-id="b94d9-124">Si la versión que necesita no está instalada, descárguela [aquí](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="b94d9-124">If the version you need is not installed, download it from [here](https://dotnet.microsoft.com/download/dotnet-core).</span></span>

## <a name="preview-not-enabled"></a><span data-ttu-id="b94d9-125">Versión preliminar no habilitada</span><span class="sxs-lookup"><span data-stu-id="b94d9-125">Preview not enabled</span></span>

<span data-ttu-id="b94d9-126">Si tiene instalada una versión preliminar de la versión del SDK de .NET solicitada, también debe establecer la opción para habilitar las versiones preliminares en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b94d9-126">If you have a preview installed of the requested .NET SDK version, you also need to set the option to enable previews in Visual Studio.</span></span> <span data-ttu-id="b94d9-127">Vaya a **Herramientas** > **Opciones** > **Entorno** > **Características en versión preliminar** y asegúrese de que la opción **Usar versiones preliminares del SDK de .NET Core** está activada.</span><span class="sxs-lookup"><span data-stu-id="b94d9-127">Go to **Tools** > **Options** > **Environment** > **Preview Features**, and make sure that **Use previews of the .NET Core SDK** is checked.</span></span>

## <a name="visual-studio-version"></a><span data-ttu-id="b94d9-128">Versión de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b94d9-128">Visual Studio version</span></span>

<span data-ttu-id="b94d9-129">Por ejemplo, en .NET Core 3.0 y versiones posteriores se necesita Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="b94d9-129">For example, .NET Core 3.0 and later require Visual Studio 2019.</span></span> <span data-ttu-id="b94d9-130">Actualice su versión a [Visual Studio 2019, versión 16.3](https://visualstudio.microsoft.com/downloads) o posterior para compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b94d9-130">Upgrade to [Visual Studio 2019 version 16.3](https://visualstudio.microsoft.com/downloads) or later to build your project.</span></span>

## <a name="path-environment-variable"></a><span data-ttu-id="b94d9-131">Variable de entorno PATH</span><span class="sxs-lookup"><span data-stu-id="b94d9-131">PATH environment variable</span></span>

<span data-ttu-id="b94d9-132">Las herramientas de compilación usan la variable de entorno PATH para encontrar la versión correcta de las herramientas de compilación de .NET.</span><span class="sxs-lookup"><span data-stu-id="b94d9-132">The build tools use the PATH environment variable to find the right version of the .NET build tools.</span></span> <span data-ttu-id="b94d9-133">Si la variable de entorno PATH contiene rutas de acceso directas a herramientas de compilación más antiguas, podría aparecer este mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="b94d9-133">If the PATH environment variable contains direct paths to older build tools, this error message could appear.</span></span> <span data-ttu-id="b94d9-134">Asegúrese de que la única ruta de acceso a las herramientas de .NET en la variable de entorno PATH es a la carpeta *dotnet* de nivel superior, por ejemplo, *C:\Archivos de programa\dotnet*.</span><span class="sxs-lookup"><span data-stu-id="b94d9-134">Make sure the only path to the .NET tools in the PATH environment variable is to the top-level *dotnet* folder, for example, *C:\Program Files\dotnet*.</span></span> <span data-ttu-id="b94d9-135">Un ejemplo de una ruta de acceso incorrecta sería similar a *C:\Archivos de programa\dotnet\2.1.0\sdks*.</span><span class="sxs-lookup"><span data-stu-id="b94d9-135">An example of an incorrect PATH would be something like *C:\Program Files\dotnet\2.1.0\sdks*.</span></span>

## <a name="msbuildsdkpath-environment-variable"></a><span data-ttu-id="b94d9-136">Variable de entorno MSBuildSDKPath</span><span class="sxs-lookup"><span data-stu-id="b94d9-136">MSBuildSDKPath environment variable</span></span>

<span data-ttu-id="b94d9-137">Compruebe la variable de entorno MSBuildSDKPath.</span><span class="sxs-lookup"><span data-stu-id="b94d9-137">Check the MSBuildSDKPath environment variable.</span></span> <span data-ttu-id="b94d9-138">MSBuild reconoce esta variable de entorno opcional y, si se establece, invalida el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b94d9-138">This optional environment variable is recognized by MSBuild and if set, overrides the default value.</span></span> <span data-ttu-id="b94d9-139">Es posible que esté establecida en una versión anterior específica del SDK de .NET.</span><span class="sxs-lookup"><span data-stu-id="b94d9-139">It might be set to a specific older version of the .NET SDK.</span></span> <span data-ttu-id="b94d9-140">Si está establecida, intente eliminarla y vuelva a compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b94d9-140">If it's set, try deleting it and rebuilding your project.</span></span>

## <a name="globaljson-file"></a><span data-ttu-id="b94d9-141">archivo global.json</span><span class="sxs-lookup"><span data-stu-id="b94d9-141">global.json file</span></span>

<span data-ttu-id="b94d9-142">Busque un archivo *global.json* en la carpeta raíz del proyecto y en la cadena de directorios de la raíz del volumen, ya que puede estar en cualquier parte de la estructura de carpetas.</span><span class="sxs-lookup"><span data-stu-id="b94d9-142">Check for a *global.json* file in the root folder in your project and up the directory chain to the root of the volume, since it can be anywhere in the folder structure.</span></span> <span data-ttu-id="b94d9-143">Si contiene una versión del SDK, elimine el nodo `sdk` y todos sus elementos secundarios, o bien actualícelo a la versión más reciente de .NET Core deseada.</span><span class="sxs-lookup"><span data-stu-id="b94d9-143">If it contains an SDK version, delete the `sdk` node and all its children, or update it to the desired newer .NET Core version.</span></span>

```json
{
  "sdk": {
    "version": "2.1.0"
  }
}
```

<span data-ttu-id="b94d9-144">El archivo *global.json* no es necesario, por lo que, si no contiene nada que no sea el nodo `sdk`, puede eliminarlo por completo.</span><span class="sxs-lookup"><span data-stu-id="b94d9-144">The *global.json* file is not required, so if it doesn't contain anything other than the `sdk` node, you can delete the whole file.</span></span>

## <a name="directorybuildprops-file"></a><span data-ttu-id="b94d9-145">Archivo Directory.build.props</span><span class="sxs-lookup"><span data-stu-id="b94d9-145">Directory.build.props file</span></span>

<span data-ttu-id="b94d9-146">*Directory.build.props* es un archivo de MSBuild opcional que puede establecer propiedades globales.</span><span class="sxs-lookup"><span data-stu-id="b94d9-146">The *Directory.build.props* file is an optional MSBuild file that can set global properties.</span></span> <span data-ttu-id="b94d9-147">Busque estos archivos en la carpeta de la solución y en la cadena de directorios de la raíz del volumen, ya que pueden estar en cualquier parte de la estructura de carpetas.</span><span class="sxs-lookup"><span data-stu-id="b94d9-147">Check for these files in the solution folder and up the directory chain to the root of the volume, since they can be anywhere in the folder structure.</span></span> <span data-ttu-id="b94d9-148">Busque elementos `TargetFramework` o la configuración de `MSBuildSDKPath` que puede invalidar la configuración deseada.</span><span class="sxs-lookup"><span data-stu-id="b94d9-148">Look for `TargetFramework` elements, or settings of `MSBuildSDKPath` that could override your desired settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="b94d9-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="b94d9-149">See also</span></span>

- [<span data-ttu-id="b94d9-150">El SDK de .NET actual no admite seleccionar como destino .NET Core 3.0: corrección</span><span class="sxs-lookup"><span data-stu-id="b94d9-150">The Current .NET SDK does not support targeting .NET Core 3.0 – Fix</span></span>](https://www.ryadel.com/current-net-sdk-not-support-net-core-3-0-fix/)
