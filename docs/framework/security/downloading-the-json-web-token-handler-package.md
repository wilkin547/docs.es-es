---
title: Descargar el paquete del controlador de token web de JSON
ms.date: 03/30/2017
ms.assetid: d12b3f5b-f1f1-4a9d-a159-0c13e5976c90
ms.openlocfilehash: 5a4846a5ec92324105f41b320d0d77f8749c28f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404682"
---
# <a name="downloading-the-json-web-token-handler-package"></a><span data-ttu-id="e245b-102">Descargar el paquete del controlador de token web de JSON</span><span class="sxs-lookup"><span data-stu-id="e245b-102">Downloading the JSON Web Token Handler Package</span></span>
<span data-ttu-id="e245b-103">En este tema se explica cómo descargar y usar el controlador de token web JSON en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e245b-103">This topic discusses how to download and use the JSON Web Token Handler in your project.</span></span>  
  
## <a name="downloading-the-json-web-token-handler"></a><span data-ttu-id="e245b-104">Descargar el controlador de token web de JSON</span><span class="sxs-lookup"><span data-stu-id="e245b-104">Downloading the JSON Web Token Handler</span></span>  
 <span data-ttu-id="e245b-105">La extensión del controlador de token web JSON está disponible como paquete NuGet, que agrega los ensamblados y referencias necesarios al proyecto.</span><span class="sxs-lookup"><span data-stu-id="e245b-105">The JSON Web Token Handler extension is available as a NuGet package, which adds the necessary assemblies and references to your project.</span></span> <span data-ttu-id="e245b-106">Si aún no tiene NuGet instalado, vaya a [nuget.org](http://nuget.org) para instalarlo.</span><span class="sxs-lookup"><span data-stu-id="e245b-106">If you do not already have NuGet installed, go to [nuget.org](http://nuget.org) to install it.</span></span> <span data-ttu-id="e245b-107">Puede ver el historial de creación de versiones para la extensión si visita su página en NuGet: [Controlador de token web JSON en NuGet](http://www.nuget.org/packages/System.IdentityModel.Tokens.Jwt/).</span><span class="sxs-lookup"><span data-stu-id="e245b-107">You can see the versioning history for the extension by visiting its page on NuGet: [JSON Web Token Handler on NuGet](http://www.nuget.org/packages/System.IdentityModel.Tokens.Jwt/)</span></span>  
  
#### <a name="downloading-the-json-web-token-handler-by-using-the-package-manager-gui"></a><span data-ttu-id="e245b-108">Descargar el controlador de token web JSON mediante la GUI del Administrador de paquetes</span><span class="sxs-lookup"><span data-stu-id="e245b-108">Downloading the JSON Web Token Handler by using the Package Manager GUI</span></span>  
  
1.  <span data-ttu-id="e245b-109">En Visual Studio, haga clic con el botón derecho en el proyecto en el **Explorador de soluciones** y, después, seleccione **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="e245b-109">In Visual Studio, right-click your project in **Solution Explorer**, and then select **Manage NuGet Packages**.</span></span>  
  
2.  <span data-ttu-id="e245b-110">En la ventana **Administrar paquetes NuGet**, haga clic en el cuadro de búsqueda, escriba `JWT Token Handler` y presione **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="e245b-110">In the **Manage NuGet Packages** window, click the search box and enter `JWT Token Handler` and press **Enter**.</span></span>  
  
3.  <span data-ttu-id="e245b-111">En el panel de resultados, haga clic en el botón **Instalar** del primer resultado.</span><span class="sxs-lookup"><span data-stu-id="e245b-111">From the results pane, click the **Install** button for the first result.</span></span>  
  
4.  <span data-ttu-id="e245b-112">El paquete comenzará la descarga.</span><span class="sxs-lookup"><span data-stu-id="e245b-112">The package will begin downloading.</span></span> <span data-ttu-id="e245b-113">Antes de agregarlo al proyecto, aparecerá el diálogo de aceptación de licencia.</span><span class="sxs-lookup"><span data-stu-id="e245b-113">Before it is added to your project, the License Acceptance dialog will appear.</span></span> <span data-ttu-id="e245b-114">Si acepta los términos de licencia, haga clic en **Acepto**.</span><span class="sxs-lookup"><span data-stu-id="e245b-114">If you agree to the license terms, click **I Accept**.</span></span>  
  
5.  <span data-ttu-id="e245b-115">Los últimos ensamblados de controlador de token web JSON se descargarán y agregarán al proyecto.</span><span class="sxs-lookup"><span data-stu-id="e245b-115">The latest JSON Web Token Handler assemblies will be downloaded and added to your project.</span></span>  
  
#### <a name="downloading-the-json-web-token-handler-by-using-the-package-manager-console"></a><span data-ttu-id="e245b-116">Descargar el controlador de token web JSON mediante la Consola del Administrador de paquetes</span><span class="sxs-lookup"><span data-stu-id="e245b-116">Downloading the JSON Web Token Handler by using the Package Manager Console</span></span>  
  
1.  <span data-ttu-id="e245b-117">En Visual Studio, haga clic en **Herramientas**, **Administrador de paquetes de biblioteca** y, después, **Consola del Administrador de paquetes**.</span><span class="sxs-lookup"><span data-stu-id="e245b-117">In Visual Studio, click **Tools**, **Library Package Manager**, and then **Package Manager Console**.</span></span>  
  
2.  <span data-ttu-id="e245b-118">Aparece la **Consola del Administrador de paquetes**.</span><span class="sxs-lookup"><span data-stu-id="e245b-118">The **Package Manager Console** appears.</span></span> <span data-ttu-id="e245b-119">Escriba el texto siguiente y presione **Entrar**:</span><span class="sxs-lookup"><span data-stu-id="e245b-119">Enter the following text and press **Enter**:</span></span>  
  
    ```powershell  
    Install-Package System.IdentityModel.Tokens.Jwt  
    ```  
  
3.  <span data-ttu-id="e245b-120">Los últimos ensamblados de controlador de token web JSON se descargarán y agregarán al proyecto.</span><span class="sxs-lookup"><span data-stu-id="e245b-120">The latest JSON Web Token Handler assemblies will be downloaded and added to your project.</span></span>
