---
title: WPF Host (PresentationHost.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Host application [WPF]
- PresentationHost.exe
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
ms.openlocfilehash: 543076c3b00bf7946111df4c18d8c71928ce7ee2
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2019
ms.locfileid: "67487322"
---
# <a name="wpf-host-presentationhostexe"></a><span data-ttu-id="f8277-102">WPF Host (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="f8277-102">WPF Host (PresentationHost.exe)</span></span>
<span data-ttu-id="f8277-103">Windows Presentation Foundation (WPF) de Host (PresentationHost.exe) es la aplicación que permite [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aplicaciones para alojarlas en exploradores compatibles (incluido [!INCLUDE[TLA#tla_ie6](../../../../includes/tlasharptla-ie6-md.md)] y versiones posteriores).</span><span class="sxs-lookup"><span data-stu-id="f8277-103">Windows Presentation Foundation (WPF) Host (PresentationHost.exe) is the application that enables [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications to be hosted in compatible browsers (including [!INCLUDE[TLA#tla_ie6](../../../../includes/tlasharptla-ie6-md.md)] and later).</span></span> <span data-ttu-id="f8277-104">De forma predeterminada, el Host de Windows Presentation Foundation (WPF) se registra como el shell y [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] controlador para hospedadas en explorador [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] contenido, que incluye:</span><span class="sxs-lookup"><span data-stu-id="f8277-104">By default, Windows Presentation Foundation (WPF) Host is registered as the shell and [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] handler for browser-hosted [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] content, which includes:</span></span>  
  
- <span data-ttu-id="f8277-105">Archivos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dinámicos (sin compilar) (.xaml).</span><span class="sxs-lookup"><span data-stu-id="f8277-105">Loose (uncompiled) [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files (.xaml).</span></span>  
  
- [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] <span data-ttu-id="f8277-106">(.xbap).</span><span class="sxs-lookup"><span data-stu-id="f8277-106">(.xbap).</span></span>  
  
 <span data-ttu-id="f8277-107">Para los archivos de estos tipos, el Host de Windows Presentation Foundation (WPF):</span><span class="sxs-lookup"><span data-stu-id="f8277-107">For files of these types, Windows Presentation Foundation (WPF) Host:</span></span>  
  
- <span data-ttu-id="f8277-108">Inicia registrado [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] controlador para hospedar el contenido de Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="f8277-108">Launches the registered [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] handler to host the Windows Presentation Foundation (WPF) content.</span></span>  
  
- <span data-ttu-id="f8277-109">Carga las versiones correctas de los necesarios [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] y ensamblados de Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="f8277-109">Loads the right versions of the required [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] and Windows Presentation Foundation (WPF) assemblies.</span></span>  
  
- <span data-ttu-id="f8277-110">Garantiza que los niveles de permisos adecuados para la zona de implementación están en vigor.</span><span class="sxs-lookup"><span data-stu-id="f8277-110">Ensures the appropriate permission levels for the zone of deployment are in place.</span></span>  
  
 <span data-ttu-id="f8277-111">Este tema describe los parámetros de la línea de comandos que se pueden utilizar con PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="f8277-111">This topic describes the command line parameters that can be used with PresentationHost.exe.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="f8277-112">Uso</span><span class="sxs-lookup"><span data-stu-id="f8277-112">Usage</span></span>  
 `PresentationHost.exe [parameters] uri|filename`  
  
## <a name="parameters"></a><span data-ttu-id="f8277-113">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f8277-113">Parameters</span></span>  
  
|<span data-ttu-id="f8277-114">Parámetro</span><span class="sxs-lookup"><span data-stu-id="f8277-114">Parameter</span></span>|<span data-ttu-id="f8277-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="f8277-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f8277-116">filename</span><span class="sxs-lookup"><span data-stu-id="f8277-116">filename</span></span>|<span data-ttu-id="f8277-117">Ruta al archivo que se va a activar.</span><span class="sxs-lookup"><span data-stu-id="f8277-117">The path of the file to be activated.</span></span> <span data-ttu-id="f8277-118">También puede ser un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f8277-118">Can also be a [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>|  
|<span data-ttu-id="f8277-119">-debug</span><span class="sxs-lookup"><span data-stu-id="f8277-119">-debug</span></span>|<span data-ttu-id="f8277-120">Al activar una aplicación, no la confirma ni la ejecuta desde el almacén.</span><span class="sxs-lookup"><span data-stu-id="f8277-120">When activating an application, does not commit it to or run it from the store.</span></span> <span data-ttu-id="f8277-121">Esto sólo funciona cuando se activa un archivo local.</span><span class="sxs-lookup"><span data-stu-id="f8277-121">This only works when a local file is activated.</span></span>|  
|<span data-ttu-id="f8277-122">-debugSecurityZoneURL \<url></span><span class="sxs-lookup"><span data-stu-id="f8277-122">-debugSecurityZoneURL \<url></span></span>|<span data-ttu-id="f8277-123">Se utiliza con un valor [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] para indicar a PresentationHost.exe que una aplicación se debe depurar como si se hubiera implementado desde la [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] especificada.</span><span class="sxs-lookup"><span data-stu-id="f8277-123">Used with a [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] value to indicate to PresentationHost.exe that an application should be debugged as if it were deployed from the specified [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)].</span></span> <span data-ttu-id="f8277-124">Esto determina la zona de implementación y el sitio de origen.</span><span class="sxs-lookup"><span data-stu-id="f8277-124">This determines both the deployment zone and the site of origin.</span></span>|  
|<span data-ttu-id="f8277-125">-embedding</span><span class="sxs-lookup"><span data-stu-id="f8277-125">-embedding</span></span>|<span data-ttu-id="f8277-126">Requerido por OLE.</span><span class="sxs-lookup"><span data-stu-id="f8277-126">Required by OLE.</span></span> <span data-ttu-id="f8277-127">Si se especifica el parámetro `-event` o `-debug`, no será necesario especificar el parámetro `-embedding`, ya que ese parámetro se establece internamente.</span><span class="sxs-lookup"><span data-stu-id="f8277-127">If the `-event` or `-debug` parameter are specified, it is not necessary to specify the `-embedding` parameter, since that parameter is set internally.</span></span>|  
|<span data-ttu-id="f8277-128">-event \<eventname></span><span class="sxs-lookup"><span data-stu-id="f8277-128">-event \<eventname></span></span>|<span data-ttu-id="f8277-129">Abra el evento con este nombre y señálelo cuando PresentationHost.exe se inicialice y esté listo para hospedar el contenido [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f8277-129">Open the event with this name and signal it when PresentationHost.exe is initialized and ready to host [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] content.</span></span> <span data-ttu-id="f8277-130">PresentationHost.exe finalizará si se produce un error al abrir el evento como, por ejemplo, si este no se ha creado todavía.</span><span class="sxs-lookup"><span data-stu-id="f8277-130">PresentationHost.exe will terminate if there was an error opening the event, such as if it has not already been created.</span></span>|  
|<span data-ttu-id="f8277-131">-launchApplication \<url></span><span class="sxs-lookup"><span data-stu-id="f8277-131">-launchApplication \<url></span></span>|<span data-ttu-id="f8277-132">Inicia una aplicación ClickOnce desde la dirección URL especificada independiente.</span><span class="sxs-lookup"><span data-stu-id="f8277-132">Launches a standalone ClickOnce application from the specified URL.</span></span> <span data-ttu-id="f8277-133">Se aplican las directivas de seguridad [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] y WinINet relativas a las aplicaciones .NET.</span><span class="sxs-lookup"><span data-stu-id="f8277-133">[!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] and WinINet security policy concerning .NET applications are applied.</span></span>|  
  
## <a name="scenarios"></a><span data-ttu-id="f8277-134">Escenarios</span><span class="sxs-lookup"><span data-stu-id="f8277-134">Scenarios</span></span>  
  
### <a name="shell-handler"></a><span data-ttu-id="f8277-135">Controlador de shell</span><span class="sxs-lookup"><span data-stu-id="f8277-135">Shell Handler</span></span>  
 `PresentationHost.exe example.xbap`  
  
### <a name="mime-handler"></a><span data-ttu-id="f8277-136">Controlador de MIME</span><span class="sxs-lookup"><span data-stu-id="f8277-136">MIME Handler</span></span>  
 `PresentationHost.exe -embedding example.xbap`  
  
### <a name="visual-studio-debugging"></a><span data-ttu-id="f8277-137">Depuración de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f8277-137">Visual Studio Debugging</span></span>  
 `PresentationHost.exe -debug example.xbap`  
  
### <a name="visual-studio-debugging-in-zone"></a><span data-ttu-id="f8277-138">Depuración de Visual Studio en Zone</span><span class="sxs-lookup"><span data-stu-id="f8277-138">Visual Studio Debugging In Zone</span></span>  
 `PresentationHost.exe -debug -debugSecurityZoneURL http://www.example.com c:\folderpath\example.xbap`  
  
## <a name="see-also"></a><span data-ttu-id="f8277-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8277-139">See also</span></span>

- [<span data-ttu-id="f8277-140">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f8277-140">Security</span></span>](../security-wpf.md)
