---
title: Instalación de F#
description: Obtenga información sobre cómo F# instalar en función de su entorno.
ms.date: 09/05/2019
ms.openlocfilehash: dffa30eac0bdb59c85a66dca6cafd62b25daa572
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855803"
---
# <a name="install-f"></a><span data-ttu-id="ed84f-103">Instalar F\#</span><span class="sxs-lookup"><span data-stu-id="ed84f-103">Install F\#</span></span>

<span data-ttu-id="ed84f-104">Puede instalar F# de varias maneras, en función de su entorno.</span><span class="sxs-lookup"><span data-stu-id="ed84f-104">You can install F# in multiple ways, depending on your environment.</span></span>

## <a name="install-f-with-visual-studio"></a><span data-ttu-id="ed84f-105">Instalación F# con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ed84f-105">Install F# with Visual Studio</span></span>

<span data-ttu-id="ed84f-106">Si está descargando [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) por primera vez, primero instalará el instalador de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ed84f-106">If you're downloading [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) for the first time, it will first install the Visual Studio installer.</span></span> <span data-ttu-id="ed84f-107">Instale la SKU adecuada de Visual Studio desde el instalador.</span><span class="sxs-lookup"><span data-stu-id="ed84f-107">Install the appropriate SKU of Visual Studio from the installer.</span></span> <span data-ttu-id="ed84f-108">Si ya lo tiene instalado, haga clic en **modificar**.</span><span class="sxs-lookup"><span data-stu-id="ed84f-108">If you already have it installed, click **Modify**.</span></span>

<span data-ttu-id="ed84f-109">A continuación verá una lista de cargas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ed84f-109">You'll next see a list of Workloads.</span></span> <span data-ttu-id="ed84f-110">Seleccione **ASP.net y desarrollo web** , que instalarán F# compatibilidad con y .net Core para proyectos de ASP.net Core.</span><span class="sxs-lookup"><span data-stu-id="ed84f-110">Select **ASP.NET and web development** which will install F# support and .NET Core support for ASP.NET Core projects.</span></span>

<span data-ttu-id="ed84f-111">A continuación, haga clic en **modificar** en la parte inferior derecha.</span><span class="sxs-lookup"><span data-stu-id="ed84f-111">Next, click **Modify** in the lower right-hand side.</span></span>  <span data-ttu-id="ed84f-112">Se instalará todo lo que haya seleccionado.</span><span class="sxs-lookup"><span data-stu-id="ed84f-112">This will install everything you have selected.</span></span> <span data-ttu-id="ed84f-113">Después, puede abrir Visual Studio 2017 con F# compatibilidad con idiomas haciendo clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="ed84f-113">You can then open Visual Studio 2017 with F# language support by clicking **Launch**.</span></span>

## <a name="install-f-with-visual-studio-for-mac"></a><span data-ttu-id="ed84f-114">Instalación F# con Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="ed84f-114">Install F# with Visual Studio for Mac</span></span>

<span data-ttu-id="ed84f-115">F#se instala de forma predeterminada en [Visual Studio para Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), independientemente de la configuración que elija.</span><span class="sxs-lookup"><span data-stu-id="ed84f-115">F# is installed by default in [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), no matter which configuration you choose.</span></span>

<span data-ttu-id="ed84f-116">Una vez finalizada la instalación, elija "iniciar Visual Studio".</span><span class="sxs-lookup"><span data-stu-id="ed84f-116">After the install completes, choose "Start Visual Studio".</span></span> <span data-ttu-id="ed84f-117">También puede iniciarlo a través de Finder en macOS.</span><span class="sxs-lookup"><span data-stu-id="ed84f-117">You can also launch it through Finder on macOS.</span></span>

## <a name="install-f-with-visual-studio-code"></a><span data-ttu-id="ed84f-118">Instalación F# con Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="ed84f-118">Install F# with Visual Studio Code</span></span>

