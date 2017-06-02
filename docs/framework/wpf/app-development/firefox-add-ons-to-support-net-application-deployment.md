---
title: "Complementos de Firefox para la implementaci&#243;n de aplicaciones .NET | Microsoft Docs"
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
  - "implementación de aplicaciones .NET, implementar con complementos Firefox"
  - "Asistente de .NET Framework para Firefox"
  - "Complementos de Firefox para la implementación de aplicaciones .NET"
  - "complemento de WPF para Firefox"
ms.assetid: 2403403b-9b14-48e9-b70d-fa288a3c9081
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# Complementos de Firefox para la implementaci&#243;n de aplicaciones .NET
El complemento [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] para Firefox y el asistente de .NET Framework para Firefox permiten a [!INCLUDE[TLA#tla_winfxwebapp#plural](../../../../includes/tlasharptla-winfxwebappsharpplural-md.md)], al [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dinámico y a las aplicaciones ClickOnce trabajar con el explorador Mozilla Firefox.  
  
## Complemento WPF para Firefox  
 El complemento WPF para Firefox permite navegar a [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] y a los archivos de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dinámico y ejecutarlos en el nivel superior o en un IFRAME HTML en el explorador de Firefox.  Una [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] es una aplicación [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] que se puede publicar en un servidor web e iniciar dentro de los exploradores compatibles.  El [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dinámico es un archivo solo de XAML al que se puede navegar y mostrar en exploradores compatibles, como un archivo XML.  
  
 El complemento [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] para Firefox se instala con [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)].  Windows 7 incluye [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)], pero no incluye el complemento [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] para Firefox. No puede instalar el complemento [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] para Firefox en Windows 7.  
  
 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] no incluye el complemento [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] para Firefox. Sin embargo, si [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] y [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] están instalados, el complemento WPF para Firefox se instala con [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)].  Por consiguiente, las aplicaciones de [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] todavía se ejecutarán porque el host de WPF cargará la versión correcta del marco.  Para obtener más información, vea [WPF Host \(PresentationHost.exe\)](../../../../docs/framework/wpf/app-development/wpf-host-presentationhost-exe.md).  
  
## Asistente de .NET Framework para Firefox  
 El asistente de .NET Framework para Firefox permite a las aplicaciones ClickOnce independientes ejecutarse desde el explorador de Firefox.  El asistente de .NET Framework para Firefox funciona exactamente igual si se instala antes y después del explorador Firefox.  Cuando se inicia el explorador Firefox y se instala [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)], Firefox encuentra e instala el asistente de .NET Framework para Firefox.  Los usuarios pueden configurar el asistente de .NET Framework para Firefox para hacer lo siguiente:  
  
-   Preguntar antes de ejecutar la aplicación ClickOnce.  
  
-   Notificar todas las versiones instaladas de .NET Framework o solamente la última versión.  
  
 El asistente de .NET Framework para Firefox se incluye con [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)].  Para obtener información sobre cómo quitar el asistente de .NET Framework para Firefox, vea [How to remove the .NET Framework Assistant for Firefox](http://go.microsoft.com/fwlink/?LinkId=177944).  
  
## Vea también  
 [Implementar una aplicación de WPF](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md)   
 [Información general sobre las aplicaciones de explorador XAML de WPF](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)   
 [Detectar si está instalado el complemento WPF para Firefox](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed.md)