---
title: Throttled Parallel ForEach
ms.date: 03/30/2017
ms.assetid: f2855b5f-e9a7-433d-96a4-40fc31025215
ms.openlocfilehash: 7149e6db8992bff5b436ffae4a77d985ec255986
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43564910"
---
# <a name="throttled-parallel-foreach"></a>Throttled Parallel ForEach
El `ThrottleParallelForEach` actividad es similar a la <!--zz <xref:System.Activities.Statements.ParallelForEach>--> `System.Activities.Statements.ParallelForEach` actividad con la excepción que permite establecer un factor de simultaneidad para restringir el número de bifurcaciones simultáneas que se ejecute. La actividad `ThrottleParallelForEach` se deriva de <xref:System.Activities.NativeActivity>, porque necesita programar otras actividades (las actividades secundarias) y el único acceso posible es a través de la clase <xref:System.Activities.NativeActivityContext>.  
  
## <a name="projects"></a>Proyectos  
  
|**ProjectName**|**Descripción**|**Archivos principales**|  
|-|-|-|  
|ThrottledParallelForEach|Contiene la actividad `ThrottledParallelForEach` y su diseñador.|ThrottledParallelForEach.cs<br /><br /> La definición de actividad de `ThrottledParallelForEach`.|  
|CodeTestClient|Aplicación cliente de ejemplo que configura y ejecuta un flujo de trabajo con una actividad `ThrottledParallelForEach` utilizando código imperativo.|Program.cs<br /><br /> Define y ejecuta una instancia del flujo de trabajo de muestra.|  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Abra el archivo ThrottledParallelForEach.sln con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
3.  Presione F5 para ejecutar la solución.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\ThrottledParallelForEach`