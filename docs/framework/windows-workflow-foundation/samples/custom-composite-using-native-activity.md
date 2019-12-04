---
title: Compuesto personalizado utilizando la actividad Native
ms.date: 03/30/2017
ms.assetid: ef9e739c-8a8a-4d11-9e25-cb42c62e3c76
ms.openlocfilehash: 57c724ad55c3aa2960e9a2d11fcd8419a94a0c72
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715177"
---
# <a name="custom-composite-using-native-activity"></a>Compuesto personalizado utilizando la actividad Native
En este ejemplo se muestra cómo escribir un objeto <xref:System.Activities.NativeActivity> que programa otros objetos <xref:System.Activities.Activity> para controlar el flujo de ejecución de un flujo de trabajo. En este ejemplo se utilizan dos flujos de control comunes, Sequence y While, para mostrar cómo hacerlo.

## <a name="sample-details"></a>Detalles del ejemplo
 A partir de `MySequence`, lo primero que debe observar es que deriva de <xref:System.Activities.NativeActivity>. <xref:System.Activities.NativeActivity> es el objeto <xref:System.Activities.Activity> que expone todo el tiempo de ejecución de flujo de trabajo mediante el <xref:System.Activities.NativeActivityContext> pasado al método `Execute`.

 `MySequence` expone una colección pública de objetos <xref:System.Activities.Activity> que rellena el autor del flujo de trabajo. Antes de que se ejecute el flujo de trabajo, el tiempo de ejecución del flujo de trabajo llama al método <xref:System.Activities.Activity.CacheMetadata%2A> en cada actividad de un flujo de trabajo. Durante este proceso, el tiempo de ejecución establece relaciones primarias-secundarias para administrar la duración y el ámbito de los datos. La implementación predeterminada del método <xref:System.Activities.Activity.CacheMetadata%2A> usa la clase de instancia <xref:System.ComponentModel.TypeDescriptor> de la actividad `MySequence` para agregar cualquier propiedad pública del tipo <xref:System.Activities.Activity> o <xref:System.Collections.IEnumerable>\<<xref:System.Activities.Activity>> como elementos secundarios de la actividad `MySequence`.

 Siempre que una actividad expone una colección pública de actividades secundarias, es bastante probable que esas actividades secundarias compartan estado. Es un procedimiento recomendado para la actividad primaria, en este caso `MySequence`, exponer también una colección de variables que permitan a las actividades secundarias lograrlo. Al igual que las actividades secundarias, el método <xref:System.Activities.Activity.CacheMetadata%2A> agrega propiedades públicas de tipo <xref:System.Activities.Variable> o <xref:System.Collections.IEnumerable>\<<xref:System.Activities.Variable>> como variables asociadas a la actividad `MySequence`.

 Además de las variables públicas, que son manipuladas por los elementos secundarios de `MySequence`, `MySequence` debe realizar también un seguimiento de en qué punto se encuentra en la ejecución de sus elementos secundarios. Para ello, utiliza una variable privada, `currentIndex`. Esta variable se registra como parte del entorno `MySequence` agregando una llamada al método <xref:System.Activities.NativeActivityMetadata.AddImplementationVariable%2A> dentro del método `MySequence` de la actividad <xref:System.Activities.Activity.CacheMetadata%2A>. Los objetos <xref:System.Activities.Activity> agregados a la colección `MySequence``Activities` no pueden obtener acceso a las variables agregadas de esta manera.

 Cuando el tiempo de ejecución ejecuta `MySequence`, llama a su método <xref:System.Activities.NativeActivity.Execute%2A>, pasando un objeto <xref:System.Activities.NativeActivityContext>. <xref:System.Activities.NativeActivityContext> es el proxy de actividad en el tiempo de ejecución para eliminar la referencia de argumentos y variables, así como para programar otros objetos <xref:System.Activities.Activity> o `ActivityDelegates`. `MySequence` usa un método `InternalExecute` para encapsular la lógica de programar el primer elemento secundario y todos los elementos secundarios subsiguientes en un único método. Se inicia desreferenciando el objeto `currentIndex`. Si es igual al recuento de la colección `Activities`, se finaliza la secuencia, la actividad devuelve sin programar cualquier trabajo y el tiempo de ejecución pasa al estado <xref:System.Activities.ActivityInstanceState.Closed>. Si el `currentIndex` es menor que el número de actividades, el siguiente elemento secundario se obtiene de la colección `Activities` y `MySequence` llama a <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>, pasando el elemento secundario que se va a programar y una <xref:System.Activities.CompletionCallback> que apunta al método `InternalExecute`. Por último, `currentIndex` se incrementa y el control se devuelve al tiempo de ejecución. Mientras una instancia de `MySequence` tenga un objeto secundario <xref:System.Activities.Activity> programado, el motor de ejecución considerará que su estado es En ejecución.

 Cuando la actividad secundaria se completa, se ejecuta <xref:System.Activities.CompletionCallback>. El bucle continúa desde el principio. Al igual que `Execute`, <xref:System.Activities.CompletionCallback> toma un objeto <xref:System.Activities.NativeActivityContext>, otorgando al implementador acceso al tiempo de ejecución.

 `MyWhile` difiere de `MySequence` en que programa un solo <xref:System.Activities.Activity> objeto de forma repetida y en que utiliza una <xref:System.Activities.Activity%601>< bool\> denominada `Condition` para determinar si se debe realizar esta programación. Al igual que `MySequence`, `MyWhile` utiliza un método `InternalExecute` para centralizar su lógica de programación. Programa el `Condition`<xref:System.Activities.Activity>< bool\> con <xref:System.Activities.CompletionCallback%601>\<bool > con el nombre `OnEvaluationCompleted`. Cuando se completa la ejecución de `Condition`, su resultado pasa a estar disponible a través de <xref:System.Activities.CompletionCallback> en un parámetro fuertemente tipado denominado `result`. If `true`, `MyWhile` llama a  <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>, pasando el objeto `Body`<xref:System.Activities.Activity> y `InternalExecute` como <xref:System.Activities.CompletionCallback>. Cuando la ejecución de `Body` se completa, `Condition` se vuelve a programar en `InternalExecute`, lo que inicia de nuevo el bucle. Cuando `Condition` devuelve `false`, una instancia de `MyWhile` devuelve el control al tiempo de ejecución sin programar el objeto `Body` y el tiempo de ejecución pasa al estado <xref:System.Activities.ActivityInstanceState.Closed>.

#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo

1. Abra la solución de ejemplo composite. sln en Visual Studio 2010.

2. Compile y ejecute la solución.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Este ejemplo se encuentra en el siguiente directorio.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\CustomCompositeNativeActivity`
