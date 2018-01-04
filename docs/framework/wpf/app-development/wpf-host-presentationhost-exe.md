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
ms.workload: dotnet
ms.openlocfilehash: 1c5a9df438353701932a3e732d6df28b08402ee8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="wpf-host-presentationhostexe"></a>WPF Host (PresentationHost.exe)
[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Host (PresentationHost.exe) es la aplicación que permite que las aplicaciones [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] se hospeden en exploradores compatibles (incluido [!INCLUDE[TLA#tla_ie6](../../../../includes/tlasharptla-ie6-md.md)] y versiones posteriores). De forma predeterminada, [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Host se registra como el shell y el controlador [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] para contenido [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] hospedado en el explorador, lo cual incluye:  
  
-   Archivos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dinámicos (sin compilar) (.xaml).  
  
-   [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] (.xbap).  
  
 Para estos tipos de archivos [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Host:  
  
-   Inicia el controlador de [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] registrado para hospedar el contenido [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)].  
  
-   Carga las versiones correctas de los ensamblados obligatorios [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] y [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)].  
  
-   Garantiza que los niveles de permisos adecuados para la zona de implementación están en vigor.  
  
 Este tema describe los parámetros de la línea de comandos que se pueden utilizar con PresentationHost.exe.  
  
## <a name="usage"></a>Uso  
 `PresentationHost.exe [parameters] uri|filename`  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Descripción|  
|---------------|-----------------|  
|filename|Ruta al archivo que se va a activar. También puede ser un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].|  
|-debug|Al activar una aplicación, no la confirma ni la ejecuta desde el almacén. Esto sólo funciona cuando se activa un archivo local.|  
|-debugSecurityZoneURL \<url>|Se utiliza con un valor [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] para indicar a PresentationHost.exe que una aplicación se debe depurar como si se hubiera implementado desde la [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] especificada. Esto determina la zona de implementación y el sitio de origen.|  
|-embedding|Requerido por OLE. Si se especifica el parámetro `-event` o `-debug`, no será necesario especificar el parámetro `-embedding`, ya que ese parámetro se establece internamente.|  
|-event \<eventname>|Abra el evento con este nombre y señálelo cuando PresentationHost.exe se inicialice y esté listo para hospedar el contenido [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. PresentationHost.exe finalizará si se produce un error al abrir el evento como, por ejemplo, si este no se ha creado todavía.|  
|-launchApplication \<url>|Inicia una aplicación [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] independiente desde la dirección URL especificada. Se aplican las directivas de seguridad [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] y WinINet relativas a las aplicaciones .NET.|  
  
## <a name="scenarios"></a>Escenarios  
  
### <a name="shell-handler"></a>Controlador de shell  
 `PresentationHost.exe example.xbap`  
  
### <a name="mime-handler"></a>Controlador de MIME  
 `PresentationHost.exe -embedding example.xbap`  
  
### <a name="visual-studio-debugging"></a>Depuración de Visual Studio  
 `PresentationHost.exe -debug example.xbap`  
  
### <a name="visual-studio-debugging-in-zone"></a>Depuración de Visual Studio en Zone  
 `PresentationHost.exe -debug -debugSecurityZoneURL http://www.example.com c:\folderpath\example.xbap`  
  
## <a name="see-also"></a>Vea también  
 [Seguridad](../../../../docs/framework/wpf/security-wpf.md)
