---
title: Propiedades de ejecución
ms.date: 03/30/2017
ms.assetid: 31c009db-397c-4653-87e2-32dc77fa4b13
ms.openlocfilehash: 201fe222de1cb2029696a1694ae97815db5f913d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="execution-properties"></a>Propiedades de ejecución
En este ejemplo se muestra cómo definir y utilizar una propiedad de ejecución en una actividad personalizada. En este ejemplo, la propiedad de ejecución determina el color de primer plano de la consola. Un flujo de trabajo de ejemplo muestra cómo diferentes rutas de acceso lógicas de ejecución (bifurcaciones de una actividad <xref:System.Activities.Statements.Parallel>) pueden mantener diferentes colores de consola a pesar de la ejecución intercalada de actividades (en las bifurcaciones de la actividad <xref:System.Activities.Statements.Parallel>).  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Abra la solución de ejemplo ExecutionProperties.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
    > [!NOTE]
    >  La visualización de ThreeColors.xaml antes de compilar la solución se muestra un error, porque las actividades personalizadas utilizadas se deben compilar al mismo tiempo que la solución.  
  
2.  Compile y ejecute la solución.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ExecutionProperties`