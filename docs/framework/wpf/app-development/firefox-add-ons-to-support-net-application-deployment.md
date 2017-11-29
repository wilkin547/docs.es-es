---
title: "Complementos de Firefox para la implementación de aplicaciones .NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Firefox add-ons for .NET application deployment
- WPF plug-in for Firefox
- .NET application deployment [WPF], deploying with Firefox add-ons
- .NET Framework Assistant for Firefox
ms.assetid: 2403403b-9b14-48e9-b70d-fa288a3c9081
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f16fc118ccfef6cfcb9ab0dc1356cb0c732ae229
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="firefox-add-ons-to-support-net-application-deployment"></a>Complementos de Firefox para la implementación de aplicaciones .NET
El [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] complemento para Firefox y .NET Framework Assistant para habilitar Firefox [!INCLUDE[TLA#tla_winfxwebapp#plural](../../../../includes/tlasharptla-winfxwebappsharpplural-md.md)], malas [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]y las aplicaciones ClickOnce para que funcione con el explorador Mozilla Firefox.  
  
## <a name="wpf-plug-in-for-firefox"></a>Complemento de WPF para Firefox  
 Permite que el complemento WPF para Firefox [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] y malas [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivos para navegar y ejecutarse en el nivel superior o en un IFRAME de HTML en el explorador Firefox. Un [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] es un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aplicación que se pueden publicar en un servidor Web y han iniciado en exploradores compatibles. Flexible [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] es un archivo de solo XAML que puede navegar y mostrar en exploradores compatibles, igual que un archivo XML.  
  
 El [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] complemento para Firefox está instalado con el [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]. Ventana 7 incluye la [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)], pero no incluye el [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] complemento para Firefox. No se puede instalar el [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] complemento para Firefox en Windows 7.  
  
 El [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] no incluye el [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] complemento para Firefox. Sin embargo, si tanto el [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] y [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] están instalado, el complemento WPF para Firefox se instala con el [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)]. Por lo tanto, [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] aplicaciones se ejecutarán igualmente porque el Host de WPF se cargará la versión correcta de framework. Para obtener más información, consulte [Host de WPF (PresentationHost.exe)](../../../../docs/framework/wpf/app-development/wpf-host-presentationhost-exe.md).  
  
## <a name="net-framework-assistant-for-firefox"></a>Asistente de .NET Framework para Firefox  
 .NET Framework Assistant para Firefox permite a las aplicaciones independientes de ClickOnce para ejecutarse desde el explorador Firefox. .NET Framework Assistant para Firefox funciona de forma idéntica cuando se instala antes y después el explorador Firefox. Cuando se inicie el explorador Firefox y [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)] está instalado, Firefox busca e instala el Asistente de .NET Framework para Firefox. Los usuarios pueden configurar .NET Framework Assistant para Firefox hacer lo siguiente:  
  
-   Preguntar antes de ejecutar la aplicación ClickOnce.  
  
-   Mostrar todas las versiones instaladas de .NET Framework o solo la versión más reciente.  
  
 Se incluye con .NET Framework Assistant para Firefox el [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)]. Para obtener información acerca de cómo quitar el Asistente de .NET Framework para Firefox, consulte [cómo quitar el Asistente de .NET Framework para Firefox](http://go.microsoft.com/fwlink/?LinkId=177944).  
  
## <a name="see-also"></a>Vea también  
 [Implementar una aplicación WPF](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md)  
 [Información general sobre las aplicaciones de explorador XAML de WPF](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)  
 [Detectar si está instalado el complemento WPF para Firefox](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed.md)
