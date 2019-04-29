---
title: Descargar el paquete de validación del Registro de nombres de emisores
ms.date: 10/10/2018
ms.assetid: ff8b0014-c5d4-4614-90f0-13fcc0ba777a
ms.openlocfilehash: 833a0722fdd27df4e488ed7fac99444c6d9b8905
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940587"
---
# <a name="download-the-validating-issuer-name-registry-package"></a><span data-ttu-id="3452f-102">Descargue el paquete de registro de nombres de validación del emisor</span><span class="sxs-lookup"><span data-stu-id="3452f-102">Download the Validating Issuer Name Registry Package</span></span>

<span data-ttu-id="3452f-103">En este tema se explica cómo descargar y usar el Registro de nombres del emisor que valida (VINR) en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="3452f-103">This topic discusses how to download and use the Validating Issuer Name Registry (VINR) in your project.</span></span>

<span data-ttu-id="3452f-104">El VINR está disponible como un paquete NuGet, que agrega las referencias y los ensamblados necesarios al proyecto.</span><span class="sxs-lookup"><span data-stu-id="3452f-104">The VINR is available as a NuGet package, which adds the necessary assemblies and references to your project.</span></span> <span data-ttu-id="3452f-105">Si aún no tiene NuGet instalado, vaya a [nuget.org](https://nuget.org) para instalarlo.</span><span class="sxs-lookup"><span data-stu-id="3452f-105">If you do not already have NuGet installed, go to [nuget.org](https://nuget.org) to install it.</span></span> <span data-ttu-id="3452f-106">Puede ver el historial de control de versiones para la extensión si visita su página en NuGet: [Validar el registro de nombre de emisor en NuGet de Microsoft](https://nuget.org/packages/System.IdentityModel.Tokens.ValidatingIssuerNameRegistry/)</span><span class="sxs-lookup"><span data-stu-id="3452f-106">You can see the versioning history for the extension by visiting its page on NuGet: [Microsoft Validating Issuer Name Registry on NuGet](https://nuget.org/packages/System.IdentityModel.Tokens.ValidatingIssuerNameRegistry/)</span></span>

## <a name="use-the-package-manager-gui"></a><span data-ttu-id="3452f-107">Usar la GUI del Administrador de paquetes</span><span class="sxs-lookup"><span data-stu-id="3452f-107">Use the Package Manager GUI</span></span>

1. <span data-ttu-id="3452f-108">En Visual Studio, haga clic con el botón derecho en el proyecto en el **Explorador de soluciones** y, después, seleccione **Administrar paquetes NuGet**.</span><span class="sxs-lookup"><span data-stu-id="3452f-108">In Visual Studio, right-click your project in **Solution Explorer**, and then select **Manage NuGet Packages**.</span></span>

2. <span data-ttu-id="3452f-109">En la ventana **Administrar paquetes NuGet**, haga clic en el cuadro de búsqueda, escriba `ValidatingIssuerNameRegistry` y presione **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="3452f-109">In the **Manage NuGet Packages** window, click the search box and enter `ValidatingIssuerNameRegistry` and press **Enter**.</span></span>

3. <span data-ttu-id="3452f-110">En el panel de resultados, haga clic en el botón **Instalar** del primer resultado.</span><span class="sxs-lookup"><span data-stu-id="3452f-110">From the results pane, click the **Install** button for the first result.</span></span>

4. <span data-ttu-id="3452f-111">El paquete comenzará la descarga.</span><span class="sxs-lookup"><span data-stu-id="3452f-111">The package will begin downloading.</span></span> <span data-ttu-id="3452f-112">Antes de agregarlo al proyecto, aparecerá el diálogo de aceptación de licencia.</span><span class="sxs-lookup"><span data-stu-id="3452f-112">Before it is added to your project, the License Acceptance dialog will appear.</span></span> <span data-ttu-id="3452f-113">Si acepta los términos de licencia, haga clic en **Acepto**.</span><span class="sxs-lookup"><span data-stu-id="3452f-113">If you agree to the license terms, click **I Accept**.</span></span>

5. <span data-ttu-id="3452f-114">Los últimos ensamblados VINR se descargarán y agregarán al proyecto.</span><span class="sxs-lookup"><span data-stu-id="3452f-114">The latest VINR assemblies will be downloaded and added to your project.</span></span>

## <a name="use-the-package-manager-console"></a><span data-ttu-id="3452f-115">Use la consola de administrador de paquetes</span><span class="sxs-lookup"><span data-stu-id="3452f-115">Use the Package Manager Console</span></span>

1. <span data-ttu-id="3452f-116">En Visual Studio, haga clic en **herramientas** > **Administrador de paquetes de NuGet** > **Package Manager Console**.</span><span class="sxs-lookup"><span data-stu-id="3452f-116">In Visual Studio, click **Tools** > **NuGet Package Manager** > **Package Manager Console**.</span></span>

2. <span data-ttu-id="3452f-117">Aparece la **Consola del Administrador de paquetes**.</span><span class="sxs-lookup"><span data-stu-id="3452f-117">The **Package Manager Console** appears.</span></span> <span data-ttu-id="3452f-118">Escriba el texto siguiente y presione **Entrar**:</span><span class="sxs-lookup"><span data-stu-id="3452f-118">Enter the following text and press **Enter**:</span></span>

    ```powershell
    Install-Package System.IdentityModel.Tokens.ValidatingIssuerNameRegistry
    ```

3. <span data-ttu-id="3452f-119">Los últimos ensamblados VINR se descargarán y agregarán al proyecto.</span><span class="sxs-lookup"><span data-stu-id="3452f-119">The latest VINR assemblies will be downloaded and added to your project.</span></span>