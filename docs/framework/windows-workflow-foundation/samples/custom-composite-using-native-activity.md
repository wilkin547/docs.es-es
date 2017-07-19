---
title: "Compuesto personalizado utilizando la actividad Native | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ef9e739c-8a8a-4d11-9e25-cb42c62e3c76
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Compuesto personalizado utilizando la actividad Native
En este ejemplo se muestra cómo escribir un objeto <xref:System.Activities.NativeActivity> que programa otros objetos <xref:System.Activities.Activity> para controlar el flujo de ejecución de un flujo de trabajo.En este ejemplo se utilizan dos flujos de control comunes, Sequence y While, para mostrar cómo hacerlo.  
  
## Detalles del ejemplo  
 A partir de `MySequence`, lo primero que debe observar es que deriva de <xref:System.Activities.NativeActivity>.<xref:System.Activities.NativeActivity> es el objeto <xref:System.Activities.Activity> que expone todo el runtime de flujo de trabajo mediante el <xref:System.Activities.NativeActivityContext> pasado al método `Execute`.  
  
 `MySequence` expone una colección pública de objetos <xref:System.Activities.Activity> que rellena el autor del flujo de trabajo.Antes de que se ejecute el flujo de trabajo, el tiempo de ejecución del flujo de trabajo llama al método <xref:System.Activities.Activity.CacheMetadata%2A> en cada actividad de un flujo de trabajo.Durante este proceso, el tiempo de ejecución establece relaciones primarias\-secundarias para administrar la duración y el ámbito de los datos.La implementación predeterminada del método <xref:System.Activities.Activity.CacheMetadata%2A> utiliza la clase de instancia <xref:System.ComponentModel.TypeDescriptor> de la actividad `MySequence` para agregar las propiedades públicas de tipo <xref:System.Activities.Activity> o <xref:System.Collections.IEnumerable>\<<xref:System.Activities.Activity>\> como elementos secundarios de la actividad `MySequence`.  
  
 Siempre que una actividad expone una colección pública de actividades secundarias, es bastante probable que esas actividades secundarias compartan estado.Es un procedimiento recomendado para la actividad primaria, en este caso `MySequence`, exponer también una colección de variables que permitan a las actividades secundarias lograrlo.Al igual que las actividades secundarias, el método <xref:System.Activities.Activity.CacheMetadata%2A> agrega propiedades públicas de tipo <xref:System.Activities.Variable> o <xref:System.Collections.IEnumerable>\<<xref:System.Activities.Variable>\> como variables asociadas a la actividad `MySequence`.  
  
 Además de las variables públicas, que son manipuladas por los elementos secundarios de `MySequence`, `MySequence` debe realizar también un seguimiento de en qué punto se encuentra en la ejecución de sus elementos secundarios.Para ello, utiliza una variable privada, `currentIndex`.Esta variable se registra como parte del entorno `MySequence` agregando una llamada al método <xref:System.Activities.NativeActivityMetadata.AddImplementationVariable%2A> dentro del método <xref:System.Activities.Activity.CacheMetadata%2A> de la actividad `MySequence`.Los objetos <xref:System.Activities.Activity> agregados a la colección `MySequence` `Activities` no pueden obtener acceso a las variables agregadas de esta manera.  
  
 Cuando el tiempo de ejecución ejecuta `MySequence`, llama a su método <xref:System.Activities.NativeActivity.Execute%2A>, pasando un objeto <xref:System.Activities.NativeActivityContext>.<xref:System.Activities.NativeActivityContext> es el proxy de actividad en el runtime para desreferenciar argumentos y variables, así como para programar otros objetos <xref:System.Activities.Activity> o `ActivityDelegates`.`MySequence` usa un método `InternalExecute` para encapsular la lógica de programar el primer elemento secundario y todos los elementos secundarios subsiguientes en un único método.Se inicia desreferenciando el objeto `currentIndex`.Si es igual al recuento de la colección `Activities`, se finaliza la secuencia, la actividad devuelve sin programar cualquier trabajo y el tiempo de ejecución pasa al estado <xref:System.Activities.ActivityInstanceState>.Si `currentIndex` es menor que el recuento de actividades, el elemento secundario siguiente se obtiene de la colección `Activities` y `MySequence` llama a <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>, pasando el elemento secundario que se va a programar y <xref:System.Activities.CompletionCallback> que señala al método `InternalExecute`.Por último, `currentIndex` se incrementa y el control se devuelve al tiempo de ejecución.Mientras una instancia de `MySequence` tenga un objeto secundario <xref:System.Activities.Activity> programado, el motor de ejecución considerará que su estado es En ejecución.  
  
 Cuando la actividad secundaria se completa, se ejecuta <xref:System.Activities.CompletionCallback>.El bucle continúa desde el principio.Al igual que `Execute`, <xref:System.Activities.CompletionCallback> toma un objeto <xref:System.Activities.NativeActivityContext>, otorgando al implementador acceso al tiempo de ejecución.  
  
 `MyWhile` difiere de `MySequence` en que programa un objeto <xref:System.Activities.Activity> único de forma repetida y en que utiliza un objeto <xref:System.Activities.Activity%601>\<bool\> denominado `Condition` para determinar si se debería producir la programación.Al igual que `MySequence`, `MyWhile` utiliza un método `InternalExecute` para centralizar su lógica de programación.Programa el objeto `Condition`<xref:System.Activities.Activity>\<bool\> con un <xref:System.Activities.CompletionCallback%601>\<bool\> denominado `OnEvaluationCompleted`.Cuando se completa la ejecución de `Condition`, su resultado pasa a estar disponible a través de <xref:System.Activities.CompletionCallback> en un parámetro fuertemente tipado denominado `result`.If `true`, `MyWhile` llama a  <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>, pasando el objeto `Body`<xref:System.Activities.Activity> y `InternalExecute` como <xref:System.Activities.CompletionCallback>.Cuando la ejecución de `Body` se completa, `Condition` se vuelve a programar en `InternalExecute`, lo que inicia de nuevo el bucle.Cuando `Condition` devuelve `false`, una instancia de `MyWhile` devuelve el control al tiempo de ejecución sin programar el objeto `Body` y el tiempo de ejecución pasa al estado <xref:System.Activities.ActivityInstanceState>.  
  
#### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Abra la solución de prueba Composite.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Compile y ejecute la solución.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\CustomCompositeNativeActivity`  
  
## Vea también