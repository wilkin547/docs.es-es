---
title: "Propiedades de ejecuci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 31c009db-397c-4653-87e2-32dc77fa4b13
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Propiedades de ejecuci&#243;n
En este ejemplo se muestra cómo definir y utilizar una propiedad de ejecución en una actividad personalizada.En este ejemplo, la propiedad de ejecución determina el color de primer plano de la consola.Un flujo de trabajo de ejemplo muestra cómo diferentes rutas de acceso lógicas de ejecución \(bifurcaciones de una actividad <xref:System.Activities.Statements.Parallel>\) pueden mantener diferentes colores de consola a pesar de la ejecución intercalada de actividades \(en las bifurcaciones de la actividad <xref:System.Activities.Statements.Parallel>\).  
  
#### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Abra la solución de ejemplo ExecutionProperties.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
    > [!NOTE]
    >  La visualización de ThreeColors.xaml antes de compilar la solución se muestra un error, porque las actividades personalizadas utilizadas se deben compilar al mismo tiempo que la solución.  
  
2.  Compile y ejecute la solución.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ExecutionProperties`  
  
## Vea también