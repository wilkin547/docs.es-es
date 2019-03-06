---
title: Complementos de Firefox para la implementación de aplicaciones .NET
ms.date: 03/30/2017
helpviewer_keywords:
- Firefox add-ons for .NET application deployment
- WPF plug-in for Firefox
- .NET application deployment [WPF], deploying with Firefox add-ons
- .NET Framework Assistant for Firefox
ms.assetid: 2403403b-9b14-48e9-b70d-fa288a3c9081
ms.openlocfilehash: 837ed1cd41869031e8c0b549ffcd26e3285570cd
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368069"
---
# <a name="firefox-add-ons-to-support-net-application-deployment"></a>Complementos de Firefox para la implementación de aplicaciones .NET
Habilitar Windows Presentation Foundation (WPF) complemento para Firefox y el Asistente de .NET Framework para Firefox [!INCLUDE[TLA#tla_winfxwebapp#plural](../../../../includes/tlasharptla-winfxwebappsharpplural-md.md)], sueltos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]y las aplicaciones ClickOnce para que funcione con el explorador Mozilla Firefox.  
  
## <a name="wpf-plug-in-for-firefox"></a>Complemento WPF para Firefox  
 Permite que el complemento WPF para Firefox [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] y flexible [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivos para navegar y ejecutarse en el nivel superior o en un IFRAME de HTML en el explorador Firefox. Un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] es un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] exploradores compatibles con la aplicación que se puede publicar en un servidor Web e iniciarse. Flexible [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] es un archivo de solo XAML que puede navegar y mostrar en exploradores compatibles, como un archivo XML.  
  
 El [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] complemento para Firefox está instalado con el [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]. Windows 7 incluyen la [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)], pero no incluye el [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] complemento para Firefox. No se puede instalar el [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] complemento para Firefox en Windows 7.  
  
 El [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] no incluye el [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] complemento para Firefox. Sin embargo, si tanto el [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] y [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] están instalado, se instala el complemento WPF para Firefox con la [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]. Por lo tanto, [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] aplicaciones todavía se ejecutarán porque el Host de WPF se cargará la versión correcta de framework. Para obtener más información, consulte [WPF Host (PresentationHost.exe)](wpf-host-presentationhost-exe.md).  
  
## <a name="net-framework-assistant-for-firefox"></a>Asistente de .NET Framework para Firefox  
 El Asistente de .NET Framework para Firefox permite que las aplicaciones independientes de ClickOnce para ejecutarse desde el explorador Firefox. El Asistente de .NET Framework para Firefox funciona exactamente igual cuando se instala antes y después el explorador Firefox. Cuando se inicia el explorador Firefox y [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)] está instalado, Firefox busca e instala el Asistente de .NET Framework para Firefox. Los usuarios pueden configurar el Asistente de .NET Framework para Firefox hacer lo siguiente:  
  
-   Preguntar antes de ejecutar la aplicación ClickOnce.  
  
-   Informe todas las versiones instaladas de .NET Framework o solo la versión más reciente.  
  
 El Asistente de .NET Framework para Firefox se incluye con el [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)]. Para obtener información acerca de cómo quitar el Asistente de .NET Framework para Firefox, consulte [cómo quitar el Asistente de .NET Framework para Firefox](https://go.microsoft.com/fwlink/?LinkId=177944).  
  
## <a name="see-also"></a>Vea también
- [Implementar una aplicación WPF](deploying-a-wpf-application-wpf.md)
- [Información general sobre las aplicaciones de explorador XAML de WPF](wpf-xaml-browser-applications-overview.md)
- [Detectar si está instalado el complemento WPF para Firefox](how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed.md)
