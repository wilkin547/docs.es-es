---
title: Procedimiento Configurar Visual Studio para depurar una aplicación de explorador XAML y llamar a un servicio web
ms.date: 03/30/2017
helpviewer_keywords:
- debugging XBAPs that call a Web service [WPF]
- debugging security exceptions for XBAPs [WPF]
- security exception for XBAPs [WPF], debugging
- configuring Visual Studio to debug XAML browser applications [WPF]
- configuring Visual Studio to debug XBAPs [WPF]
ms.assetid: fd1db082-a7bb-4c4b-9331-6ad74a0682d0
ms.openlocfilehash: e41dd46e4ddbdcde6448c68b4f9fb2e073baca43
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69958685"
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a><span data-ttu-id="5521e-102">Procedimiento Configurar Visual Studio para depurar una aplicación de explorador XAML y llamar a un servicio web</span><span class="sxs-lookup"><span data-stu-id="5521e-102">How to: Configure Visual Studio to Debug a XAML Browser Application to Call a Web Service</span></span>
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]<span data-ttu-id="5521e-103">se ejecuta dentro de un espacio aislado de seguridad de confianza parcial que está restringido al conjunto de permisos de la zona de Internet.</span><span class="sxs-lookup"><span data-stu-id="5521e-103">run within a partial-trust security sandbox that is restricted to the Internet zone set of permissions.</span></span> <span data-ttu-id="5521e-104">Este conjunto de permisos restringe las llamadas de servicio Web a los servicios web que se [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] encuentran en el sitio de origen de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5521e-104">This permission set restricts Web service calls to only Web services that are located at the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] application's site of origin.</span></span> <span data-ttu-id="5521e-105">Sin embargo, cuando sedepuradesdeVisualStudio2005,noseconsideraquetieneelmismositiodeorigenqueelservicioWebalquehacereferencia.[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5521e-105">When an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] is debugged from Visual Studio 2005, though, it is not considered to have the same site of origin as the Web service it references.</span></span> <span data-ttu-id="5521e-106">Esto hace que se produzcan excepciones de seguridad [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] cuando intenta llamar al servicio Web.</span><span class="sxs-lookup"><span data-stu-id="5521e-106">This causes security exceptions to be raised when the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] attempts to call the Web service.</span></span> <span data-ttu-id="5521e-107">Sin embargo, se puede configurar [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] un proyecto de Visual Studio 2005 para simular tener el mismo sitio de origen que el servicio Web al que llama durante la depuración.</span><span class="sxs-lookup"><span data-stu-id="5521e-107">However, a Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project can be configured to simulate having the same site of origin as the Web service it calls while debugging.</span></span> <span data-ttu-id="5521e-108">Esto permite a [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] la llamada de forma segura al servicio Web sin producir excepciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5521e-108">This allows the [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] to safely call the Web service without causing security exceptions.</span></span>

## <a name="configuring-visual-studio"></a><span data-ttu-id="5521e-109">Configuración de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5521e-109">Configuring Visual Studio</span></span>
 <span data-ttu-id="5521e-110">Para configurar Visual Studio 2005 para depurar un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] que llama a un servicio Web:</span><span class="sxs-lookup"><span data-stu-id="5521e-110">To configure Visual Studio 2005 to debug an [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] that calls a Web service:</span></span>

1. <span data-ttu-id="5521e-111">Seleccione un proyecto en el **Explorador de soluciones**y, en el menú **Proyecto** , haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5521e-111">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="5521e-112">En el **Diseñador de proyectos**, haga clic en la pestaña depurar.</span><span class="sxs-lookup"><span data-stu-id="5521e-112">In the **Project Designer**, click the **Debug** tab.</span></span>

3. <span data-ttu-id="5521e-113">En la sección **acción de inicio** , seleccione **programa externo de inicio** y escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5521e-113">In the **Start Action** section, select **Start external program** and enter the following:</span></span>

     `C:\WINDOWS\System32\PresentationHost.exe`

4. <span data-ttu-id="5521e-114">En la sección **Opciones de inicio** , escriba lo siguiente en el cuadro de texto argumentos de la línea de **comandos** :</span><span class="sxs-lookup"><span data-stu-id="5521e-114">In the **Start Options** section, enter the following into the **Command line arguments** text box:</span></span>

     <span data-ttu-id="5521e-115">`-debug`  *extensión*</span><span class="sxs-lookup"><span data-stu-id="5521e-115">`-debug`  *filename*</span></span>

     <span data-ttu-id="5521e-116">El valor del *nombre de archivo* para el parámetro **-Debug** es el nombre de archivo. XBAP; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5521e-116">The *filename* value for the **-debug** parameter is the .xbap filename; for example:</span></span>

     `-debug c:\example.xbap`

> [!NOTE]
> <span data-ttu-id="5521e-117">Esta es la configuración predeterminada para las soluciones que se crean con la plantilla de [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] proyecto de Visual Studio 2005.</span><span class="sxs-lookup"><span data-stu-id="5521e-117">This is the default configuration for solutions that are created with the Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] project template.</span></span>

1. <span data-ttu-id="5521e-118">Seleccione un proyecto en el **Explorador de soluciones**y, en el menú **Proyecto** , haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5521e-118">With a project selected in **Solution Explorer**, on the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="5521e-119">En el **Diseñador de proyectos**, haga clic en la pestaña depurar.</span><span class="sxs-lookup"><span data-stu-id="5521e-119">In the **Project Designer**, click the **Debug** tab.</span></span>

3. <span data-ttu-id="5521e-120">En la sección **Opciones de inicio** , agregue el siguiente parámetro de línea de comandos al cuadro de texto argumentos de línea de **comandos** :</span><span class="sxs-lookup"><span data-stu-id="5521e-120">In the **Start Options** section, add the following command-line parameter to the **Command line arguments** text box:</span></span>

     <span data-ttu-id="5521e-121">`-debugSecurityZoneURL`  *URL*</span><span class="sxs-lookup"><span data-stu-id="5521e-121">`-debugSecurityZoneURL`  *URL*</span></span>

     <span data-ttu-id="5521e-122">El valor de *dirección URL* para el parámetro **-debugSecurityZoneURL** es el [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] de la ubicación que desea simular como el sitio de origen de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5521e-122">The *URL* value for the **-debugSecurityZoneURL** parameter is the [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] for the location that you want to simulate as being the site of origin of your application.</span></span>

 <span data-ttu-id="5521e-123">Como ejemplo, considere un [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] que usa un servicio Web con lo siguiente: [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5521e-123">As an example, consider a [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] that uses a Web service with the following [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:</span></span>

 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`

 <span data-ttu-id="5521e-124">El sitio de origen [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] de este servicio web es:</span><span class="sxs-lookup"><span data-stu-id="5521e-124">The site of origin [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] for this Web service is:</span></span>

 `http://services.msdn.microsoft.com`

 <span data-ttu-id="5521e-125">Por lo tanto, el valor y el parámetro de línea de comandos complete **-debugSecurityZoneURL** son:</span><span class="sxs-lookup"><span data-stu-id="5521e-125">Consequently, the complete **-debugSecurityZoneURL** command-line parameter and value is:</span></span>

 `-debugSecurityZoneURL http://services.msdn.microsoft.com`

## <a name="see-also"></a><span data-ttu-id="5521e-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="5521e-126">See also</span></span>

- [<span data-ttu-id="5521e-127">WPF Host (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="5521e-127">WPF Host (PresentationHost.exe)</span></span>](wpf-host-presentationhost-exe.md)
