---
title: "Implementar una aplicación de WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WPF applications [WPF], deployment
- deployment [WPF], applications
ms.assetid: 12cadca0-b32c-4064-9a56-e6a306dcc76d
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 860549d444bcef3a25af753923955b2e3e1a3677
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="deploying-a-wpf-application-wpf"></a>Implementar una aplicación de WPF
Después de compilar aplicaciones de [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)], se tienen que implementar. [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] y [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] incluyen varias tecnologías de implementación. La tecnología de implementación que se usa para implementar una aplicación de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] depende del tipo de esta. En este tema se proporciona alguna información general sobre cada tecnología de implementación y su uso, además de los requisitos de implementación de cada tipo de aplicación de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
   
<a name="Deployment_Technologies"></a>   
## <a name="deployment-technologies"></a>Tecnologías de implementación  
 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] y [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] incluyen varias tecnologías de implementación, entre las que se incluyen las siguientes:  
  
-   Implementación de XCopy.  
  
-   Implementación de [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)].  
  
-   Implementación de [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)].  
  
<a name="XCopy_Deployment"></a>   
### <a name="xcopy-deployment"></a>Implementación de XCopy  
 La implementación de XCopy se refiere al uso del programa de línea de comandos XCopy para copiar los archivos de una ubicación a otra. La implementación de XCopy es adecuada en las circunstancias siguientes:  
  
-   La aplicación es autónoma. No necesita actualizar el cliente para ejecutarse.  
  
-   Los archivos de la aplicación se deben mover de una ubicación a otra; por ejemplo, de la ubicación de compilación (disco local, recurso compartido de archivos [!INCLUDE[TLA2#tla_unc](../../../../includes/tla2sharptla-unc-md.md)], etc.) a la ubicación de publicación (sitio web, recurso compartido de archivos [!INCLUDE[TLA2#tla_unc](../../../../includes/tla2sharptla-unc-md.md)], etc.).  
  
-   La aplicación no necesita la integración en el Shell (acceso directo del menú de Inicio, icono de escritorio, etc.).  
  
 Aunque XCopy es adecuado para escenarios de implementación simples, presenta limitaciones cuando se requieren funciones de implementación más complejas. En particular, al usar Xcopy se provoca una sobrecarga al crear, ejecutar y mantener los scripts necesarios para administrar la implementación de una manera robusta. Además, XCopy no admite el control de versiones, la desinstalación ni la reversión.  
  
<a name="Windows_Installer"></a>   
### <a name="windows-installer"></a>Windows Installer  
 [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] permite empaquetar las aplicaciones como aplicaciones ejecutables autónomas que se pueden distribuir con facilidad a los clientes y ejecutar. Además, [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] se instala con [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] y habilita la integración con el escritorio, el menú Inicio y el panel de control Programas.  
  
 [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] simplifica la instalación y desinstalación de aplicaciones, pero no proporciona los medios para asegurarse de que las aplicaciones instaladas se mantengan actualizadas desde el punto de vista de su versión.  
  
 Para obtener más información sobre [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)], vea [Implementación de Windows Installer](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0).  
  
<a name="ClickOnce_Deployment"></a>   
### <a name="clickonce-deployment"></a>Implementación ClickOnce  
 [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] habilita la implementación de aplicaciones de estilo web para aplicaciones que no son de web. Las aplicaciones se publican e implementan para Web o para servidores de archivos. Aunque [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] no admite la gama completa de características de cliente que sí poseen las aplicaciones instaladas con [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)], admite un subconjunto que incluye lo siguiente:  
  
-   Integración con el menú Inicio y el panel de control de Programas.  
  
-   Control de versiones, reversión y desinstalación.  
  
-   Modo de instalación en línea, que siempre inicia una aplicación desde la ubicación de implementación.  
  
-   Actualización automática cuando se publican nuevas versiones.  
  
-   Registro de extensiones de archivo.  
  
 Para obtener más información sobre [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)], vea [Seguridad e implementación ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment).  
  
<a name="Deploying_WPF_Applications"></a>   
## <a name="deploying-wpf-applications"></a>Implementar aplicaciones de WPF  
 Las opciones de implementación para una aplicación de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] dependen del tipo de aplicación. Desde una perspectiva de implementación, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] tiene tres tipos de aplicación significativos:  
  
-   Aplicaciones independientes.  
  
-   Aplicaciones [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] solo de marcado.  
  
-   [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)].  
  
<a name="Deploying_Standalone_Applications"></a>   
### <a name="deploying-standalone-applications"></a>Implementar aplicaciones independientes  
 Las aplicaciones independientes se implementan usando [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] o [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)]. De cualquier modo, las aplicaciones independientes requieren plena confianza para ejecutarse. La plena confianza se concede automáticamente a las aplicaciones independientes que se implementan mediante [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)]. Las aplicaciones independientes que se implementan mediante [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] no reciben la plena confianza de manera automática. En lugar de ello, [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] muestra un cuadro de diálogo de advertencia de seguridad que el usuario debe aceptar antes de instalar cualquier aplicación independiente. Si el usuario acepta, se instala la aplicación independiente y se le otorgan permisos de plena confianza. En caso contrario, no se instala la aplicación independiente.  
  
