---
title: Actividad RangeEnumeration
ms.date: 03/30/2017
ms.assetid: ca5b78f4-94fa-4aa7-830d-26039ac422c8
ms.openlocfilehash: c9cf522227620422b414adc26cbc0bf338bf57d4
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44207595"
---
# <a name="rangeenumeration-activity"></a>Actividad RangeEnumeration
En este ejemplo se muestra cómo crear una actividad personalizada que recorra en iteración una colección de números. La tabla que sigue detalla los archivos principales incluidos en el ejemplo.  
  
|Nombre del archivo|Descripción|  
|---------------|-----------------|  
|RangeEnumeration.cs|Define una actividad personalizada denominada `RangeEnumeration` que invalida la clase <xref:System.Activities.NativeActivity> y recorre en bucle una serie de números.|  
|RangeEnumerationSample.cs|Una aplicación cliente que utiliza la actividad `RangeEnumeration` para recorrer en iteración una colección de números.|  
  
 En la tabla siguiente se detallan las propiedades de la actividad `RangeEnumeration`.  
  
|Propiedad|Descripción|  
|--------------|-----------------|  
|Iniciar|El entero a partir del cual se inicia el bucle.|  
|Detener|El entero en el que detener el bucle.|  
|Paso|Especifica cuánto se recorre en iteración cada vez.|  
|Body|Especifica el código para ejecutar durante cada iteración.|  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Abra el archivo de solución de RangeEnumeration.sln con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
3.  Para ejecutar la solución, presione CTRL+F5.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\RangeEnumeration`