---
title: "WPF Host (PresentationHost.exe) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "PresentationHost.exe"
  - "aplicación host de WPF"
ms.assetid: 3215bfa1-722c-4ac8-a7c5-bdd02d30afbd
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# WPF Host (PresentationHost.exe)
El host de [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] \(PresentationHost.exe\) es la aplicación que permite hospedar aplicaciones [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] en exploradores compatibles \(incluidos [!INCLUDE[TLA#tla_ie6](../../../../includes/tlasharptla-ie6-md.md)] y versiones posteriores\).  De manera predeterminada, el host de [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] se registra como el shell y controlador [!INCLUDE[TLA2#tla_mime](../../../../includes/tla2sharptla-mime-md.md)] para el contenido de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] hospedado por explorador, lo que incluye:  
  
-   Archivos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dinámicos \(.xaml\) \(sin compilar\).  
  
-   [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] \(.xbap\).  
  
 Para los archivos de estos tipos, el host de [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]:  
  
-   Inicia el controlador [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] registrado para hospedar el contenido de [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)].  
  
-   Carga las versiones correctas de los ensamblados necesarios de [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] y [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)].  
  
-   Se asegura de que se apliquen los niveles de permisos adecuados para la zona de implementación.  
  
 En este tema se describen los parámetros de línea de comandos que se pueden utilizar con PresentationHost.exe.  
  
## Uso  
 `PresentationHost.exe [parameters] uri|filename`  
  
## Parámetros  
  
|Parámetro|Descripción|  
|---------------|-----------------|  
|filename|Ruta de acceso del archivo que se va a activar.  También puede ser un [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].|  
|\-debug|Al activar una aplicación, no se confirma en el almacén ni se ejecuta desde él.  Únicamente funciona cuando se activa un archivo local.|  
|\-debugSecurityZoneURL \<url\>|Se utiliza con un valor de [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] para indicar a PresentationHost.exe que una aplicación se debe depurar como si se implementara desde la [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] especificada.  Determina la zona de implementación y el sitio de origen.|  
|\-embedding|Requerido por OLE.  Si se especifica el parámetro `-event` o `-debug`, no es necesario especificar el parámetro `-embedding`, puesto que se establece internamente.|  
|\-event \<nombreEvento\>|Abre el evento de este nombre y lo señala cuando PresentationHost.exe se inicializa y queda listo para hospedar contenido de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  PresentationHost.exe finalizará si se produce un error al abrir el evento, por ejemplo, si aún no se ha creado.|  
|\-launchApplication \<url\>|Inicia una aplicación [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] independiente desde la dirección URL especificada.  Se aplican las directivas de seguridad de [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] y WinINet con respecto a las aplicaciones de .NET.|  
  
## Escenarios  
  
### Controlador de shell  
 `PresentationHost.exe example.xbap`  
  
### Controlador MIME  
 `PresentationHost.exe -embedding example.xbap`  
  
### Depuración en Visual Studio  
 `PresentationHost.exe -debug example.xbap`  
  
### Depuración en Visual Studio en una zona  
 `PresentationHost.exe -debug -debugSecurityZoneURL http://www.example.com c:\folderpath\example.xbap`  
  
## Vea también  
 [Seguridad](../../../../docs/framework/wpf/security-wpf.md)