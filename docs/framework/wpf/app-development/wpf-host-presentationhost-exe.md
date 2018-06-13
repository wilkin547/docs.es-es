---
title: WPF Host (PresentationHost.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Host application [WPF]
- PresentationHost.exe
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
ms.openlocfilehash: ca8198e17bec62866b6a58e6fd14ea468308f48b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552693"
---
# <a name="wpf-host-presentationhostexe"></a>WPF Host (PresentationHost.exe)
Host de Windows Presentation Foundation (WPF) (PresentationHost.exe) es la aplicación que permite [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aplicaciones se alojen en los exploradores compatibles (incluidos [!INCLUDE[TLA#tla_ie6](../../../../includes/tlasharptla-ie6-md.md)] y versiones posteriores). De forma predeterminada, el Host de Windows Presentation Foundation (WPF) está registrado como el shell y [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] controlador para hospedadas en explorador [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] contenido, que incluye:  
  
-   Archivos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dinámicos (sin compilar) (.xaml).  
  
-   [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] (.xbap).  
  
 Para los archivos de estos tipos, el Host de Windows Presentation Foundation (WPF):  
  
-   Inicia el registrado [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] controlador para hospedar el contenido de Windows Presentation Foundation (WPF).  
  
-   Carga las versiones correctas de los necesarios [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] y ensamblados de Windows Presentation Foundation (WPF).  
  
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
