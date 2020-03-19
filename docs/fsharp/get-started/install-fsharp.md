---
title: Instalación de F#
description: Obtenga información sobre cómo instalar F de varias maneras diferentes.
ms.date: 12/20/2019
ms.openlocfilehash: 302e04f7cf3271516dff88d9d5f18f620b6ede80
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401098"
---
# <a name="install-f"></a><span data-ttu-id="b8ed6-103">Instalar F\#</span><span class="sxs-lookup"><span data-stu-id="b8ed6-103">Install F\#</span></span>

<span data-ttu-id="b8ed6-104">Puede instalar F de varias maneras, dependiendo de su entorno.</span><span class="sxs-lookup"><span data-stu-id="b8ed6-104">You can install F# in multiple ways, depending on your environment.</span></span>

## <a name="install-f-with-visual-studio"></a><span data-ttu-id="b8ed6-105">Instalar F con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b8ed6-105">Install F# with Visual Studio</span></span>

1. <span data-ttu-id="b8ed6-106">Si va a descargar [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) por primera vez, primero instalará Visual Studio Installer.</span><span class="sxs-lookup"><span data-stu-id="b8ed6-106">If you're downloading [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) for the first time, it will first install Visual Studio Installer.</span></span> <span data-ttu-id="b8ed6-107">Instale la edición adecuada de Visual Studio desde el instalador.</span><span class="sxs-lookup"><span data-stu-id="b8ed6-107">Install the appropriate edition of Visual Studio from the installer.</span></span>

   <span data-ttu-id="b8ed6-108">Si ya tiene visual de Visual Studio instalado, elija **Modificar** junto a la edición a la que desea agregar F.</span><span class="sxs-lookup"><span data-stu-id="b8ed6-108">If you already have Visual Studio installed, choose **Modify** next to the edition you want to add F# to.</span></span>

2. <span data-ttu-id="b8ed6-109">En la página Cargas de trabajo, seleccione la carga de **trabajo de desarrollo ASP.NET y web,** que incluye compatibilidad con F y .NET Core para proyectos de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="b8ed6-109">On the Workloads page, select the **ASP.NET and web development** workload, which includes F# and .NET Core support for ASP.NET Core projects.</span></span>

3. <span data-ttu-id="b8ed6-110">Elija **Modificar** en la esquina inferior derecha para instalar todo lo que ha seleccionado.</span><span class="sxs-lookup"><span data-stu-id="b8ed6-110">Choose **Modify** in the lower right-hand corner to install everything you've selected.</span></span>

   <span data-ttu-id="b8ed6-111">A continuación, puede abrir Visual Studio con F, elija **Iniciar** en el instalador de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b8ed6-111">You can then open Visual Studio with F# by choosing **Launch** in Visual Studio Installer.</span></span>

## <a name="install-f-with-visual-studio-code"></a><span data-ttu-id="b8ed6-112">Instalar F con Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="b8ed6-112">Install F# with Visual Studio Code</span></span>