<span data-ttu-id="ed84f-119">Debe tener [git instalado](https://git-scm.com/download) y disponible en su ruta de acceso para hacer uso de las plantillas de proyecto.</span><span class="sxs-lookup"><span data-stu-id="ed84f-119">You must have [git installed](https://git-scm.com/download) and available on your PATH to make use of project templates.</span></span> <span data-ttu-id="ed84f-120">Para comprobar que se ha instalado correctamente, escriba `git --version` en un símbolo del sistema y presione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="ed84f-120">You can verify that it is installed correctly by typing `git --version` at a command prompt and pressing **Enter**.</span></span>

### <a name="macostabmacos"></a>[<span data-ttu-id="ed84f-121">macOS</span><span class="sxs-lookup"><span data-stu-id="ed84f-121">macOS</span></span>](#tab/macos)

<span data-ttu-id="ed84f-122">[Mono](https://www.mono-project.com) se usa para [ F# ](../tutorials/fsharp-interactive/index.md) el soporte interactivo.</span><span class="sxs-lookup"><span data-stu-id="ed84f-122">[Mono](https://www.mono-project.com) is used for [F# Interactive](../tutorials/fsharp-interactive/index.md) support.</span></span> <span data-ttu-id="ed84f-123">La forma más fácil de instalar mono en macOS es a través de homebrew.</span><span class="sxs-lookup"><span data-stu-id="ed84f-123">The easiest way to install Mono on macOS is via Homebrew.</span></span> <span data-ttu-id="ed84f-124">Simplemente escriba lo siguiente en el terminal:</span><span class="sxs-lookup"><span data-stu-id="ed84f-124">Simply type the following into your terminal:</span></span>

```console
brew install mono
```

<span data-ttu-id="ed84f-125">Instale también el [SDK de .net Core](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="ed84f-125">Also install the [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>

### <a name="linuxtablinux"></a>[<span data-ttu-id="ed84f-126">Linux</span><span class="sxs-lookup"><span data-stu-id="ed84f-126">Linux</span></span>](#tab/linux)

<span data-ttu-id="ed84f-127">[Mono](https://www.mono-project.com) se usa para [ F# ](../tutorials/fsharp-interactive/index.md) el soporte interactivo.</span><span class="sxs-lookup"><span data-stu-id="ed84f-127">[Mono](https://www.mono-project.com) is used for [F# Interactive](../tutorials/fsharp-interactive/index.md) support.</span></span> <span data-ttu-id="ed84f-128">Si se encuentra en Debian o Ubuntu, puede utilizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ed84f-128">If you're on Debian or Ubuntu, you can use the following:</span></span>

```console
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

<span data-ttu-id="ed84f-129">Instale también el [SDK de .net Core](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="ed84f-129">Also install the [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>

### <a name="windowstabwindows"></a>[<span data-ttu-id="ed84f-130">Windows</span><span class="sxs-lookup"><span data-stu-id="ed84f-130">Windows</span></span>](#tab/windows)

<span data-ttu-id="ed84f-131">Instale [Visual Studio con F# compatibilidad](#install-f-with-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="ed84f-131">Install [Visual Studio with F# support](#install-f-with-visual-studio).</span></span> <span data-ttu-id="ed84f-132">Esto instala todos los componentes necesarios para escribir, compilar y ejecutar F# código.</span><span class="sxs-lookup"><span data-stu-id="ed84f-132">This installs all the necessary components to write, compile, and execute F# code.</span></span>

<span data-ttu-id="ed84f-133">Instale también el [SDK de .net Core](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="ed84f-133">Also install the [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>

---

<span data-ttu-id="ed84f-134">A continuación, necesitará [Visual Studio Code](https://code.visualstudio.com) instalado.</span><span class="sxs-lookup"><span data-stu-id="ed84f-134">You will then need [Visual Studio Code](https://code.visualstudio.com) installed.</span></span>

<span data-ttu-id="ed84f-135">A continuación, haga clic en el icono de extensiones y busque "Ionide":</span><span class="sxs-lookup"><span data-stu-id="ed84f-135">Next, click the Extensions icon and search for "Ionide":</span></span>

<span data-ttu-id="ed84f-136">El único complemento necesario para F# la compatibilidad en Visual Studio Code es [Ionide-FSharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span><span class="sxs-lookup"><span data-stu-id="ed84f-136">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="ed84f-137">Sin embargo, también puede instalar [Ionide-falsificación](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) para obtener compatibilidad [falsa](https://fsharp.github.io/FAKE/) y [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) para obtener soporte técnico de [Paket](https://fsprojects.github.io/Paket/) .</span><span class="sxs-lookup"><span data-stu-id="ed84f-137">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fsharp.github.io/FAKE/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="ed84f-138">FALSAS y Paket son herramientas F# de la comunidad adicionales para la creación de proyectos y la administración de dependencias, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="ed84f-138">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>

## <a name="install-f-on-a-build-server"></a><span data-ttu-id="ed84f-139">Instalar F# en un servidor de compilación</span><span class="sxs-lookup"><span data-stu-id="ed84f-139">Install F# on a Build Server</span></span>

<span data-ttu-id="ed84f-140">Si usa .NET Core o .NET Framework a través del SDK de .NET, solo tiene que instalar el SDK de .NET en el servidor de compilación.</span><span class="sxs-lookup"><span data-stu-id="ed84f-140">If you are using .NET Core or .NET Framework via the .NET SDK, you simply need to install the .NET SDK on your build server.</span></span> <span data-ttu-id="ed84f-141">Tiene todo lo que necesita.</span><span class="sxs-lookup"><span data-stu-id="ed84f-141">It has everything you need.</span></span>

<span data-ttu-id="ed84f-142">Si usa .NET Framework y **no** usa el SDK de .net, tendrá que instalar la [SKU de Visual Studio build tools](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) en el servidor de Windows.</span><span class="sxs-lookup"><span data-stu-id="ed84f-142">If you are using .NET Framework and you are **not** using the .NET SDK, then you will need to install the [Visual Studio Build Tools SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) onto your Windows Server.</span></span> <span data-ttu-id="ed84f-143">En el instalador, seleccione **herramientas de compilación de escritorio de .net** y, a continuación, seleccione el  **F# componente del compilador** en el lado derecho del menú del instalador.</span><span class="sxs-lookup"><span data-stu-id="ed84f-143">In the installer, select **.NET desktop build tools** and then select the **F# compiler** component on the right side of the installer menu.</span></span>
