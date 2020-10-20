---
title: Instalación de F#
description: 'Obtenga información sobre cómo instalar F # de varias maneras diferentes.'
ms.date: 12/20/2019
ms.openlocfilehash: 302e04f7cf3271516dff88d9d5f18f620b6ede80
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2020
ms.locfileid: "92224287"
---
# <a name="install-f"></a><span data-ttu-id="85946-103">Instalar F\#</span><span class="sxs-lookup"><span data-stu-id="85946-103">Install F\#</span></span>

<span data-ttu-id="85946-104">Puede instalar F # de varias maneras, en función de su entorno.</span><span class="sxs-lookup"><span data-stu-id="85946-104">You can install F# in multiple ways, depending on your environment.</span></span>

## <a name="install-f-with-visual-studio"></a><span data-ttu-id="85946-105">Instalación de F # con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="85946-105">Install F# with Visual Studio</span></span>

1. <span data-ttu-id="85946-106">Si está descargando [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) por primera vez, primero instalará instalador de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="85946-106">If you're downloading [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) for the first time, it will first install Visual Studio Installer.</span></span> <span data-ttu-id="85946-107">Instale la edición adecuada de Visual Studio desde el instalador.</span><span class="sxs-lookup"><span data-stu-id="85946-107">Install the appropriate edition of Visual Studio from the installer.</span></span>

   <span data-ttu-id="85946-108">Si ya tiene instalado Visual Studio, elija **modificar** junto a la edición a la que desea agregar F #.</span><span class="sxs-lookup"><span data-stu-id="85946-108">If you already have Visual Studio installed, choose **Modify** next to the edition you want to add F# to.</span></span>

2. <span data-ttu-id="85946-109">En la página cargas de trabajo, seleccione la carga de trabajo **desarrollo de ASP.net y Web** , que incluye compatibilidad con F # y .net Core para proyectos de ASP.net Core.</span><span class="sxs-lookup"><span data-stu-id="85946-109">On the Workloads page, select the **ASP.NET and web development** workload, which includes F# and .NET Core support for ASP.NET Core projects.</span></span>

3. <span data-ttu-id="85946-110">Elija **modificar** en la esquina inferior derecha para instalar todo lo que ha seleccionado.</span><span class="sxs-lookup"><span data-stu-id="85946-110">Choose **Modify** in the lower right-hand corner to install everything you've selected.</span></span>

   <span data-ttu-id="85946-111">Después, puede abrir Visual Studio con F # eligiendo **iniciar** en instalador de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="85946-111">You can then open Visual Studio with F# by choosing **Launch** in Visual Studio Installer.</span></span>

## <a name="install-f-with-visual-studio-code"></a><span data-ttu-id="85946-112">Instalar F # con Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="85946-112">Install F# with Visual Studio Code</span></span>

1. <span data-ttu-id="85946-113">Asegúrese de que tiene [git](https://git-scm.com/download) instalado y disponible en su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="85946-113">Ensure you have [git](https://git-scm.com/download) installed and available on your PATH.</span></span> <span data-ttu-id="85946-114">Para comprobar que se ha instalado correctamente, escriba `git --version` en un símbolo del sistema y presione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="85946-114">You can verify that it's installed correctly by entering `git --version` at a command prompt and pressing **Enter**.</span></span>

2. <span data-ttu-id="85946-115">Instale el [SDK de .net Core](https://dotnet.microsoft.com/download) y [Visual Studio Code](https://code.visualstudio.com).</span><span class="sxs-lookup"><span data-stu-id="85946-115">Install the [.NET Core SDK](https://dotnet.microsoft.com/download) and [Visual Studio Code](https://code.visualstudio.com).</span></span>

3. <span data-ttu-id="85946-116">Seleccione el icono de extensiones y busque "Ionide":</span><span class="sxs-lookup"><span data-stu-id="85946-116">Select the Extensions icon and search for "Ionide":</span></span>

   <span data-ttu-id="85946-117">El único complemento necesario para la compatibilidad con F # en Visual Studio Code es [Ionide-FSharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span><span class="sxs-lookup"><span data-stu-id="85946-117">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="85946-118">Sin embargo, también puede instalar [Ionide-falsificación](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) para obtener compatibilidad [falsa](https://fake.build/) y [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) para obtener soporte técnico de [Paket](https://fsprojects.github.io/Paket/) .</span><span class="sxs-lookup"><span data-stu-id="85946-118">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fake.build/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="85946-119">FALSAS y Paket son herramientas de la comunidad de F # adicionales para compilar proyectos y administrar dependencias, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="85946-119">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>

## <a name="install-f-with-visual-studio-for-mac"></a><span data-ttu-id="85946-120">Instalar F # con Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="85946-120">Install F# with Visual Studio for Mac</span></span>

<span data-ttu-id="85946-121">F # está instalado de forma predeterminada en [Visual Studio para Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), independientemente de la configuración que elija.</span><span class="sxs-lookup"><span data-stu-id="85946-121">F# is installed by default in [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), no matter which configuration you choose.</span></span>

<span data-ttu-id="85946-122">Una vez finalizada la instalación, elija **iniciar Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="85946-122">After the install completes, choose **Start Visual Studio**.</span></span> <span data-ttu-id="85946-123">También puede abrir Visual Studio a través de Finder en macOS.</span><span class="sxs-lookup"><span data-stu-id="85946-123">You can also open Visual Studio through Finder on macOS.</span></span>

## <a name="install-f-on-a-build-server"></a><span data-ttu-id="85946-124">Instalar F # en un servidor de compilación</span><span class="sxs-lookup"><span data-stu-id="85946-124">Install F# on a build server</span></span>

<span data-ttu-id="85946-125">Si usa .NET Core o .NET Framework a través del SDK de .NET, solo tiene que instalar el SDK de .NET en el servidor de compilación.</span><span class="sxs-lookup"><span data-stu-id="85946-125">If you're using .NET Core or .NET Framework via the .NET SDK, you simply need to install the .NET SDK on your build server.</span></span> <span data-ttu-id="85946-126">Tiene todo lo que necesita.</span><span class="sxs-lookup"><span data-stu-id="85946-126">It has everything you need.</span></span>

<span data-ttu-id="85946-127">Si usa .NET Framework y **no** usa el SDK de .net, deberá instalar la [SKU de Visual Studio build tools](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) en el servidor de Windows.</span><span class="sxs-lookup"><span data-stu-id="85946-127">If you're using .NET Framework and you are **not** using the .NET SDK, then you'll need to install the [Visual Studio Build Tools SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) onto your Windows Server.</span></span> <span data-ttu-id="85946-128">En el instalador, seleccione **herramientas de compilación de escritorio de .net**y, a continuación, seleccione el componente de **compilador de F #** en el lado derecho del menú del instalador.</span><span class="sxs-lookup"><span data-stu-id="85946-128">In the installer, select **.NET desktop build tools**, and then select the **F# compiler** component on the right-hand side of the installer menu.</span></span>
