---
title: Procedimiento Configurar Visual Studio para depurar una aplicación de explorador XAML y llamar a un servicio web
ms.date: 03/30/2017
helpviewer_keywords:
- debugging XBAPs that call a Web service [WPF]
- debugging security exceptions for XBAPs [WPF]
- security exception for XBAPs [WPF], debugging
- configuring Visual Studio to debug XAML browser applications [WPF]
- configuring Visual Studio to debug XBAPs [WPF]
ms.assetid: fd1db082-a7bb-4c4b-9331-6ad74a0682d0
ms.openlocfilehash: dcaabf9ecd47bc88095e92aa8ed28ad5f13fd1dc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59314378"
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a>Procedimiento Configurar Visual Studio para depurar una aplicación de explorador XAML y llamar a un servicio web
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] ejecutar en un recinto de seguridad de confianza parcial está restringido para el conjunto de permisos de zona de Internet. Este conjunto de permisos restringe las llamadas a solo servicios Web que se encuentran en el [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] sitio de origen de la aplicación. Cuando un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] se depura desde Visual Studio 2005, sin embargo, no se considera que tienen el mismo sitio de origen como el servicio Web, las referencias. Este excepciones de seguridad de las causas que se genera cuando el [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] intenta llamar al servicio Web. Sin embargo, un Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] proyecto puede configurarse para simular que tiene el mismo sitio de origen que el servicio Web que llama durante la depuración. Esto permite la [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] llame al servicio Web sin ningún riesgo sin producir excepciones de seguridad.

## <a name="configuring-visual-studio"></a>Configuración de Visual Studio
 Para configurar Visual Studio 2005 para depurar un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] que llama a un servicio Web:

1. Seleccione un proyecto en el **Explorador de soluciones**y, en el menú **Proyecto** , haga clic en **Propiedades**.

2. En el **Diseñador de proyectos**, haga clic en el **depurar** ficha.

3. En el **acción de inicio** sección, seleccione **iniciar programa externo** y escriba lo siguiente:

     `C:\WINDOWS\System32\PresentationHost.exe`

4. En el **opciones de inicio** sección, escriba lo siguiente en el **argumentos de línea de comandos** cuadro de texto:

     `-debug`  *filename*

     El *filename* valor para el **-depurar** parámetro es el nombre de archivo .xbap; por ejemplo:

     `-debug c:\example.xbap`

> [!NOTE]
>  Esta es la configuración predeterminada para las soluciones creadas con Visual Studio 2005 [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] plantilla de proyecto.

1. Seleccione un proyecto en el **Explorador de soluciones**y, en el menú **Proyecto** , haga clic en **Propiedades**.

2. En el **Diseñador de proyectos**, haga clic en el **depurar** ficha.

3. En el **opciones de inicio** sección, agregue el siguiente parámetro de línea de comandos para el **argumentos de línea de comandos** cuadro de texto:

     `-debugSecurityZoneURL`  *URL*

     El *URL* valor para el **- debugSecurityZoneURL** parámetro es el [!INCLUDE[TLA#tla_url](../../../../includes/tlasharptla-url-md.md)] para la ubicación que desee simular como sitio de origen de la aplicación.

 Por ejemplo, considere la posibilidad de un [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] que utiliza un servicio Web con el siguiente [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)]:

 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`

 El sitio de origen [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] para este sitio Web de servicio es:

 `http://services.msdn.microsoft.com`

 Por lo tanto, toda **- debugSecurityZoneURL** valor y parámetro de línea de comandos es:

 `-debugSecurityZoneURL http://services.msdn.microsoft.com`

## <a name="see-also"></a>Vea también

- [WPF Host (PresentationHost.exe)](wpf-host-presentationhost-exe.md)
