---
title: "Utilizar interoperabilidad con intercambio de datos externos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 96f6fe26-5305-494f-9119-7748e0c4b3fa
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Utilizar interoperabilidad con intercambio de datos externos
La actividad <xref:System.Activities.Statements.Interop> se puede utilizar para ejecutar actividades desde [!INCLUDE[wf](../../../../includes/wf-md.md)] en [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] y [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] \(WF3\), y flujos de trabajo dentro de [!INCLUDE[wf2](../../../../includes/wf2-md.md)] en [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] \(WF4\).En este ejemplo se muestra cómo configurar y ejecutar un flujo de trabajo WF3 que utiliza <xref:System.Workflow.Activities.ExternalDataExchangeService> \(y las actividades personalizadas correspondientes para llamar a los métodos y administrar los eventos\) utilizando la actividad <xref:System.Activities.Statements.Interop> en un servicio de flujo de trabajo WF4.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\Migration\ExternalDataExchange`  
  
#### Para utilizar este ejemplo  
  
1.  Abra el archivo ExternalDataExchange.sln de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Para generar el ejemplo, presione Ctrl\+Mayús\+B.  
  
3.  Para ejecutar el ejemplo, presione F5.