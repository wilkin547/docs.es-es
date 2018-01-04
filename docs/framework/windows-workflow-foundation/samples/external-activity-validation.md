---
title: Validar actividades externas
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 49619f59-9819-484a-bcd8-5596308e8551
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: da326969e622a51f6a93b9faf5f81da079ea4003
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="external-activity-validation"></a>Validar actividades externas
Este ejemplo muestra cómo agregar la lógica de validación a una actividad integrada cuyo autor no es usted. La lógica de validación consiste en exigir que todas las actividades <xref:System.Activities.Statements.If> presentes en el flujo de trabajo tengan su propiedad <xref:System.Activities.Statements.If.Then%2A> establecida o su propiedad <xref:System.Activities.Statements.If.Else%2A> establecida. Además, la lógica de validación incluye la comprobación de que todas las actividades <xref:System.Activities.Statements.Pick> presentes en el flujo de trabajo tienen más de una bifurcación; si no es así, se genera una advertencia.  
  
## <a name="sample-details"></a>Detalles del ejemplo  
 En este ejemplo se crea un flujo de trabajo con una instancia de cada actividad que se va a validar: la actividad <xref:System.Activities.Statements.If> y la actividad <xref:System.Activities.Statements.Pick>. Se crea un nuevo objeto <xref:System.Activities.Validation.Constraint> para cada comportamiento de validación. Las restricciones creadas en este ejemplo son `ConstraintError_IfShouldHaveThenOrElse` y `ConstraintWarning_PickHasOneBranch`. A continuación, estas restricciones se agregan a la colección `AdditionalConstraints` de una instancia <xref:System.Activities.Validation.ValidationSettings>. Por último, se llama al método `static`<xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> de <xref:System.Activities.Validation.ActivityValidationServices> para validar las actividades del flujo de trabajo y el resultado de la validación se imprime en la consola.  
  
> [!NOTE]
>  Puede agregar restricciones de directiva a cualquier actividad. Por ejemplo, puede agregar una restricción de directiva a una actividad <xref:System.Activities.Statements.Sequence> o <xref:System.Activities.Statements.Parallel>.  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Abra el archivo ExternalActivityValidation.sln con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
3.  Presione Ctrl + F5 para ejecutar la solución.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\ExternalActivityValidation`