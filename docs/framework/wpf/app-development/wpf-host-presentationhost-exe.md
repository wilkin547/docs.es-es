---
title: WPF Host (PresentationHost.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Host application [WPF]
- PresentationHost.exe
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
ms.openlocfilehash: 64ba1261134184f22e9faf157ca70e3471e3b3cb
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636255"
---
# <a name="wpf-host-presentationhostexe"></a><span data-ttu-id="9f0c3-102">WPF Host (PresentationHost.exe)</span><span class="sxs-lookup"><span data-stu-id="9f0c3-102">WPF Host (PresentationHost.exe)</span></span>
<span data-ttu-id="9f0c3-103">El host de Windows Presentation Foundation (WPF) (PresentationHost. exe) es la aplicación que permite hospedar aplicaciones WPF en exploradores compatibles (incluido Microsoft Internet Explorer 6 y versiones posteriores).</span><span class="sxs-lookup"><span data-stu-id="9f0c3-103">Windows Presentation Foundation (WPF) Host (PresentationHost.exe) is the application that enables WPF applications to be hosted in compatible browsers (including Microsoft Internet Explorer 6 and later).</span></span> <span data-ttu-id="9f0c3-104">De forma predeterminada, el host de Windows Presentation Foundation (WPF) se registra como el controlador de Shell y MIME para el contenido WPF hospedado en el explorador, que incluye:</span><span class="sxs-lookup"><span data-stu-id="9f0c3-104">By default, Windows Presentation Foundation (WPF) Host is registered as the shell and MIME handler for browser-hosted WPF content, which includes:</span></span>  
  
- <span data-ttu-id="9f0c3-105">Archivos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dinámicos (sin compilar) (.xaml).</span><span class="sxs-lookup"><span data-stu-id="9f0c3-105">Loose (uncompiled) [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files (.xaml).</span></span>  
  
- <span data-ttu-id="9f0c3-106">Aplicación de explorador XAML (XBAP) (. XBAP).</span><span class="sxs-lookup"><span data-stu-id="9f0c3-106">XAML browser application (XBAP) (.xbap).</span></span>  
  
 <span data-ttu-id="9f0c3-107">En el caso de los archivos de estos tipos, el host de Windows Presentation Foundation (WPF):</span><span class="sxs-lookup"><span data-stu-id="9f0c3-107">For files of these types, Windows Presentation Foundation (WPF) Host:</span></span>  
  
- <span data-ttu-id="9f0c3-108">Inicia el controlador HTML registrado para hospedar el contenido de Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="9f0c3-108">Launches the registered HTML handler to host the Windows Presentation Foundation (WPF) content.</span></span>  
  
- <span data-ttu-id="9f0c3-109">Carga las versiones correctas de los ensamblados Common Language Runtime (CLR) y Windows Presentation Foundation (WPF) necesarios.</span><span class="sxs-lookup"><span data-stu-id="9f0c3-109">Loads the right versions of the required common language runtime (CLR) and Windows Presentation Foundation (WPF) assemblies.</span></span>  
  
- <span data-ttu-id="9f0c3-110">Garantiza que los niveles de permisos adecuados para la zona de implementación están en vigor.</span><span class="sxs-lookup"><span data-stu-id="9f0c3-110">Ensures the appropriate permission levels for the zone of deployment are in place.</span></span>  
  
 <span data-ttu-id="9f0c3-111">Este tema describe los parámetros de la línea de comandos que se pueden utilizar con PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="9f0c3-111">This topic describes the command line parameters that can be used with PresentationHost.exe.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="9f0c3-112">Usage</span><span class="sxs-lookup"><span data-stu-id="9f0c3-112">Usage</span></span>  
 `PresentationHost.exe [parameters] uri|filename`  
  
## <a name="parameters"></a><span data-ttu-id="9f0c3-113">Parameters</span><span class="sxs-lookup"><span data-stu-id="9f0c3-113">Parameters</span></span>  
  
|<span data-ttu-id="9f0c3-114">Parámetro</span><span class="sxs-lookup"><span data-stu-id="9f0c3-114">Parameter</span></span>|<span data-ttu-id="9f0c3-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="9f0c3-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9f0c3-116">filename</span><span class="sxs-lookup"><span data-stu-id="9f0c3-116">filename</span></span>|<span data-ttu-id="9f0c3-117">Ruta al archivo que se va a activar.</span><span class="sxs-lookup"><span data-stu-id="9f0c3-117">The path of the file to be activated.</span></span> <span data-ttu-id="9f0c3-118">También puede ser un URI.</span><span class="sxs-lookup"><span data-stu-id="9f0c3-118">Can also be a URI.</span></span>|  
|<span data-ttu-id="9f0c3-119">-debug</span><span class="sxs-lookup"><span data-stu-id="9f0c3-119">-debug</span></span>|<span data-ttu-id="9f0c3-120">Al activar una aplicación, no la confirma ni la ejecuta desde el almacén.</span><span class="sxs-lookup"><span data-stu-id="9f0c3-120">When activating an application, does not commit it to or run it from the store.</span></span> <span data-ttu-id="9f0c3-121">Esto sólo funciona cuando se activa un archivo local.</span><span class="sxs-lookup"><span data-stu-id="9f0c3-121">This only works when a local file is activated.</span></span>|  
|<span data-ttu-id="9f0c3-122">-debugSecurityZoneURL \<url></span><span class="sxs-lookup"><span data-stu-id="9f0c3-122">-debugSecurityZoneURL \<url></span></span>|<span data-ttu-id="9f0c3-123">Se usa con un valor de dirección URL para indicar a PresentationHost. exe que se debe depurar una aplicación como si se hubiera implementado desde la dirección URL especificada.</span><span class="sxs-lookup"><span data-stu-id="9f0c3-123">Used with a URL value to indicate to PresentationHost.exe that an application should be debugged as if it were deployed from the specified URL.</span></span> <span data-ttu-id="9f0c3-124">Esto determina la zona de implementación y el sitio de origen.</span><span class="sxs-lookup"><span data-stu-id="9f0c3-124">This determines both the deployment zone and the site of origin.</span></span>|  
|<span data-ttu-id="9f0c3-125">-embedding</span><span class="sxs-lookup"><span data-stu-id="9f0c3-125">-embedding</span></span>|<span data-ttu-id="9f0c3-126">Requerido por OLE.</span><span class="sxs-lookup"><span data-stu-id="9f0c3-126">Required by OLE.</span></span> <span data-ttu-id="9f0c3-127">Si se especifica el parámetro `-event` o `-debug`, no será necesario especificar el parámetro `-embedding`, ya que ese parámetro se establece internamente.</span><span class="sxs-lookup"><span data-stu-id="9f0c3-127">If the `-event` or `-debug` parameter are specified, it is not necessary to specify the `-embedding` parameter, since that parameter is set internally.</span></span>|  
|<span data-ttu-id="9f0c3-128">-event \<eventname></span><span class="sxs-lookup"><span data-stu-id="9f0c3-128">-event \<eventname></span></span>|<span data-ttu-id="9f0c3-129">Abra el evento con este nombre y señalice cuando PresentationHost. exe esté inicializado y listo para hospedar contenido de WPF.</span><span class="sxs-lookup"><span data-stu-id="9f0c3-129">Open the event with this name and signal it when PresentationHost.exe is initialized and ready to host WPF content.</span></span> <span data-ttu-id="9f0c3-130">PresentationHost.exe finalizará si se produce un error al abrir el evento como, por ejemplo, si este no se ha creado todavía.</span><span class="sxs-lookup"><span data-stu-id="9f0c3-130">PresentationHost.exe will terminate if there was an error opening the event, such as if it has not already been created.</span></span>|  
|<span data-ttu-id="9f0c3-131">-launchApplication \<url></span><span class="sxs-lookup"><span data-stu-id="9f0c3-131">-launchApplication \<url></span></span>|<span data-ttu-id="9f0c3-132">Inicia una aplicación ClickOnce independiente desde la dirección URL especificada.</span><span class="sxs-lookup"><span data-stu-id="9f0c3-132">Launches a standalone ClickOnce application from the specified URL.</span></span> <span data-ttu-id="9f0c3-133">Se aplican las directivas de seguridad de Internet Explorer y WinINet relativas a las aplicaciones .NET.</span><span class="sxs-lookup"><span data-stu-id="9f0c3-133">Internet Explorer and WinINet security policy concerning .NET applications are applied.</span></span>|  
  
## <a name="scenarios"></a><span data-ttu-id="9f0c3-134">Escenarios</span><span class="sxs-lookup"><span data-stu-id="9f0c3-134">Scenarios</span></span>  
  
### <a name="shell-handler"></a><span data-ttu-id="9f0c3-135">Controlador de shell</span><span class="sxs-lookup"><span data-stu-id="9f0c3-135">Shell Handler</span></span>  
 `PresentationHost.exe example.xbap`  
  
### <a name="mime-handler"></a><span data-ttu-id="9f0c3-136">Controlador de MIME</span><span class="sxs-lookup"><span data-stu-id="9f0c3-136">MIME Handler</span></span>  
 `PresentationHost.exe -embedding example.xbap`  
  
### <a name="visual-studio-debugging"></a><span data-ttu-id="9f0c3-137">Depuración de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9f0c3-137">Visual Studio Debugging</span></span>  
 `PresentationHost.exe -debug example.xbap`  
  
### <a name="visual-studio-debugging-in-zone"></a><span data-ttu-id="9f0c3-138">Depuración de Visual Studio en Zone</span><span class="sxs-lookup"><span data-stu-id="9f0c3-138">Visual Studio Debugging In Zone</span></span>  
 `PresentationHost.exe -debug -debugSecurityZoneURL http://www.example.com c:\folderpath\example.xbap`  
  
## <a name="see-also"></a><span data-ttu-id="9f0c3-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f0c3-139">See also</span></span>

- [<span data-ttu-id="9f0c3-140">Seguridad</span><span class="sxs-lookup"><span data-stu-id="9f0c3-140">Security</span></span>](../security-wpf.md)
