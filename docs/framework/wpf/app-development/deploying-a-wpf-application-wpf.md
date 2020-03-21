---
title: Implementación de una aplicación
ms.date: 03/30/2017
helpviewer_keywords:
- WPF applications [WPF], deployment
- deployment [WPF], applications
ms.assetid: 12cadca0-b32c-4064-9a56-e6a306dcc76d
ms.openlocfilehash: 54d14503a0f65bb50f2dfb14d40af3b47d51589c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186312"
---
# <a name="deploy-a-wpf-application"></a>Implementar una aplicación WPF

Después de compilar las aplicaciones de Windows Presentation Foundation (WPF), es necesario implementarlas. Windows y .NET Framework incluyen varias tecnologías de implementación. La tecnología de implementación que se usa para implementar una aplicación WPFWPF depende del tipo de aplicación. En este tema se proporciona una breve descripción general de cada tecnología de implementación y cómo se usan junto con los requisitos de implementación de cada tipo de aplicación WPFWPF.

<a name="Deployment_Technologies"></a>
## <a name="deployment-technologies"></a>Tecnologías de implementación  
 Windows y .NET Framework incluyen varias tecnologías de implementación, entre ellas:  
  
- Implementación de XCopy.  
  
- Implementación de Windows Installer.  
  
- Implementación ClickOnce.  
  
<a name="XCopy_Deployment"></a>
### <a name="xcopy-deployment"></a>Implementación de XCopy  
 La implementación de XCopy se refiere al uso del programa de línea de comandos XCopy para copiar los archivos de una ubicación a otra. La implementación de XCopy es adecuada en las circunstancias siguientes:  
  
- La aplicación es autónoma. No necesita actualizar el cliente para ejecutarse.  
  
- Los archivos de aplicación se deben mover de una ubicación a otra, como desde una ubicación de compilación (disco local, recurso compartido de archivos UNC, etc.) a una ubicación de publicación (sitio web, recurso compartido de archivos UNC, etc.).  
  
- La aplicación no necesita la integración en el Shell (acceso directo del menú de Inicio, icono de escritorio, etc.).  
  
 Aunque XCopy es adecuado para escenarios de implementación simples, presenta limitaciones cuando se requieren funciones de implementación más complejas. En particular, al usar Xcopy se provoca una sobrecarga al crear, ejecutar y mantener los scripts necesarios para administrar la implementación de una manera robusta. Además, XCopy no admite el control de versiones, la desinstalación ni la reversión.  
  
<a name="Windows_Installer"></a>
### <a name="windows-installer"></a>Windows Installer  
 Windows Installer permite empaquetar las aplicaciones como ejecutables independientes que se pueden distribuir fácilmente a los clientes y ejecutarse. Además, Windows Installer se instala con Windows y permite la integración con el escritorio, el menú Inicio y el panel de control Programas.  
  
 Windows Installer simplifica la instalación y desinstalación de aplicaciones, pero no proporciona facilidades para garantizar que las aplicaciones instaladas se mantengan actualizadas desde el punto de vista del control de versiones.  
  
 Para obtener más información acerca de Windows Installer, vea [Implementación](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop)de Windows Installer .
  
<a name="ClickOnce_Deployment"></a>
### <a name="clickonce-deployment"></a>Implementación ClickOnce  
 ClickOnce habilita la implementación de aplicaciones de estilo web para aplicaciones que no son Web. Las aplicaciones se publican e implementan para Web o para servidores de archivos. Aunque ClickOnce no admite la gama completa de características de cliente que hacen las aplicaciones instaladas por Windows Installer, sí admite un subconjunto que incluye lo siguiente:  
  
- Integración con el menú Inicio y el panel de control de Programas.  
  
- Control de versiones, reversión y desinstalación.  
  
- Modo de instalación en línea, que siempre inicia una aplicación desde la ubicación de implementación.  
  
- Actualización automática cuando se publican nuevas versiones.  
  
- Registro de extensiones de archivo.  
  
 Para obtener más información acerca de ClickOnce, vea [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).  
  
<a name="Deploying_WPF_Applications"></a>
## <a name="deploying-wpf-applications"></a>Implementar aplicaciones de WPF  
 Las opciones de implementación de una aplicación WPFDEPENDEN del tipo de aplicación. Desde una perspectiva de implementación, WPFWPF tiene tres tipos de aplicación significativos:  
  
- Aplicaciones independientes.  
  
- Aplicaciones [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] solo de marcado.  
  
- Aplicaciones de explorador XAML (XBAP).  
  
<a name="Deploying_Standalone_Applications"></a>
### <a name="deploying-standalone-applications"></a>Implementar aplicaciones independientes  
 Las aplicaciones independientes se implementan mediante ClickOnce o Windows Installer. De cualquier modo, las aplicaciones independientes requieren plena confianza para ejecutarse. La plena confianza se concede automáticamente a las aplicaciones independientes que se implementan con Windows Installer. Las aplicaciones independientes que se implementan mediante ClickOnce no se conceden automáticamente plena confianza. En su lugar, ClickOnce ClickOnce muestra un cuadro de diálogo de advertencia de seguridad que los usuarios deben aceptar antes de instalar una aplicación independiente. Si el usuario acepta, se instala la aplicación independiente y se le otorgan permisos de plena confianza. En caso contrario, no se instala la aplicación independiente.  
  
