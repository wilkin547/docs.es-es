---
title: "Propiedades de ejecución"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 31c009db-397c-4653-87e2-32dc77fa4b13
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5a394ff136464dd2e69f8c38f07b1b2542bf4a87
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
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
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ExecutionProperties`  
  
## <a name="see-also"></a>Vea también
