---
title: "Throttled Parallel ForEach | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f2855b5f-e9a7-433d-96a4-40fc31025215
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Throttled Parallel ForEach
La actividad `ThrottleParallelForEach` es similar a la actividad <xref:System.Activities.Statements.ParallelForEach> con la única excepción de que permite establecer un factor de simultaneidad para restringir el número de bifurcaciones simultáneas que se ejecutará.La actividad `ThrottleParallelForEach` se deriva de <xref:System.Activities.NativeActivity>, porque necesita programar otras actividades \(las actividades secundarias\) y el único acceso posible es a través de la clase <xref:System.Activities.NativeActivityContext>.  
  
## Proyectos  
  
||||  
|-|-|-|  
|**ProjectName**|**Descripción**|**Archivos principales**|  
|ThrottledParallelForEach|Contiene la actividad `ThrottledParallelForEach` y su diseñador.|ThrottledParallelForEach.cs<br /><br /> La definición de actividad de `ThrottledParallelForEach`.|  
|CodeTestClient|Aplicación cliente de ejemplo que configura y ejecuta un flujo de trabajo con una actividad `ThrottledParallelForEach` utilizando código imperativo.|Program.cs<br /><br /> Define y ejecuta una instancia del flujo de trabajo de muestra.|  
  
#### Para utilizar este ejemplo  
  
1.  Abra el archivo ThrottledParallelForEach.sln con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Para compilar la solución, presione Ctrl\+MAYÚS\+B.  
  
3.  Presione F5 para ejecutar la solución.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\ThrottledParallelForEach`  
  
## Vea también