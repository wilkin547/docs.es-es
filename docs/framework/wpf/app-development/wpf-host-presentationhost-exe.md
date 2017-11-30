---
title: WPF Host (PresentationHost.exe)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WPF Host application [WPF]
- PresentationHost.exe
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8b7662213d7204675de7e8681b6fc8141f04dd21
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="wpf-host-presentationhostexe"></a><span data-ttu-id="72aa4-102">WPF Host (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="72aa4-102">WPF Host (PresentationHost.exe)</span></span>
[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]<span data-ttu-id="72aa4-103"> Host (PresentationHost.exe) es la aplicación que permite que las aplicaciones [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] se hospeden en exploradores compatibles (incluido [!INCLUDE[TLA#tla_ie6](../../../../includes/tlasharptla-ie6-md.md)] y versiones posteriores).</span><span class="sxs-lookup"><span data-stu-id="72aa4-103"> Host (PresentationHost.exe) is the application that enables [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications to be hosted in compatible browsers (including [!INCLUDE[TLA#tla_ie6](../../../../includes/tlasharptla-ie6-md.md)] and later).</span></span> <span data-ttu-id="72aa4-104">De forma predeterminada, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Host se registra como el shell y el controlador [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] para contenido [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] hospedado en el explorador, lo cual incluye:</span><span class="sxs-lookup"><span data-stu-id="72aa4-104">By default, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Host is registered as the shell and [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] handler for browser-hosted [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] content, which includes:</span></span>  
  
-   <span data-ttu-id="72aa4-105">Archivos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dinámicos (sin compilar) (.xaml).</span><span class="sxs-lookup"><span data-stu-id="72aa4-105">Loose (uncompiled) [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files (.xaml).</span></span>  
  
-   [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)]<span data-ttu-id="72aa4-106"> (.xbap).</span><span class="sxs-lookup"><span data-stu-id="72aa4-106"> (.xbap).</span></span>  
  
 <span data-ttu-id="72aa4-107">Para estos tipos de archivos [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Host:</span><span class="sxs-lookup"><span data-stu-id="72aa4-107">For files of these types, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Host:</span></span>  
  
-   <span data-ttu-id="72aa4-108">Inicia el controlador de [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] registrado para hospedar el contenido [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72aa4-108">Launches the registered [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] handler to host the [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] content.</span></span>  
  
-   <span data-ttu-id="72aa4-109">Carga las versiones correctas de los ensamblados obligatorios [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] y [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72aa4-109">Loads the right versions of the required [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] and [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] assemblies.</span></span>  
  
-   <span data-ttu-id="72aa4-110">Garantiza que los niveles de permisos adecuados para la zona de implementación están en vigor.</span><span class="sxs-lookup"><span data-stu-id="72aa4-110">Ensures the appropriate permission levels for the zone of deployment are in place.</span></span>  
  
 <span data-ttu-id="72aa4-111">Este tema describe los parámetros de la línea de comandos que se pueden utilizar con PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="72aa4-111">This topic describes the command line parameters that can be used with PresentationHost.exe.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="72aa4-112">Uso</span><span class="sxs-lookup"><span data-stu-id="72aa4-112">Usage</span></span>  
 `PresentationHost.exe [parameters] uri|filename`  
  
## <a name="parameters"></a><span data-ttu-id="72aa4-113">Parámetros</span><span class="sxs-lookup"><span data-stu-id="72aa4-113">Parameters</span></span>  
  
|<span data-ttu-id="72aa4-114">Parámetro</span><span class="sxs-lookup"><span data-stu-id="72aa4-114">Parameter</span></span>|<span data-ttu-id="72aa4-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="72aa4-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="72aa4-116">filename</span><span class="sxs-lookup"><span data-stu-id="72aa4-116">filename</span></span>|<span data-ttu-id="72aa4-117">Ruta al archivo que se va a activar.</span><span class="sxs-lookup"><span data-stu-id="72aa4-117">The path of the file to be activated.</span></span> <span data-ttu-id="72aa4-118">También puede ser un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72aa4-118">Can also be a [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].</span></span>|  
|<span data-ttu-id="72aa4-119">-debug</span><span class="sxs-lookup"><span data-stu-id="72aa4-119">-debug</span></span>|<span data-ttu-id="72aa4-120">Al activar una aplicación, no la confirma ni la ejecuta desde el almacén.</span><span class="sxs-lookup"><span data-stu-id="72aa4-120">When activating an application, does not commit it to or run it from the store.</span></span> <span data-ttu-id="72aa4-121">Esto sólo funciona cuando se activa un archivo local.</span><span class="sxs-lookup"><span data-stu-id="72aa4-121">This only works when a local file is activated.</span></span>|  
|<span data-ttu-id="72aa4-122">-debugSecurityZoneURL \<url></span><span class="sxs-lookup"><span data-stu-id="72aa4-122">-debugSecurityZoneURL \<url></span></span>|<span data-ttu-id="72aa4-123">Se utiliza con un valor [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] para indicar a PresentationHost.exe que una aplicación se debe depurar como si se hubiera implementado desde la [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] especificada.</span><span class="sxs-lookup"><span data-stu-id="72aa4-123">Used with a [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] value to indicate to PresentationHost.exe that an application should be debugged as if it were deployed from the specified [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)].</span></span> <span data-ttu-id="72aa4-124">Esto determina la zona de implementación y el sitio de origen.</span><span class="sxs-lookup"><span data-stu-id="72aa4-124">This determines both the deployment zone and the site of origin.</span></span>|  
|<span data-ttu-id="72aa4-125">-embedding</span><span class="sxs-lookup"><span data-stu-id="72aa4-125">-embedding</span></span>|<span data-ttu-id="72aa4-126">Requerido por OLE.</span><span class="sxs-lookup"><span data-stu-id="72aa4-126">Required by OLE.</span></span> <span data-ttu-id="72aa4-127">Si se especifica el parámetro `-event` o `-debug`, no será necesario especificar el parámetro `-embedding`, ya que ese parámetro se establece internamente.</span><span class="sxs-lookup"><span data-stu-id="72aa4-127">If the `-event` or `-debug` parameter are specified, it is not necessary to specify the `-embedding` parameter, since that parameter is set internally.</span></span>|  
|<span data-ttu-id="72aa4-128">-event \<eventname></span><span class="sxs-lookup"><span data-stu-id="72aa4-128">-event \<eventname></span></span>|<span data-ttu-id="72aa4-129">Abra el evento con este nombre y señálelo cuando PresentationHost.exe se inicialice y esté listo para hospedar el contenido [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72aa4-129">Open the event with this name and signal it when PresentationHost.exe is initialized and ready to host [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] content.</span></span> <span data-ttu-id="72aa4-130">PresentationHost.exe finalizará si se produce un error al abrir el evento como, por ejemplo, si este no se ha creado todavía.</span><span class="sxs-lookup"><span data-stu-id="72aa4-130">PresentationHost.exe will terminate if there was an error opening the event, such as if it has not already been created.</span></span>|  
|<span data-ttu-id="72aa4-131">-launchApplication \<url></span><span class="sxs-lookup"><span data-stu-id="72aa4-131">-launchApplication \<url></span></span>|<span data-ttu-id="72aa4-132">Inicia una aplicación [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] independiente desde la dirección URL especificada.</span><span class="sxs-lookup"><span data-stu-id="72aa4-132">Launches a standalone [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] application from the specified URL.</span></span> <span data-ttu-id="72aa4-133">Se aplican las directivas de seguridad [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] y WinINet relativas a las aplicaciones .NET.</span><span class="sxs-lookup"><span data-stu-id="72aa4-133">[!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] and WinINet security policy concerning .NET applications are applied.</span></span>|  
  
## <a name="scenarios"></a><span data-ttu-id="72aa4-134">Escenarios</span><span class="sxs-lookup"><span data-stu-id="72aa4-134">Scenarios</span></span>  
  
### <a name="shell-handler"></a><span data-ttu-id="72aa4-135">Controlador de shell</span><span class="sxs-lookup"><span data-stu-id="72aa4-135">Shell Handler</span></span>  
 `PresentationHost.exe example.xbap`  
  
### <a name="mime-handler"></a><span data-ttu-id="72aa4-136">Controlador de MIME</span><span class="sxs-lookup"><span data-stu-id="72aa4-136">MIME Handler</span></span>  
 `PresentationHost.exe -embedding example.xbap`  
  
### <a name="visual-studio-debugging"></a><span data-ttu-id="72aa4-137">Depuración de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="72aa4-137">Visual Studio Debugging</span></span>  
 `PresentationHost.exe -debug example.xbap`  
  
### <a name="visual-studio-debugging-in-zone"></a><span data-ttu-id="72aa4-138">Depuración de Visual Studio en Zone</span><span class="sxs-lookup"><span data-stu-id="72aa4-138">Visual Studio Debugging In Zone</span></span>  
 `PresentationHost.exe -debug -debugSecurityZoneURL http://www.example.com c:\folderpath\example.xbap`  
  
## <a name="see-also"></a><span data-ttu-id="72aa4-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="72aa4-139">See Also</span></span>  
 [<span data-ttu-id="72aa4-140">Seguridad</span><span class="sxs-lookup"><span data-stu-id="72aa4-140">Security</span></span>](../../../../docs/framework/wpf/security-wpf.md)
