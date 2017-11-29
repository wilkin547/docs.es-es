---
title: "Cómo: Configurar Visual Studio para depurar una aplicación de explorador XAML y llamar a un servicio Web"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging XBAPs that call a Web service [WPF]
- debugging security exceptions for XBAPs [WPF]
- security exception for XBAPs [WPF], debugging
- configuring Visual Studio to debug XAML browser applications [WPF]
- configuring Visual Studio to debug XBAPs [WPF]
ms.assetid: fd1db082-a7bb-4c4b-9331-6ad74a0682d0
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5db89cf6220f086d2d71b99f3e6440e584d6a5d7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a>Cómo: Configurar Visual Studio para depurar una aplicación de explorador XAML y llamar a un servicio Web
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]ejecutar dentro de un espacio aislado de seguridad de confianza parcial que está restringido para el conjunto de permisos de zona de Internet. Este conjunto de permisos restringe llamadas al servicio Web para que solo los servicios Web que se encuentran en el [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] sitio de la aplicación de origen. Cuando un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] está depurando desde [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)], aunque no se considera que tienen el mismo sitio de origen como el servicio Web las referencias. Excepciones de seguridad de este causas que se genera cuando el [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] intenta llamar al servicio Web. Sin embargo, un [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] proyecto puede configurarse para simular que tiene el mismo sitio de origen que el servicio Web que se llama durante la depuración. Esto permite la [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] para llamar sin ningún riesgo al servicio Web sin producir excepciones de seguridad.  
  
## <a name="configuring-visual-studio"></a>Configurar Visual Studio  
 Para configurar [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] para depurar un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] que llama a un servicio Web:  
  
1.  Seleccione un proyecto en el **Explorador de soluciones**y, en el menú **Proyecto** , haga clic en **Propiedades**.  
  
2.  En el **Diseñador de proyectos**, haga clic en el **depurar** ficha.  
  
3.  En el **acción de inicio** sección, seleccione **programa externo de inicio** y escriba lo siguiente:  
  
     `C:\WINDOWS\System32\PresentationHost.exe`  
  
4.  En el **opciones de inicio** sección, escriba lo siguiente en el **argumentos de línea de comandos** cuadro de texto:  
  
     `-debug`  *nombre de archivo*  
  
     El *filename* valor para el **-depurar** parámetro es el nombre de archivo de XBAP; por ejemplo:  
  
     `-debug c:\example.xbap`  
  
> [!NOTE]
>  Esta es la configuración predeterminada para las soluciones que se crean con el [!INCLUDE[TLA2#tla_visualstu2005](../../../../includes/tla2sharptla-visualstu2005-md.md)] [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] plantilla de proyecto.  
  
1.  Seleccione un proyecto en el **Explorador de soluciones**y, en el menú **Proyecto** , haga clic en **Propiedades**.  
  
2.  En el **Diseñador de proyectos**, haga clic en el **depurar** ficha.  
  
3.  En el **opciones de inicio** sección, agregue el siguiente parámetro de línea de comandos para la **argumentos de línea de comandos** cuadro de texto:  
  
     `-debugSecurityZoneURL`  *URL*  
  
     El *URL* valor para el **- debugSecurityZoneURL** parámetro es la [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] para la ubicación que desee simular como sitio de origen de la aplicación.  
  
 Por ejemplo, considere la posibilidad de un [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] que utiliza un servicio Web con el siguiente [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:  
  
 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`  
  
 El sitio de origen [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] para este sitio Web es el servicio:  
  
 `http://services.msdn.microsoft.com`  
  
 Por lo tanto, la sección completa **- debugSecurityZoneURL** parámetro de línea de comandos y el valor es:  
  
 `-debugSecurityZoneURL http://services.msdn.microsoft.com`  
  
## <a name="see-also"></a>Vea también  
 [WPF Host (PresentationHost.exe)](../../../../docs/framework/wpf/app-development/wpf-host-presentationhost-exe.md)
