---
title: WPF Host (PresentationHost.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Host application [WPF]
- PresentationHost.exe
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
ms.openlocfilehash: 586d306d0f375241c9382e1e24cf1af75b990ba9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122868"
---
# <a name="wpf-host-presentationhostexe"></a>WPF Host (PresentationHost.exe)
Windows Presentation Foundation (WPF) de Host (PresentationHost.exe) es la aplicación que permite [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aplicaciones para alojarlas en exploradores compatibles (incluido [!INCLUDE[TLA#tla_ie6](../../../../includes/tlasharptla-ie6-md.md)] y versiones posteriores). De forma predeterminada, el Host de Windows Presentation Foundation (WPF) se registra como el shell y [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] controlador para hospedadas en explorador [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] contenido, que incluye:  
  
-   Archivos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dinámicos (sin compilar) (.xaml).  
  
-   [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] (.xbap).  
  
 Para los archivos de estos tipos, el Host de Windows Presentation Foundation (WPF):  
  
-   Inicia registrado [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] controlador para hospedar el contenido de Windows Presentation Foundation (WPF).  
  
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
|-launchApplication \<url>|Inicia una aplicación [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] independiente desde la dirección URL especificada. [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] y se aplican la directiva de seguridad de WinINet relativas a las aplicaciones. NET.|  
  
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

- [Seguridad](../security-wpf.md)