<a name="Deploying_Markup_Only_XAML_Applications"></a>   
### <a name="deploying-markup-only-xaml-applications"></a>Implementar aplicaciones XAML solo de marcado  
 Las páginas [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] solo de marcado se suelen publicar en servidores web, al igual que las páginas [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)], y se pueden ver mediante [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)]. Las páginas [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] solo de marcado se ejecutan dentro de un recinto de seguridad de confianza parcial con restricciones definidas por el conjunto de permisos de zona de Internet. Esto proporciona un recinto de seguridad equivalente al de las aplicaciones web basadas en [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)].  
  
 Para obtener más información sobre los cambios en materia de seguridad que se han realizado en las aplicaciones [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], vea [Seguridad (WPF)](../../../../docs/framework/wpf/security-wpf.md).  
  
 Las páginas [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] solo de marcado se pueden instalar en el sistema de archivos local usando XCopy o [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)]. Estas páginas se pueden ver usando [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] o el Explorador de [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)].  
  
 Para obtener más información sobre XAML, vea [Información general sobre XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).  
  
<a name="Deploying_XAML_Browser_Applications"></a>   
### <a name="deploying-xaml-browser-applications"></a>Implementar aplicaciones de explorador XAML  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] son aplicaciones compiladas que necesitan los tres archivos siguientes para implementarse:  
  
-   *nombreDeAplicación*.exe: el archivo de aplicación del ensamblado ejecutable.  
  
-   *nombreDeAplicación*.xbap: el manifiesto de implementación.  
  
-   *nombreDeAplicación*.exe.manifest: el manifiesto de la aplicación.  
  
> [!NOTE]
>  Para obtener más información sobre los manifiestos de implementación y de aplicación, vea [Compilar una aplicación de WPF (WPF)](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md).  
  
 Estos archivos se crean al compilar una [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]. Para obtener más información, vea [Cómo: Crear un nuevo proyecto de aplicación de explorador de WPF](http://msdn.microsoft.com/en-us/72ef4d90-e163-42a1-8df0-ea7ccfd1901f). Al igual que las páginas [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] solo de marcado, las [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] se suelen publicar en un servidor web y se ven mediante [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)].  
  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] se puede implementar en los clientes usando cualquiera de las técnicas de implementación. En cambio, se recomienda [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] porque proporciona las siguientes capacidades:  
  
1.  Actualizaciones automáticas cuando se publica una nueva versión.  
  
2.  Privilegios aumentados para [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] que se ejecuta con plena confianza.  
  
 De manera predeterminada, ClickOnce publica los archivos de aplicación con la extensión .deploy. Esto puede ser problemático, pero también puede deshabilitarse. Para obtener más información, vea [Problemas de configuración de servidor y cliente en implementaciones de ClickOnce](/visualstudio/deployment/server-and-client-configuration-issues-in-clickonce-deployments).  
  
 Para obtener más información sobre la manera de implementar [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)], vea [Información general sobre las aplicaciones de explorador XAML de WPF](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md).  
  
<a name="Installing__NET_Framework_3_0"></a>   
## <a name="installing-the-net-framework"></a>Instalar .NET Framework  
 Para ejecutar una aplicación de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] debe estar instalado en el cliente. [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] detecta automáticamente si los clientes tienen [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] instalado cuando se ven aplicaciones [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] hospedadas en el explorador. Si [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] no está instalado, [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] pide al usuario que lo instale.  
  
 Para detectar si [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] está instalado, [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] incluye una aplicación de arranque que se registra como controlador [!INCLUDE[TLA#tla_mime](../../../../includes/tlasharptla-mime-md.md)] de reserva para los archivos de contenido con las extensiones siguientes: .xaml, .xps, .xbap y .application. Cuando se navega a estos tipos de archivo y [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] no está instalado en el cliente, la aplicación de arranque solicita permiso para instalarlo. Si no se concede este permiso, no se instala [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] ni la aplicación.  
  
 Si se concede el permiso, [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] descarga e instala [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] mediante [!INCLUDE[TLA#tla_bits](../../../../includes/tlasharptla-bits-md.md)]. Después de instalar [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] correctamente, se abre el archivo solicitado originalmente en una nueva ventana del explorador.  
  
 La detección automática de [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] está disponible en los clientes de [!INCLUDE[TLA#tla_longhorn](../../../../includes/tlasharptla-longhorn-md.md)], [!INCLUDE[TLA#tla_winxpsp2](../../../../includes/tlasharptla-winxpsp2-md.md)] y [!INCLUDE[TLA#tla_winnetsvrfamsp1](../../../../includes/tlasharptla-winnetsvrfamsp1-md.md)] que tengan [!INCLUDE[TLA2#tla_ie7](../../../../includes/tla2sharptla-ie7-md.md)] o posterior instalado.  
  
 Para obtener más información, vea [Implementar .NET Framework y aplicaciones](../../../../docs/framework/deployment/index.md).  
  
## <a name="see-also"></a>Vea también  
 [Compilar una aplicación de WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)  
 [Seguridad](../../../../docs/framework/wpf/security-wpf.md)
