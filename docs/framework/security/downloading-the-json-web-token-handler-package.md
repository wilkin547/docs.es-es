---
title: Descargar el paquete del controlador de token web de JSON
ms.date: 10/10/2018
ms.assetid: d12b3f5b-f1f1-4a9d-a159-0c13e5976c90
ms.openlocfilehash: 8f878d23afd76488de7da03f16f72cbfa43c17d7
ms.sourcegitcommit: d88024e6d6d8b242feae5f4007a709379355aa24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2018
ms.locfileid: "49316485"
---
# <a name="download-the-json-web-token-handler-package"></a><span data-ttu-id="d6f82-102">Descargue el paquete de controladores de Token Web JSON</span><span class="sxs-lookup"><span data-stu-id="d6f82-102">Download the JSON Web Token Handler Package</span></span>

<span data-ttu-id="d6f82-103">En este tema se explica cómo descargar y usar el controlador de token web JSON en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="d6f82-103">This topic discusses how to download and use the JSON Web Token Handler in your project.</span></span>

<span data-ttu-id="d6f82-104">La extensión del controlador de token web JSON está disponible como paquete NuGet, que agrega los ensamblados y referencias necesarios al proyecto.</span><span class="sxs-lookup"><span data-stu-id="d6f82-104">The JSON Web Token Handler extension is available as a NuGet package, which adds the necessary assemblies and references to your project.</span></span> <span data-ttu-id="d6f82-105">Si aún no tiene NuGet instalado, vaya a [nuget.org](https://nuget.org) para instalarlo.</span><span class="sxs-lookup"><span data-stu-id="d6f82-105">If you do not already have NuGet installed, go to [nuget.org](https://nuget.org) to install it.</span></span> <span data-ttu-id="d6f82-106">Puede ver el historial de creación de versiones para la extensión si visita su página en NuGet: [Controlador de token web JSON en NuGet](https://www.nuget.org/packages/System.IdentityModel.Tokens.Jwt/).</span><span class="sxs-lookup"><span data-stu-id="d6f82-106">You can see the versioning history for the extension by visiting its page on NuGet: [JSON Web Token Handler on NuGet](https://www.nuget.org/packages/System.IdentityModel.Tokens.Jwt/)</span></span>

## <a name="use-the-package-manager-gui"></a><span data-ttu-id="d6f82-107">Usar la GUI del Administrador de paquetes</span><span class="sxs-lookup"><span data-stu-id="d6f82-107">Use the Package Manager GUI</span></span>

1. <span data-ttu-id="d6f82-108">En Visual Studio, haga clic con el botón derecho en el proyecto en el **Explorador de soluciones** y, después, seleccione **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="d6f82-108">In Visual Studio, right-click your project in **Solution Explorer**, and then select **Manage NuGet Packages**.</span></span>

2. <span data-ttu-id="d6f82-109">En la ventana **Administrar paquetes NuGet**, haga clic en el cuadro de búsqueda, escriba `JWT Token Handler` y presione **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="d6f82-109">In the **Manage NuGet Packages** window, click the search box and enter `JWT Token Handler` and press **Enter**.</span></span>

3. <span data-ttu-id="d6f82-110">En el panel de resultados, haga clic en el botón **Instalar** del primer resultado.</span><span class="sxs-lookup"><span data-stu-id="d6f82-110">From the results pane, click the **Install** button for the first result.</span></span>

4. <span data-ttu-id="d6f82-111">El paquete comenzará la descarga.</span><span class="sxs-lookup"><span data-stu-id="d6f82-111">The package will begin downloading.</span></span> <span data-ttu-id="d6f82-112">Antes de agregarlo al proyecto, aparecerá el diálogo de aceptación de licencia.</span><span class="sxs-lookup"><span data-stu-id="d6f82-112">Before it is added to your project, the License Acceptance dialog will appear.</span></span> <span data-ttu-id="d6f82-113">Si acepta los términos de licencia, haga clic en **Acepto**.</span><span class="sxs-lookup"><span data-stu-id="d6f82-113">If you agree to the license terms, click **I Accept**.</span></span>

5. <span data-ttu-id="d6f82-114">Los últimos ensamblados de controlador de token web JSON se descargarán y agregarán al proyecto.</span><span class="sxs-lookup"><span data-stu-id="d6f82-114">The latest JSON Web Token Handler assemblies will be downloaded and added to your project.</span></span>

## <a name="use-the-package-manager-console"></a><span data-ttu-id="d6f82-115">Use la consola de administrador de paquetes</span><span class="sxs-lookup"><span data-stu-id="d6f82-115">Use the Package Manager Console</span></span>

1. <span data-ttu-id="d6f82-116">En Visual Studio, haga clic en **herramientas** > **Administrador de paquetes de NuGet** > **Package Manager Console**.</span><span class="sxs-lookup"><span data-stu-id="d6f82-116">In Visual Studio, click **Tools** > **NuGet Package Manager** > **Package Manager Console**.</span></span>

2. <span data-ttu-id="d6f82-117">Aparece la **Consola del Administrador de paquetes**.</span><span class="sxs-lookup"><span data-stu-id="d6f82-117">The **Package Manager Console** appears.</span></span> <span data-ttu-id="d6f82-118">Escriba el texto siguiente y presione **Entrar**:</span><span class="sxs-lookup"><span data-stu-id="d6f82-118">Enter the following text and press **Enter**:</span></span>

    ```powershell
    Install-Package System.IdentityModel.Tokens.Jwt
    ```

3. <span data-ttu-id="d6f82-119">Los últimos ensamblados de controlador de token web JSON se descargarán y agregarán al proyecto.</span><span class="sxs-lookup"><span data-stu-id="d6f82-119">The latest JSON Web Token Handler assemblies will be downloaded and added to your project.</span></span>