---
title: WPF Host (PresentationHost.exe)
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Host application [WPF]
- PresentationHost.exe
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
ms.openlocfilehash: bda7efbb1b7a4760199215bdb58c12b3063e290c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743402"
---
# <a name="wpf-host-presentationhostexe"></a>WPF Host (PresentationHost.exe)
El host de Windows Presentation Foundation (WPF) (PresentationHost. exe) es la aplicación que permite hospedar aplicaciones WPF en exploradores compatibles (incluido Microsoft Internet Explorer 6 y versiones posteriores). De forma predeterminada, el host de Windows Presentation Foundation (WPF) se registra como el controlador de Shell y MIME para el contenido WPF hospedado en el explorador, que incluye:  
  
- Archivos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dinámicos (sin compilar) (.xaml).  
  
- Aplicación de explorador XAML (XBAP) (. XBAP).  
  
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
|filename|Ruta al archivo que se va a activar. También puede ser un URI.|  
|-debug|Al activar una aplicación, no la confirma ni la ejecuta desde el almacén. Esto sólo funciona cuando se activa un archivo local.|  
|-debugSecurityZoneURL \<url>|Se usa con un valor de dirección URL para indicar a PresentationHost. exe que se debe depurar una aplicación como si se hubiera implementado desde la dirección URL especificada. Esto determina la zona de implementación y el sitio de origen.|  
|-embedding|Requerido por OLE. Si se especifica el parámetro `-event` o `-debug`, no será necesario especificar el parámetro `-embedding`, ya que ese parámetro se establece internamente.|  
|-event \<eventname>|Abra el evento con este nombre y señalice cuando PresentationHost. exe esté inicializado y listo para hospedar contenido de WPF. PresentationHost.exe finalizará si se produce un error al abrir el evento como, por ejemplo, si este no se ha creado todavía.|  
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
  
## <a name="see-also"></a>Consulte también

- [Seguridad](../security-wpf.md)
