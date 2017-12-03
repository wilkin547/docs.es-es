---
title: "Validación básica"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba1343cc-aaab-4ade-b0c0-1dd5063bf4ad
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 99af85c87f52447f9be7a01c1ab2549158844677
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="basic-validation"></a>Validación básica
Este ejemplo consta de una actividad, `CreateProduct`, que valida que su argumento `Cost` es menor o igual que su argumento `Price`.  
  
## <a name="sample-details"></a>Detalles del ejemplo  
 Hay dos autores que utilizan la validación: el autor de actividad (crea la lógica de validación de la actividad) y el autor del flujo de trabajo que llama a los servicios de validación en un flujo de trabajo concreto. En este escenario, el autor de actividad desea exigir que cada instancia de su actividad tenga un costo menor o igual que el del precio.  
  
 El autor de actividad (dentro de la actividad) debe:  
  
-   Crear una restricción (`PriceGreaterThanCost`). Aquí es donde reside toda la lógica de validación.  
  
-   Invalidar `System.Activities.CodeActivity.OnGetConstraints()` y agregar la restricción (`PriceGreaterThanCost`) a las restricciones <xref:System.Collections.IList>.  
  
 El autor del flujo de trabajo (programa general) debe:  
  
-   Crear un flujo de trabajo con una instancia de la actividad para validar (`CreateProduct`).  
  
-   Llamar a <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, que devuelve una colección <xref:System.Activities.Validation.ValidationResults> de <xref:System.Activities.Validation.ValidationError>.  
  
-   (Opcional) Imprimir los objetos <xref:System.Activities.Validation.ValidationError>.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Abra la solución de ejemplo BasicValidation.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Compile y ejecute la solución.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\BasicValidation`