---
title: Realizar el seguimiento visual del flujo de trabajo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0143448f-2044-40a0-8a3d-941f6d12468b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 687cc2acbff7c85b89c4502fff863e48dada97de
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="visual-workflow-tracking"></a>Realizar el seguimiento visual del flujo de trabajo
En este ejemplo se muestra cómo escribir una aplicación de seguimiento de flujo de trabajo visual mediante la funcionalidad de depuración disponible en [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].  
  
## <a name="sample-details"></a>Detalles del ejemplo  
 La aplicación ejecuta un flujo de trabajo de diagrama de flujo simple (definido en Workflow.xaml) y hospeda en otro host el diseñador de flujo de trabajo para mostrar el flujo de trabajo que se está ejecutando actualmente. A medida que se ejecuta el flujo de trabajo, la actividad que se está ejecutando actualmente se muestra con un contorno amarillo y una flecha de depuración. Además, los registros de seguimiento generados por el flujo de trabajo también se muestran en la ventana de la aplicación. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]flujo de trabajo de seguimiento, vea [seguimiento y traza del flujo de trabajo](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md). [!INCLUDE[crabout](../../../../includes/crabout-md.md)]hospedar en otro host el Diseñador de flujo de trabajo, consulte [Rehospedar el Diseñador de flujo de trabajo](../../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md).  
  
 El simulador de flujo de trabajo funciona manteniendo dos diccionarios. Uno contiene una asignación entre el objeto de actividad actualmente en ejecución y el número de línea de XAML donde se crea la instancia de la actividad. El otro contiene una asignación entre el identificador de la instancia de actividad y el objeto de actividad. Cuando se emiten registros de seguimiento mediante un perfil de seguimiento personalizado, la aplicación determina el identificador de instancia de la actividad que se está ejecutando actualmente y lo asigna al archivo XAML que creó su instancia. A continuación, se indica al diseñador de flujo de trabajo hospedado en otro host que resalte la actividad en la superficie del diseñador y utilice el mismo método que el depurador del flujo de trabajo, concretamente que dibuje un borde amarillo en torno a la actividad y que muestre una flecha amarilla en el lado izquierdo del diseñador.  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Abra el archivo WorkflowSimulator.sln del directorio de ejemplo en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Presione Ctrl+MAYÚS+B para compilar la solución.  
  
3.  Presione CTRL + F5 para ejecutar el ejemplo. Así se muestra el archivo Workflow.xaml en una ventana de diseñador de flujo de trabajo hospedada en otro host.  
  
4.  Haga clic en el **archivo** menú y seleccione **ejecutar el flujo de trabajo...** .  
  
5.  Observe que la actividad actualmente en ejecución se resalta tal como se ha descrito previamente y que en el lado derecho de la ventana de la aplicación se muestran los registros de seguimiento.  
  
6.  Cuando el flujo de trabajo se ha completado, puede hacer clic en cualquier registro de seguimiento para inspeccionar qué actividad corresponde.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Application\VisualWorkflowTracking`