<a name="Deploying_Markup_Only_XAML_Applications"></a>
### <a name="deploying-markup-only-xaml-applications"></a>Implementar aplicaciones XAML solo de marcado  
 Las páginas de solo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] marcado normalmente se publican en servidores web, como páginas HTML, y se pueden ver mediante Internet Explorer. Las páginas [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] solo de marcado se ejecutan dentro de un recinto de seguridad de confianza parcial con restricciones definidas por el conjunto de permisos de zona de Internet. Esto proporciona un entorno limitado de seguridad equivalente a las aplicaciones web basadas en HTML.  
  
 Para obtener más información acerca de la seguridad para aplicaciones WPF, vea [Seguridad](../security-wpf.md).  
  
 Las páginas de solo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] marcado se pueden instalar en el sistema de archivos local mediante XCopy o Windows Installer. Estas páginas se pueden ver mediante Internet Explorer o Windows Explorer.  
  
 Para obtener más información sobre XAML, vea [Información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md).  
  
<a name="Deploying_XAML_Browser_Applications"></a>
### <a name="deploying-xaml-browser-applications"></a>Implementar aplicaciones de explorador XAML  
 Los XBAP son aplicaciones compiladas que requieren que se implementen los tres archivos siguientes:  
  
- *nombreDeAplicación*.exe: el archivo de aplicación del ensamblado ejecutable.  
  
- *nombreDeAplicación*.xbap: el manifiesto de implementación.  
  
- *nombreDeAplicación*.exe.manifest: el manifiesto de la aplicación.  
  
> [!NOTE]
> Para obtener más información sobre los manifiestos de implementación y de aplicación, vea [Compilar una aplicación de WPF (WPF)](building-a-wpf-application-wpf.md).  
  
 Estos archivos se producen cuando se crea un XBAP. Para obtener más información, vea [Cómo: Crear un nuevo proyecto de aplicación de explorador de WPF](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628663(v=vs.100)). Al igual [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] que las páginas de solo marcado, los XBAP normalmente se publican en un servidor Web y se visualizan mediante Internet Explorer.  
  
 Los XBAP se pueden implementar en los clientes mediante cualquiera de las técnicas de implementación. Sin embargo, ClickOnce se recomienda ya que proporciona las siguientes capacidades:  
  
1. Actualizaciones automáticas cuando se publica una nueva versión.  
  
2. Privilegios de elevación para el XBAP que se ejecuta con plena confianza.  
  
 De manera predeterminada, ClickOnce publica los archivos de aplicación con la extensión .deploy. Esto puede ser problemático, pero también puede deshabilitarse. Para obtener más información, vea [Problemas de configuración de servidor y cliente en implementaciones de ClickOnce](/visualstudio/deployment/server-and-client-configuration-issues-in-clickonce-deployments).  
  
 Para obtener más información acerca de la implementación de aplicaciones de explorador XAML (XBAP), vea Información general sobre aplicaciones [de explorador XAML de WPF](wpf-xaml-browser-applications-overview.md).  
  
<a name="Installing__NET_Framework_3_0"></a>
## <a name="installing-the-net-framework"></a>Instalar .NET Framework  
 Para ejecutar una aplicación WPF, Microsoft .NET Framework debe estar instalado en el cliente. Internet Explorer detecta automáticamente si los clientes se instalan con .NET Framework cuando se ven las aplicaciones hospedadas en el explorador WPFWPF. Si .NET Framework no está instalado, Internet Explorer solicita a los usuarios que lo instalen.  
  
 Para detectar si .NET Framework está instalado, Internet Explorer incluye una aplicación de arranque que está registrada como el controlador de extensiones de correo de Internet multipropósito (MIME) para archivos de contenido con las siguientes extensiones: .xaml, .xps, .xbap , y .application. Si navega a estos tipos de archivo y .NET Framework no está instalado en el cliente, la aplicación de arranque solicita permiso para instalarlo. Si no se proporciona permiso, ni .NET Framework ni la aplicación están instalados.  
  
 Si se concede permiso, Internet Explorer descarga e instala .NET Framework mediante Microsoft Background Intelligent Transfer Service (BITS). Después de la instalación correcta de .NET Framework, el archivo solicitado originalmente se abre en una nueva ventana del explorador.  
  
 Para obtener más información, vea [Implementar .NET Framework y aplicaciones](../../deployment/index.md).  
  
## <a name="see-also"></a>Consulte también

- [Compilar una aplicación WPF](building-a-wpf-application-wpf.md)
- [Seguridad](../security-wpf.md)
