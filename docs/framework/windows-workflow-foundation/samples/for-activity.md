---
title: Actividad For
ms.date: 03/30/2017
ms.assetid: 2ea751b4-36f0-48aa-a115-70a2ab89f6d8
ms.openlocfilehash: 7a7023abb9057ab4b25552fbf9a81cd2ae2b4e88
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44206268"
---
# <a name="for-activity"></a>Actividad For
El ejemplo de For muestra cómo compilar una actividad personalizada que hereda de <xref:System.Activities.NativeActivity> y utilizarla en un flujo de trabajo para ejecutar un ejemplo del mundo real. La actividad personalizada incluida en este ejemplo funciones como la instrucción `for` de C#. T  
  
 La actividad personalizada `For` tiene propiedades denominadas `InitAction`, `IterationAction`, `Condition` y `Body` que corresponden respectivamente a la instrucción de inicialización, instrucción iterativa, condición de continuación e instrucción de cuerpo de la instrucción `For` estándar de C#.  
  
 En la siguiente tabla se describen los archivos clave del ejemplo.  
  
|Archivo|Descripción|  
|----------|-----------------|  
|For.cs|Definición de clase para la actividad personalizada `For`, que amplía la clase <xref:System.Activities.NativeActivity> para proporcionar la funcionalidad de la instrucción `For` de C#.|  
|Program.cs|Aplicación cliente que realiza trabajo repetitivo básico en una colección mediante la actividad `For` personalizada.|  
  
> [!NOTE]
>  Al utilizar la actividad personalizada `For`, asegúrese de que se establece la propiedad `Condition`; de lo contrario se podría producir un bucle infinito.  
  
## <a name="demonstrates"></a>Demostraciones  
 Cree una actividad personalizada que herede de <xref:System.Activities.NativeActivity>.  
  
## <a name="discussion"></a>Explicación  
 En la siguiente tabla se describen las propiedades de la actividad incluida en este ejemplo.  
  
 InitAction  
 Instrucción de inicialización  
  
 IterationAction  
 Instrucción iterativa  
  
 Condición  
 Instrucción de continuación  
  
 Body  
 Instrucción de cuerpo  
  
 La actividad hereda de <xref:System.Activities.NativeActivity> para obtener acceso a las características en tiempo de ejecución, como la programación de actividades adicionales para ejecutarse, utilizando uno de los métodos `ScheduleActivity` de <xref:System.Activities.NativeActivityContext>.  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución For.sln.  
  
2.  Compile la solución presionando CTRL+MAYÚS+B.  
  
3.  Ejecute la solución presionando F5.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\For`