1. <span data-ttu-id="b8ed6-113">Asegúrese de [que](https://git-scm.com/download) git está instalado y disponible en su PATH.</span><span class="sxs-lookup"><span data-stu-id="b8ed6-113">Ensure you have [git](https://git-scm.com/download) installed and available on your PATH.</span></span> <span data-ttu-id="b8ed6-114">Puede comprobar que está instalado correctamente `git --version` introduciendo en un símbolo del sistema y pulsando **Intro**.</span><span class="sxs-lookup"><span data-stu-id="b8ed6-114">You can verify that it's installed correctly by entering `git --version` at a command prompt and pressing **Enter**.</span></span>

2. <span data-ttu-id="b8ed6-115">Instale el SDK de [.NET Core](https://dotnet.microsoft.com/download) y Visual Studio [Code.](https://code.visualstudio.com)</span><span class="sxs-lookup"><span data-stu-id="b8ed6-115">Install the [.NET Core SDK](https://dotnet.microsoft.com/download) and [Visual Studio Code](https://code.visualstudio.com).</span></span>

3. <span data-ttu-id="b8ed6-116">Seleccione el icono Extensiones y busque "Ionide":</span><span class="sxs-lookup"><span data-stu-id="b8ed6-116">Select the Extensions icon and search for "Ionide":</span></span>

   <span data-ttu-id="b8ed6-117">El único complemento necesario para la compatibilidad con F en Visual Studio Code es [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span><span class="sxs-lookup"><span data-stu-id="b8ed6-117">The only plugin required for F# support in Visual Studio Code is [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).</span></span> <span data-ttu-id="b8ed6-118">Sin embargo, también puede instalar [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) para obtener soporte [FAKE](https://fake.build/) e [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) para obtener soporte [de Paket.](https://fsprojects.github.io/Paket/)</span><span class="sxs-lookup"><span data-stu-id="b8ed6-118">However, you can also install [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) to get [FAKE](https://fake.build/) support and [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) to get [Paket](https://fsprojects.github.io/Paket/) support.</span></span> <span data-ttu-id="b8ed6-119">FAKE y Paket son herramientas adicionales de la comunidad de F para crear proyectos y administrar dependencias, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="b8ed6-119">FAKE and Paket are additional F# community tools for building projects and managing dependencies, respectively.</span></span>

## <a name="install-f-with-visual-studio-for-mac"></a><span data-ttu-id="b8ed6-120">Instalar F con Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="b8ed6-120">Install F# with Visual Studio for Mac</span></span>

<span data-ttu-id="b8ed6-121">F se instala de forma predeterminada en [Visual Studio para Mac,](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)independientemente de la configuración que elija.</span><span class="sxs-lookup"><span data-stu-id="b8ed6-121">F# is installed by default in [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), no matter which configuration you choose.</span></span>

<span data-ttu-id="b8ed6-122">Una vez completada la instalación, elija **Iniciar Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="b8ed6-122">After the install completes, choose **Start Visual Studio**.</span></span> <span data-ttu-id="b8ed6-123">También puede abrir Visual Studio a través de Finder en macOS.</span><span class="sxs-lookup"><span data-stu-id="b8ed6-123">You can also open Visual Studio through Finder on macOS.</span></span>

## <a name="install-f-on-a-build-server"></a><span data-ttu-id="b8ed6-124">Instalar F en un servidor de compilación</span><span class="sxs-lookup"><span data-stu-id="b8ed6-124">Install F# on a build server</span></span>

<span data-ttu-id="b8ed6-125">Si usa .NET Core o .NET Framework a través del SDK de .NET, solo tiene que instalar el SDK de .NET en el servidor de compilación.</span><span class="sxs-lookup"><span data-stu-id="b8ed6-125">If you're using .NET Core or .NET Framework via the .NET SDK, you simply need to install the .NET SDK on your build server.</span></span> <span data-ttu-id="b8ed6-126">Tiene todo lo que necesitas.</span><span class="sxs-lookup"><span data-stu-id="b8ed6-126">It has everything you need.</span></span>

<span data-ttu-id="b8ed6-127">Si usa .NET Framework y **no** usa el SDK de .NET, deberá instalar la [SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) de Visual Studio Build Tools en Windows Server.</span><span class="sxs-lookup"><span data-stu-id="b8ed6-127">If you're using .NET Framework and you are **not** using the .NET SDK, then you'll need to install the [Visual Studio Build Tools SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) onto your Windows Server.</span></span> <span data-ttu-id="b8ed6-128">En el instalador, seleccione Herramientas de compilación de escritorio de **.NET**y, a continuación, seleccione el componente **del compilador** de F en el lado derecho del menú del instalador.</span><span class="sxs-lookup"><span data-stu-id="b8ed6-128">In the installer, select **.NET desktop build tools**, and then select the **F# compiler** component on the right-hand side of the installer menu.</span></span>
