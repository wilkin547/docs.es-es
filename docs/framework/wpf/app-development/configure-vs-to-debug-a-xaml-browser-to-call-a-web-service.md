---
title: 'Cómo: Configurar Visual Studio para depurar una aplicación de explorador XAML y llamar a un servicio Web'
ms.date: 03/30/2017
helpviewer_keywords:
- debugging XBAPs that call a Web service [WPF]
- debugging security exceptions for XBAPs [WPF]
- security exception for XBAPs [WPF], debugging
- configuring Visual Studio to debug XAML browser applications [WPF]
- configuring Visual Studio to debug XBAPs [WPF]
ms.assetid: fd1db082-a7bb-4c4b-9331-6ad74a0682d0
ms.openlocfilehash: 182ceb96385bdca74d1d5c20079f78fe589982cf
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2018
ms.locfileid: "48873208"
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a><span data-ttu-id="6ef5c-102">Cómo: Configurar Visual Studio para depurar una aplicación de explorador XAML y llamar a un servicio Web</span><span class="sxs-lookup"><span data-stu-id="6ef5c-102">How to: Configure Visual Studio to Debug a XAML Browser Application to Call a Web Service</span></span>
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] <span data-ttu-id="6ef5c-103">ejecutar en un recinto de seguridad de confianza parcial está restringido para el conjunto de permisos de zona de Internet.</span><span class="sxs-lookup"><span data-stu-id="6ef5c-103"> run within a partial-trust security sandbox that is restricted to the Internet zone set of permissions.</span></span> <span data-ttu-id="6ef5c-104">Este conjunto de permisos restringe las llamadas a solo servicios Web que se encuentran en el [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] sitio de origen de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6ef5c-104">This permission set restricts Web service calls to only Web services that are located at the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] application's site of origin.</span></span> <span data-ttu-id="6ef5c-105">Cuando un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] se depura desde Visual Studio 2005, sin embargo, no se considera que tienen el mismo sitio de origen como el servicio Web, las referencias.</span><span class="sxs-lookup"><span data-stu-id="6ef5c-105">When an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] is debugged from Visual Studio 2005, though, it is not considered to have the same site of origin as the Web service it references.</span></span> <span data-ttu-id="6ef5c-106">Este excepciones de seguridad de las causas que se genera cuando el [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] intenta llamar al servicio Web.</span><span class="sxs-lookup"><span data-stu-id="6ef5c-106">This causes security exceptions to be raised when the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] attempts to call the Web service.</span></span> <span data-ttu-id="6ef5c-107">Sin embargo, un Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] proyecto puede configurarse para simular que tiene el mismo sitio de origen que el servicio Web que llama durante la depuración.</span><span class="sxs-lookup"><span data-stu-id="6ef5c-107">However, a Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project can be configured to simulate having the same site of origin as the Web service it calls while debugging.</span></span> <span data-ttu-id="6ef5c-108">Esto permite la [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] llame al servicio Web sin ningún riesgo sin producir excepciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6ef5c-108">This allows the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] to safely call the Web service without causing security exceptions.</span></span>

## <a name="configuring-visual-studio"></a><span data-ttu-id="6ef5c-109">Configurar Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6ef5c-109">Configuring Visual Studio</span></span>
 <span data-ttu-id="6ef5c-110">Para configurar Visual Studio 2005 para depurar un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] que llama a un servicio Web:</span><span class="sxs-lookup"><span data-stu-id="6ef5c-110">To configure Visual Studio 2005 to debug an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] that calls a Web service:</span></span>

1.  <span data-ttu-id="6ef5c-111">Seleccione un proyecto en el **Explorador de soluciones**y, en el menú **Proyecto** , haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6ef5c-111">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2.  <span data-ttu-id="6ef5c-112">En el **Diseñador de proyectos**, haga clic en el **depurar** ficha.</span><span class="sxs-lookup"><span data-stu-id="6ef5c-112">In the **Project Designer**, click the **Debug** tab.</span></span>

