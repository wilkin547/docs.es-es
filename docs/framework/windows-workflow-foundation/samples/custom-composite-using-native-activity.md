---
title: Compuesto personalizado utilizando la actividad Native
ms.date: 03/30/2017
ms.assetid: ef9e739c-8a8a-4d11-9e25-cb42c62e3c76
ms.openlocfilehash: 2b922ef721ab4d125f390e908eb8ea4d3b087035
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142802"
---
# <a name="custom-composite-using-native-activity"></a>Compuesto personalizado utilizando la actividad Native
En este ejemplo se muestra cómo escribir un objeto <xref:System.Activities.NativeActivity> que programa otros objetos <xref:System.Activities.Activity> para controlar el flujo de ejecución de un flujo de trabajo. En este ejemplo se utilizan dos flujos de control comunes, Sequence y While, para mostrar cómo hacerlo.

## <a name="sample-details"></a>Detalles del ejemplo
 A partir de `MySequence`, lo primero que debe observar es que deriva de <xref:System.Activities.NativeActivity>. <xref:System.Activities.NativeActivity> es el objeto <xref:System.Activities.Activity> que expone todo el tiempo de ejecución de flujo de trabajo mediante el <xref:System.Activities.NativeActivityContext> pasado al método `Execute`.

 `MySequence` expone una colección pública de objetos <xref:System.Activities.Activity> que rellena el autor del flujo de trabajo. Antes de que se ejecute el flujo de trabajo, el tiempo de ejecución del flujo de trabajo llama al método <xref:System.Activities.Activity.CacheMetadata%2A> en cada actividad de un flujo de trabajo. Durante este proceso, el tiempo de ejecución establece relaciones primarias-secundarias para administrar la duración y el ámbito de los datos. La implementación <xref:System.Activities.Activity.CacheMetadata%2A> predeterminada del <xref:System.ComponentModel.TypeDescriptor> método utiliza `MySequence` la clase de instancia <xref:System.Activities.Activity> <xref:System.Collections.IEnumerable> \< <xref:System.Activities.Activity> para la actividad `MySequence` para agregar cualquier propiedad pública de tipo o> como elementos secundarios de la actividad.

 Siempre que una actividad expone una colección pública de actividades secundarias, es bastante probable que esas actividades secundarias compartan estado. Es un procedimiento recomendado para la actividad primaria, en este caso `MySequence`, exponer también una colección de variables que permitan a las actividades secundarias lograrlo. Al igual que <xref:System.Activities.Activity.CacheMetadata%2A> las actividades secundarias, <xref:System.Collections.IEnumerable> \< <xref:System.Activities.Variable> el método agrega propiedades públicas de tipo `MySequence` <xref:System.Activities.Variable> o> como variables asociadas a la actividad.

 Además de las variables públicas, que son manipuladas por los elementos secundarios de `MySequence`, `MySequence` debe realizar también un seguimiento de en qué punto se encuentra en la ejecución de sus elementos secundarios. Para ello, utiliza una variable privada, `currentIndex`. Esta variable se registra como parte del entorno `MySequence` agregando una llamada al método <xref:System.Activities.NativeActivityMetadata.AddImplementationVariable%2A> dentro del método `MySequence` de la actividad <xref:System.Activities.Activity.CacheMetadata%2A>. Los <xref:System.Activities.Activity> objetos `MySequence` `Activities` agregados a la colección no pueden tener acceso a las variables agregadas de esta manera.

 Cuando el tiempo de ejecución ejecuta `MySequence`, llama a su método <xref:System.Activities.NativeActivity.Execute%2A>, pasando un objeto <xref:System.Activities.NativeActivityContext>. <xref:System.Activities.NativeActivityContext> es el proxy de actividad en el tiempo de ejecución para eliminar la referencia de argumentos y variables, así como para programar otros objetos <xref:System.Activities.Activity> o `ActivityDelegates`. `MySequence` usa un método `InternalExecute` para encapsular la lógica de programar el primer elemento secundario y todos los elementos secundarios subsiguientes en un único método. Se inicia desreferenciando el objeto `currentIndex`. Si es igual al recuento de la colección `Activities`, se finaliza la secuencia, la actividad devuelve sin programar cualquier trabajo y el tiempo de ejecución pasa al estado <xref:System.Activities.ActivityInstanceState.Closed>. Si `currentIndex` es menor que el recuento de actividades, el `Activities` siguiente `MySequence` <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>elemento secundario se obtiene de <xref:System.Activities.CompletionCallback> la colección `InternalExecute` y las llamadas, pasando el elemento secundario que se va a programar y un that apunta al método. Por último, `currentIndex` se incrementa y el control se devuelve al tiempo de ejecución. Mientras una instancia de `MySequence` tenga un objeto secundario <xref:System.Activities.Activity> programado, el motor de ejecución considerará que su estado es En ejecución.

 Cuando la actividad secundaria se completa, se ejecuta <xref:System.Activities.CompletionCallback>. El bucle continúa desde el principio. Al igual que `Execute`, <xref:System.Activities.CompletionCallback> toma un objeto <xref:System.Activities.NativeActivityContext>, otorgando al implementador acceso al tiempo de ejecución.

 `MyWhile`difiere de `MySequence` que programa un <xref:System.Activities.Activity> solo objeto repetidamente y en <xref:System.Activities.Activity%601> que\> utiliza `Condition` un<bool denominado para determinar si debe producirse esta programación. Al igual que `MySequence`, `MyWhile` utiliza un método `InternalExecute` para centralizar su lógica de programación. Programa `Condition` <xref:System.Activities.Activity> el bool\><<xref:System.Activities.CompletionCallback%601> \<con un `OnEvaluationCompleted`bool> llamado . Cuando se completa la ejecución de `Condition`, su resultado pasa a estar disponible a través de <xref:System.Activities.CompletionCallback> en un parámetro fuertemente tipado denominado `result`. If `true`, `MyWhile` llama a  <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>, pasando el objeto `Body`<xref:System.Activities.Activity> y `InternalExecute` como <xref:System.Activities.CompletionCallback>. Cuando la ejecución de `Body` se completa, `Condition` se vuelve a programar en `InternalExecute`, lo que inicia de nuevo el bucle. Cuando `Condition` devuelve `false`, una instancia de `MyWhile` devuelve el control al tiempo de ejecución sin programar el objeto `Body` y el tiempo de ejecución pasa al estado <xref:System.Activities.ActivityInstanceState.Closed>.

#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo

1. Abra la solución de ejemplo Composite.sln en Visual Studio 2010.

2. Compile y ejecute la solución.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\CustomCompositeNativeActivity`
