---
title: Tipos de restricción
ms.date: 03/30/2017
ms.assetid: b6b246e6-1130-4698-9625-c5c42abcbfed
ms.openlocfilehash: 53e5975017c3a27ede8ad07cd93f78f71df2d3e5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517513"
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
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Validation\ConstraintLibrary`