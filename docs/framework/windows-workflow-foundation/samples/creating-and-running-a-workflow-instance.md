---
title: Crear y ejecutar una instancia de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 19d27f47-0491-4569-8f53-51bc1d940e80
ms.openlocfilehash: 571d41194ebc98be81646fb5bfdab060225015ca
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2018
ms.locfileid: "44252374"
---
# <a name="creating-and-running-a-workflow-instance"></a>Crear y ejecutar una instancia de flujo de trabajo
En este ejemplo se muestra cómo ejecutar una instancia de flujo de trabajo. Muestra cómo ejecutarla sincrónicamente y de forma asincrónica.  
  
## <a name="demonstrates"></a>Demostraciones  
 <xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.  
  
## <a name="discussion"></a>Explicación  
 La primera parte del ejemplo utiliza <xref:System.Activities.WorkflowInvoker.Invoke%2A>. Esta es la manera más básica de ejecutar un flujo de trabajo. Los flujos de trabajo ejecutados con <xref:System.Activities.WorkflowInvoker.Invoke%2A> se ejecutan de forma sincrónica.  
  
 La segunda parte del ejemplo usa la clase <xref:System.Activities.WorkflowApplication>. <xref:System.Activities.WorkflowApplication> permite tener más control sobre cada instancia, incluida la capacidad de interactuar con el flujo de trabajo en ejecución y ejecutar el flujo de trabajo de forma asincrónica.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreatingWorkflowInstances`  
  
## <a name="see-also"></a>Vea también  
 [Usar WorkflowInvoker y WorkflowApplication](../../../../docs/framework/windows-workflow-foundation/using-workflowinvoker-and-workflowapplication.md)
