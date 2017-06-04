---
title: "Usar una actividad de .NET Framework 3.0 o .NET Framework 3.5 en un flujo de trabajo de .NET Framework 4.5 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6c53fd4c-5dd0-4fb4-ab6b-111302629548
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Usar una actividad de .NET Framework 3.0 o .NET Framework 3.5 en un flujo de trabajo de .NET Framework 4.5
La actividad <xref:System.Activities.Statements.Interop> permite ejecutar una actividad de .NET Framework 3.0 [!INCLUDE[wf](../../../../includes/wf-md.md)] dentro de un flujo de trabajo de [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].En este ejemplo se muestra cómo utilizar la actividad <xref:System.Activities.Statements.Interop> para pasar una cadena como un argumento a una actividad de [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] personalizada.  
  
## Para utilizar este ejemplo  
  
1.  Abra el archivo de solución SimpleInterop.sln con [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Para compilar la solución, presione Ctrl\+MAYÚS\+B.  
  
3.  Para ejecutar la solución, presione CTRL\+F5.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\Migration\SimpleInterop`  
  
## Vea también