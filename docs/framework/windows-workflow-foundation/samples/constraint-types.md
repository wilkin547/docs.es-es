---
title: "Tipos de restricción"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b6b246e6-1130-4698-9625-c5c42abcbfed
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d42be018b6a92237b5914c180d329138fb95e7dc
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="constraint-types"></a>Tipos de restricción
Este ejemplo muestra dos formas diferentes de aplicar restricciones a un flujo de trabajo: desde dentro de la actividad (compilación) y desde fuera de ella (directiva). En este escenario, un autor de actividad (de una compañía de software de terceros) desea validar la relación entre dos argumentos. En este caso, el coste debe ser menor o igual que al precio. Esta es una restricción de compilación de validación general.  
  
 A continuación, un propietario de tienda desea agregar alguna validación a esta actividad genérica. En su caso, desea que el precio de la mayoría de sus productos sea $ 9,99 o menos. Por lo tanto, utiliza una restricción de directiva que está en la parte superior de la actividad `CreateProduct`.  
  
 En el ejemplo:  
  
 El autor de actividad (compilación) debe:  
  
-   Crear una restricción (`PriceGreaterThanCost`). Aquí es donde reside toda la lógica de validación.  
  
-   Invalidar `System.Activities.CodeActivity.OnGetConstraints()` y agregar la restricción (`PriceGreaterThanCost`) a las restricciones <xref:System.Collections.IList>.  
  
 El autor del flujo de trabajo (directiva) debe:  
  
-   Crear un flujo de trabajo con una instancia de la actividad para validar (`CreateProduct`).  
  
-   Crear una restricción (`MaxPrice`).  
  
-   Crear una instancia de <xref:System.Activities.Validation.ValidationSettings> (`validationSettings`) y agregar la restricción (`MaxPrice`) a la colección `AdditionalConstraints`. Aquí el autor del flujo de trabajo puede agregar restricciones de directiva a cualquier actividad, como una secuencia o paralela.  
  
-   Llamar a <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, que devuelve una colección <xref:System.Activities.Validation.ValidationResults> de objetos <xref:System.Activities.Validation.ValidationError>.  
  
-   (Opcional) Imprimir los objetos <xref:System.Activities.Validation.ValidationError>.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Abra la solución de ejemplo ConstraintTypes.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Compile y ejecute la solución.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Validation\ConstraintLibrary`