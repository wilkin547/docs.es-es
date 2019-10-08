---
title: WPF Host (PresentationHost.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Host application [WPF]
- PresentationHost.exe
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
ms.openlocfilehash: c1c26b49a33a58189f66e7b938333f362e467853
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002151"
---
# <a name="wpf-host-presentationhostexe"></a>WPF Host (PresentationHost.exe)
Host de Windows Presentation Foundation (WPF) (PresentationHost. exe) es la aplicación que permite hospedar aplicaciones [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] en exploradores compatibles (incluido Microsoft Internet Explorer 6 y versiones posteriores). De forma predeterminada, el host de Windows Presentation Foundation (WPF) se registra como el controlador de Shell y MIME para el contenido hospedado en el explorador [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], que incluye:  
  
- Archivos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dinámicos (sin compilar) (.xaml).  
  
- [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] (.xbap).  
  
 En el caso de los archivos de estos tipos, el host de Windows Presentation Foundation (WPF):  
  
- Inicia el controlador HTML registrado para hospedar el contenido de Windows Presentation Foundation (WPF).  
  
- Carga las versiones correctas de los ensamblados Common Language Runtime (CLR) y Windows Presentation Foundation (WPF) necesarios.  
  
- Garantiza que los niveles de permisos adecuados para la zona de implementación están en vigor.  
  
 Este tema describe los parámetros de la línea de comandos que se pueden utilizar con PresentationHost.exe.  
  
## <a name="usage"></a>Uso  
 `PresentationHost.exe [parameters] uri|filename`  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Descripción|  
|---------------|-----------------|  
|filename|Ruta al archivo que se va a activar. También puede ser un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].|  
|-debug|Al activar una aplicación, no la confirma ni la ejecuta desde el almacén. Esto sólo funciona cuando se activa un archivo local.|  
|-debugSecurityZoneURL \<url>|Se usa con un valor de dirección URL para indicar a PresentationHost. exe que se debe depurar una aplicación como si se hubiera implementado desde la dirección URL especificada. Esto determina la zona de implementación y el sitio de origen.|  
|-embedding|Requerido por OLE. Si se especifica el parámetro `-event` o `-debug`, no será necesario especificar el parámetro `-embedding`, ya que ese parámetro se establece internamente.|  
|-event \<eventname>|Abra el evento con este nombre y señálelo cuando PresentationHost.exe se inicialice y esté listo para hospedar el contenido [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. PresentationHost.exe finalizará si se produce un error al abrir el evento como, por ejemplo, si este no se ha creado todavía.|  
|-launchApplication \<url>|Inicia una aplicación ClickOnce independiente desde la dirección URL especificada. Se aplican las directivas de seguridad de Internet Explorer y WinINet relativas a las aplicaciones .NET.|  
  
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
