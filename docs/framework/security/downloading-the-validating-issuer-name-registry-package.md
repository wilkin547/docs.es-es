---
title: "Descargar el paquete de validación del Registro de nombres de emisores"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ff8b0014-c5d4-4614-90f0-13fcc0ba777a
caps.latest.revision: "3"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9bf6869de939ed7eda7cd3de868e712126f71751
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="downloading-the-validating-issuer-name-registry-package"></a><span data-ttu-id="3c964-102">Descargar el paquete de validación del Registro de nombres de emisores</span><span class="sxs-lookup"><span data-stu-id="3c964-102">Downloading the Validating Issuer Name Registry Package</span></span>
<span data-ttu-id="3c964-103">En este tema se explica cómo descargar y usar el Registro de nombres del emisor que valida (VINR) en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c964-103">This topic discusses how to download and use the Validating Issuer Name Registry (VINR) in your project.</span></span>  
  
## <a name="downloading-the-validating-issuer-name-registry"></a><span data-ttu-id="3c964-104">Descargar el Registro de nombres del emisor que valida</span><span class="sxs-lookup"><span data-stu-id="3c964-104">Downloading the Validating Issuer Name Registry</span></span>  
 <span data-ttu-id="3c964-105">El VINR está disponible como un paquete NuGet, que agrega las referencias y los ensamblados necesarios al proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c964-105">The VINR is available as a NuGet package, which adds the necessary assemblies and references to your project.</span></span> <span data-ttu-id="3c964-106">Si aún no tiene NuGet instalado, vaya a [nuget.org](http://nuget.org) para instalarlo.</span><span class="sxs-lookup"><span data-stu-id="3c964-106">If you do not already have NuGet installed, go to [nuget.org](http://nuget.org) to install it.</span></span> <span data-ttu-id="3c964-107">Puede ver el historial de creación de versiones para la extensión si visita su página en NuGet: [Registro de Microsoft del nombre del emisor que valida en NuGet](https://nuget.org/packages/System.IdentityModel.Tokens.ValidatingIssuerNameRegistry/).</span><span class="sxs-lookup"><span data-stu-id="3c964-107">You can see the versioning history for the extension by visiting its page on NuGet: [Microsoft Validating Issuer Name Registry on NuGet](https://nuget.org/packages/System.IdentityModel.Tokens.ValidatingIssuerNameRegistry/)</span></span>  
  
#### <a name="downloading-the-validating-issuer-name-registry-by-using-the-package-manager-gui"></a><span data-ttu-id="3c964-108">Descargar el Registro de nombres del emisor que valida mediante la GUI del Administrador de paquetes</span><span class="sxs-lookup"><span data-stu-id="3c964-108">Downloading the Validating Issuer Name Registry by using the Package Manager GUI</span></span>  
  
1.  <span data-ttu-id="3c964-109">En Visual Studio, haga clic con el botón derecho en el proyecto en el **Explorador de soluciones** y, después, seleccione **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="3c964-109">In Visual Studio, right-click your project in **Solution Explorer**, and then select **Manage NuGet Packages**.</span></span>  
  
2.  <span data-ttu-id="3c964-110">En la ventana **Administrar paquetes NuGet**, haga clic en el cuadro de búsqueda, escriba `ValidatingIssuerNameRegistry` y presione **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="3c964-110">In the **Manage NuGet Packages** window, click the search box and enter `ValidatingIssuerNameRegistry` and press **Enter**.</span></span>  
  
3.  <span data-ttu-id="3c964-111">En el panel de resultados, haga clic en el botón **Instalar** del primer resultado.</span><span class="sxs-lookup"><span data-stu-id="3c964-111">From the results pane, click the **Install** button for the first result.</span></span>  
  
4.  <span data-ttu-id="3c964-112">El paquete comenzará la descarga.</span><span class="sxs-lookup"><span data-stu-id="3c964-112">The package will begin downloading.</span></span> <span data-ttu-id="3c964-113">Antes de agregarlo al proyecto, aparecerá el diálogo de aceptación de licencia.</span><span class="sxs-lookup"><span data-stu-id="3c964-113">Before it is added to your project, the License Acceptance dialog will appear.</span></span> <span data-ttu-id="3c964-114">Si acepta los términos de licencia, haga clic en **Acepto**.</span><span class="sxs-lookup"><span data-stu-id="3c964-114">If you agree to the license terms, click **I Accept**.</span></span>  
  
5.  <span data-ttu-id="3c964-115">Los últimos ensamblados VINR se descargarán y agregarán al proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c964-115">The latest VINR assemblies will be downloaded and added to your project.</span></span>  
  
#### <a name="downloading-the-validating-issuer-name-registry-by-using-the-package-manager-console"></a><span data-ttu-id="3c964-116">Descargar el Registro de nombres del emisor que valida mediante la Consola del Administrador de paquetes</span><span class="sxs-lookup"><span data-stu-id="3c964-116">Downloading the Validating Issuer Name Registry by using the Package Manager Console</span></span>  
  
1.  <span data-ttu-id="3c964-117">En Visual Studio, haga clic en **Herramientas**, **Administrador de paquetes de biblioteca** y, después, **Consola del Administrador de paquetes**.</span><span class="sxs-lookup"><span data-stu-id="3c964-117">In Visual Studio, click **Tools**, **Library Package Manager**, and then **Package Manager Console**.</span></span>  
  
2.  <span data-ttu-id="3c964-118">Aparece la **Consola del Administrador de paquetes**.</span><span class="sxs-lookup"><span data-stu-id="3c964-118">The **Package Manager Console** appears.</span></span> <span data-ttu-id="3c964-119">Escriba el texto siguiente y presione **Entrar**:</span><span class="sxs-lookup"><span data-stu-id="3c964-119">Enter the following text and press **Enter**:</span></span>  
  
    ```powershell  
    Install-Package System.IdentityModel.Tokens.ValidatingIssuerNameRegistry  
    ```  
  
3.  <span data-ttu-id="3c964-120">Los últimos ensamblados VINR se descargarán y agregarán al proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c964-120">The latest VINR assemblies will be downloaded and added to your project.</span></span>
