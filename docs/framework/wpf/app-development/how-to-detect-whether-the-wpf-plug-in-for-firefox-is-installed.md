---
title: "C&#243;mo: Detectar si est&#225; instalado el complemento WPF para Firefox | Microsoft Docs"
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
  - "buscar el complemento para Firefox [WPF]"
  - "detectar la instalación de Firefox [WPF]"
  - "detectar si está instalado el complemento de WPF para Firefox [WPF]"
  - "Firefox [WPF], detectar la instalación"
  - "complemento para Firefox [WPF]"
ms.assetid: 5f839373-e3fb-44f1-88ad-4a0761f02189
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Detectar si est&#225; instalado el complemento WPF para Firefox
El complemento [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] para Firefox permite que [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] y los archivos XAML separados se ejecuten en el explorador Mozilla Firefox.  En este tema se proporciona un script escrito en HTML y JavaScript que los administradores pueden utilizar para determinar si el complemento de WPF para Firefox está instalado.  
  
> [!NOTE]
>  Para obtener información más detallada sobre cómo instalar, implementar y detectar [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], vea [Instalar .NET Framework](../../../../docs/framework/install/guide-for-developers.md).  
  
## Ejemplo  
 Cuando se instala [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)], el equipo cliente se configura con un complemento WPF para Firefox.  El siguiente script de ejemplo comprueba el complemento WPF para Firefox y, a continuación, muestra el mensaje del estado apropiado.  
  
```  
<HTML>  
  
  <HEAD>  
    <TITLE>Test for the WPF plug-in for Firefox</TITLE>  
    <META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=utf-8" />  
    <SCRIPT type="text/javascript">  
    <!--  
    function OnLoad()  
    {  
  
       // Check for the WPF plug-in for Firefox and report  
       var msg = "The WPF plug-in for Firefox is ";  
       var wpfPlugin = navigator.plugins["Windows Presentation Foundation"];  
       if( wpfPlugin != null ) {  
          document.writeln(msg + " installed.");  
       }  
       else {  
          document.writeln(msg + " not installed. Please install or reinstall the .NET Framework 3.5.");  
       }  
    }  
    -->  
    </SCRIPT>  
  </HEAD>  
  
  <BODY onload="OnLoad()" />  
  
</HTML>  
```  
  
 Si la comprobación del complemento WPF para Firefox es correcta, se muestra el siguiente mensaje del estado:  
  
 `The WPF plug-in for Firefox is installed.`  
  
 De lo contrario, aparecerá el siguiente mensaje de estado:  
  
 `The WPF plug-in for Firefox is not installed.  Please install or reinstall the .NET Framework 3.5.`  
  
## Vea también  
 [Detectar si .NET Framework 3.0 está instalado](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md)   
 [Detectar si .NET Framework 3.5 está instalado](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-5-is-installed.md)   
 [Información general sobre las aplicaciones de explorador XAML de WPF](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md)