3.  <span data-ttu-id="6ef5c-113">En el **acción de inicio** sección, seleccione **iniciar programa externo** y escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6ef5c-113">In the **Start Action** section, select **Start external program** and enter the following:</span></span>

     `C:\WINDOWS\System32\PresentationHost.exe`

4.  <span data-ttu-id="6ef5c-114">En el **opciones de inicio** sección, escriba lo siguiente en el **argumentos de línea de comandos** cuadro de texto:</span><span class="sxs-lookup"><span data-stu-id="6ef5c-114">In the **Start Options** section, enter the following into the **Command line arguments** text box:</span></span>

     <span data-ttu-id="6ef5c-115">`-debug`  *Nombre de archivo*</span><span class="sxs-lookup"><span data-stu-id="6ef5c-115">`-debug`  *filename*</span></span>

     <span data-ttu-id="6ef5c-116">El *filename* valor para el **-depurar** parámetro es el nombre de archivo .xbap; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6ef5c-116">The *filename* value for the **-debug** parameter is the .xbap filename; for example:</span></span>

     `-debug c:\example.xbap`

> [!NOTE]
>  <span data-ttu-id="6ef5c-117">Esta es la configuración predeterminada para las soluciones creadas con Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] plantilla de proyecto.</span><span class="sxs-lookup"><span data-stu-id="6ef5c-117">This is the default configuration for solutions that are created with the Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project template.</span></span>

1.  <span data-ttu-id="6ef5c-118">Seleccione un proyecto en el **Explorador de soluciones**y, en el menú **Proyecto** , haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6ef5c-118">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2.  <span data-ttu-id="6ef5c-119">En el **Diseñador de proyectos**, haga clic en el **depurar** ficha.</span><span class="sxs-lookup"><span data-stu-id="6ef5c-119">In the **Project Designer**, click the **Debug** tab.</span></span>

3.  <span data-ttu-id="6ef5c-120">En el **opciones de inicio** sección, agregue el siguiente parámetro de línea de comandos para el **argumentos de línea de comandos** cuadro de texto:</span><span class="sxs-lookup"><span data-stu-id="6ef5c-120">In the **Start Options** section, add the following command-line parameter to the **Command line arguments** text box:</span></span>

     <span data-ttu-id="6ef5c-121">`-debugSecurityZoneURL`  *URL*</span><span class="sxs-lookup"><span data-stu-id="6ef5c-121">`-debugSecurityZoneURL`  *URL*</span></span>

     <span data-ttu-id="6ef5c-122">El *URL* valor para el **- debugSecurityZoneURL** parámetro es el [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] para la ubicación que desee simular como sitio de origen de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6ef5c-122">The *URL* value for the **-debugSecurityZoneURL** parameter is the [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] for the location that you want to simulate as being the site of origin of your application.</span></span>

 <span data-ttu-id="6ef5c-123">Por ejemplo, considere la posibilidad de un [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] que utiliza un servicio Web con el siguiente [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="6ef5c-123">As an example, consider a [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] that uses a Web service with the following [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:</span></span>

 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`

 <span data-ttu-id="6ef5c-124">El sitio de origen [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] para este sitio Web de servicio es:</span><span class="sxs-lookup"><span data-stu-id="6ef5c-124">The site of origin [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] for this Web service is:</span></span>

 `http://services.msdn.microsoft.com`

 <span data-ttu-id="6ef5c-125">Por lo tanto, toda **- debugSecurityZoneURL** valor y parámetro de línea de comandos es:</span><span class="sxs-lookup"><span data-stu-id="6ef5c-125">Consequently, the complete **-debugSecurityZoneURL** command-line parameter and value is:</span></span>

 `-debugSecurityZoneURL http://services.msdn.microsoft.com`

## <a name="see-also"></a><span data-ttu-id="6ef5c-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ef5c-126">See Also</span></span>
 [<span data-ttu-id="6ef5c-127">WPF Host (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="6ef5c-127">WPF Host (PresentationHost.exe)</span></span>](../../../../docs/framework/wpf/app-development/wpf-host-presentationhost-exe.md)
