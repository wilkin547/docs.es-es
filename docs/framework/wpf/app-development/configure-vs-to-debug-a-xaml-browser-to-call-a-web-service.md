---
title: "C&#243;mo: Configurar Visual Studio para depurar una aplicaci&#243;n de explorador XAML y llamar a un servicio Web | Microsoft Docs"
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
  - "configurar Visual Studio para depurar aplicaciones de explorador XAML [WPF]"
  - "configurar Visual Studio para depurar XBAP [WPF]"
  - "excepciones de seguridad durante la depuración de XBAP [WPF]"
  - "depurar XBAP que llaman a un servicio Web [WPF]"
  - "excepción de seguridad de XBAP [WPF], depurar"
ms.assetid: fd1db082-a7bb-4c4b-9331-6ad74a0682d0
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Configurar Visual Studio para depurar una aplicaci&#243;n de explorador XAML y llamar a un servicio Web
Las [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] se ejecutan dentro de un recinto de seguridad de confianza parcial que está restringido al conjunto de permisos de la zona Internet.  Este conjunto de permisos restringe las llamadas a aquellos servicios Web que se encuentren en el sitio de origen de la aplicación [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  Sin embargo, al depurar una [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] desde [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)], no se considera que tiene el mismo sitio de origen que el servicio Web al que hace referencia.  Esto hace que se inicien excepciones de seguridad cuando la [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] intenta llamar al servicio Web.  Sin embargo, se puede configurar un proyecto [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] de [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] para simular que tiene el mismo sitio de origen que el servicio Web al que llama durante la depuración.  Esto permite que la [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] llame sin ningún riesgo al servicio Web sin que se inicien excepciones de seguridad.  
  
## Configurar Visual Studio  
 Para configurar [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] para depurar una [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] que llama a un servicio Web:  
  
1.  Con un proyecto seleccionado en el **Explorador de soluciones**, en el menú **Proyecto** haga clic en **Propiedades**.  
  
2.  En el **Diseñador de proyectos**, haga clic en la ficha **Depurar**.  
  
3.  En la sección **Acción de inicio**, seleccione **Programa externo de inicio** y escriba lo siguiente:  
  
     `C:\WINDOWS\System32\PresentationHost.exe`  
  
4.  En la sección **Opciones de inicio**, escriba lo siguiente en el cuadro de texto **Argumentos de la línea de comandos**:  
  
     `-debug`  *filename*  
  
     El valor de *nombre\_de\_archivo* para el parámetro **\-debug** es el nombre del archivo .xbap; por ejemplo:  
  
     `-debug c:\example.xbap`  
  
> [!NOTE]
>  Esta es la configuración predeterminada para las soluciones que se crean con la plantilla del proyecto [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] de [!INCLUDE[TLA2#tla_visualstu2005](../../../../includes/tla2sharptla-visualstu2005-md.md)].  
  
1.  Con un proyecto seleccionado en el **Explorador de soluciones**, en el menú **Proyecto** haga clic en **Propiedades**.  
  
2.  En el **Diseñador de proyectos**, haga clic en la ficha **Depurar**.  
  
3.  En la sección **Opciones de inicio**, agregue el parámetro de línea de comandos siguiente al cuadro de texto **Argumentos de la línea de comandos**:  
  
     `-debugSecurityZoneURL`  *URL*  
  
     El valor de *URL* del parámetro **\-debugSecurityZoneURL** es la [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] de la ubicación que desea indicar como sitio de origen simulado de la aplicación.  
  
 A modo de ejemplo, supongamos que una [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] utiliza un servicio Web con la [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] siguiente:  
  
 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`  
  
 La [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] del sitio de origen de este servicio Web es:  
  
 `http://services.msdn.microsoft.com`  
  
 Por consiguiente, el parámetro de línea de comandos **\-debugSecurityZoneURL** completo con su valor es:  
  
 `-debugSecurityZoneURL http://services.msdn.microsoft.com`  
  
## Vea también  
 [WPF Host \(PresentationHost.exe\)](../../../../docs/framework/wpf/app-development/wpf-host-presentationhost-exe.md)