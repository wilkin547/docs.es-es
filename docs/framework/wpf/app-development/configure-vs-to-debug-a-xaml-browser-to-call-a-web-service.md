---
title: 'Cómo: Configurar Visual Studio para depurar una aplicación de explorador XAML y llamar a un servicio Web'
ms.date: 03/30/2017
helpviewer_keywords:
- debugging XBAPs that call a Web service [WPF]
- debugging security exceptions for XBAPs [WPF]
- security exception for XBAPs [WPF], debugging
- configuring Visual Studio to debug XAML browser applications [WPF]
- configuring Visual Studio to debug XBAPs [WPF]
ms.assetid: fd1db082-a7bb-4c4b-9331-6ad74a0682d0
ms.openlocfilehash: 27319179a9a30c5693f47039bf1e24c59adf0e68
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424649"
---
# <a name="how-to-configure-visual-studio-to-debug-a-xaml-browser-application-to-call-a-web-service"></a>Cómo: Configurar Visual Studio para depurar una aplicación de explorador XAML y llamar a un servicio Web
Las aplicaciones de explorador XAML (XBAP) se ejecutan en un espacio aislado de seguridad de confianza parcial que está restringido al conjunto de permisos de la zona de Internet. Este conjunto de permisos restringe las llamadas de servicio web solo a los servicios web que se encuentran en el sitio de origen de la aplicación XBAP. Sin embargo, cuando se depura una aplicación XBAP desde Visual Studio 2005, no se considera que tiene el mismo sitio de origen que el servicio Web al que hace referencia. Esto hace que se produzcan excepciones de seguridad cuando la aplicación XBAP intenta llamar al servicio Web. Sin embargo, se puede configurar un proyecto de [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] de Visual Studio 2005 para simular tener el mismo sitio de origen que el servicio Web al que llama durante la depuración. Esto permite que la aplicación XBAP llame de forma segura al servicio Web sin producir excepciones de seguridad.

## <a name="configuring-visual-studio"></a>Configuración de Visual Studio
 Para configurar Visual Studio 2005 para depurar una aplicación XBAP que llama a un servicio Web:

1. Seleccione un proyecto en el **Explorador de soluciones**y, en el menú **Proyecto** , haga clic en **Propiedades**.

2. En el **Diseñador de proyectos**, haga clic en la pestaña **depurar** .

3. En la sección **acción de inicio** , seleccione **programa externo de inicio** y escriba lo siguiente:

     `C:\WINDOWS\System32\PresentationHost.exe`

4. En la sección **Opciones de inicio** , escriba lo siguiente en el cuadro de texto argumentos de la línea de **comandos** :

     `-debug`  *nombrearchivo*

     El valor del *nombre de archivo* para el parámetro **-Debug** es el nombre de archivo. XBAP; por ejemplo:

     `-debug c:\example.xbap`

> [!NOTE]
> Esta es la configuración predeterminada para las soluciones que se crean con la plantilla de proyecto de [!INCLUDE[TLA#tla_wpfbrowserappproj](../../../../includes/tlasharptla-wpfbrowserappproj-md.md)] de Visual Studio 2005.

1. Seleccione un proyecto en el **Explorador de soluciones**y, en el menú **Proyecto** , haga clic en **Propiedades**.

2. En el **Diseñador de proyectos**, haga clic en la pestaña **depurar** .

3. En la sección **Opciones de inicio** , agregue el siguiente parámetro de línea de comandos al cuadro de texto argumentos de línea de **comandos** :

     `-debugSecurityZoneURL`  *URL*

     El valor de *dirección URL* para el parámetro **-debugSecurityZoneURL** es la dirección URL de la ubicación que desea simular como el sitio de origen de la aplicación.

 Como ejemplo, considere una aplicación de explorador XAML (XBAP) que usa un servicio Web con la siguiente dirección URL:

 `http://services.msdn.microsoft.com/ContentServices/ContentService.asmx`

 La dirección URL del sitio de origen de este servicio web es la siguiente:

 `http://services.msdn.microsoft.com`

 Por lo tanto, el valor y el parámetro de línea de comandos complete **-debugSecurityZoneURL** son:

 `-debugSecurityZoneURL http://services.msdn.microsoft.com`

## <a name="see-also"></a>Vea también

- [WPF Host (PresentationHost.exe)](wpf-host-presentationhost-exe.md)
