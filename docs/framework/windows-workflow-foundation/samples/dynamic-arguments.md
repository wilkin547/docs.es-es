---
title: Argumentos dinámicos
ms.date: 03/30/2017
ms.assetid: 122ad479-d306-4602-a943-5aefe711329d
ms.openlocfilehash: 5c00b9678191e4e88e9e41380d6b10be39684b3b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="dynamic-arguments"></a>Argumentos dinámicos
En este ejemplo se muestra cómo implementar una actividad para la que define los argumentos el consumidor de la actividad y no su autor. Para ello se invalida la forma en que el motor en tiempo de ejecución construye los metadatos de la actividad.  
  
## <a name="sample-details"></a>Detalles del ejemplo  
 Antes de la ejecución, el motor en tiempo de ejecución compila una descripción de una actividad mediante el examen de los miembros públicos del tipo de actividad y la declaración automática de los argumentos, variables, actividades secundarias y delegados de actividad como parte de los metadatos de una actividad. Esto lo realiza para asegurar la construcción correcta de un flujo de trabajo, así como para administrar relaciones en tiempo de ejecución y reglas de duración. Normalmente un autor de actividad define los argumentos de una actividad especificando los miembros públicos en el tipo de actividad que derivan de <xref:System.Activities.Argument>. Por cada miembro público que deriva de <xref:System.Activities.Argument>, el motor en tiempo de ejecución crea una clase <xref:System.Activities.RuntimeArgument> y la enlaza con el argumento proporcionado por el usuario en dicho miembro. En algunos casos, sin embargo, el consumidor de la actividad proporciona alguna configuración que determina el conjunto de argumentos. Un autor de actividad invalida el método <xref:System.Activities.Activity.CacheMetadata%2A> para personalizar la manera en que se compilan los metadatos de la actividad, lo que incluye el conjunto de argumentos asociados a la actividad.  
  
 En este ejemplo se muestra cómo compilar dinámicamente una lista de argumentos para una actividad que invoca un método. El consumidor de la actividad especifica el tipo y el nombre del método que desea invocar junto con una colección de argumentos que se van a pasar a ese método.  
  
> [!NOTE]
>  Este ejemplo pretende mostrar cómo invalidar el método <xref:System.Activities.CodeActivity.CacheMetadata%2A> y cómo usar la clase <xref:System.Activities.RuntimeArgument>. Existen algunas advertencias con respecto a los tipos de métodos que esta actividad puede invocar. Por ejemplo, no funciona con genéricos ni con matrices de parámetros. La actividad <xref:System.Activities.Statements.InvokeMethod> que se distribuye con .NET Framework controla estos y otros casos.  
  
 La actividad `MethodInvoke` invalida el método <xref:System.Activities.CodeActivity.CacheMetadata%2A> y comienza creando una clase <xref:System.Activities.RuntimeArgument> para administrar cualquier resultado de la invocación del método. Enlaza esta clase <xref:System.Activities.RuntimeArgument> a la clase <xref:System.Activities.OutArgument> que se puede establecer públicamente denominada `Result`. Si `MethodInvoke.Result` es `null`, el motor en tiempo de ejecución lo rellena automáticamente con una clase <xref:System.Activities.OutArgument> configurada con la expresión predeterminado para su tipo. Este comportamiento significa que un autor de actividad nunca tiene que comprobar si una propiedad de argumento es `null`.  
  
 A continuación, la invalidación del método<xref:System.Activities.CodeActivity.CacheMetadata%2A> determina la clase `MethodInfo` que utiliza para la invocación desde los parámetros `MethodName` y `TargetType` proporcionados por el usuario. El método `DetermineMethodInfo` toma el parámetro <xref:System.Activities.CodeActivityMetadata> pasado a la invalidación del método <xref:System.Activities.CodeActivity.CacheMetadata%2A> de forma que los errores de configuración se puedan notificar como errores de validación. Esto se hace llamando a `metadata.AddValidationError`.  
  
 Una vez establecido el parámetro `MethodInfo`, el ejemplo recorre en iteración los parámetros `MethodInfo`. Para cada parámetro, crea una clase <xref:System.Activities.RuntimeArgument> y la enlaza con el argumento correspondiente en la colección proporcionada por el usuario de la propiedad `Parameters`. Por último, la colección de <xref:System.Activities.RuntimeArgument>s se asocia a la actividad llamando a `metadata.SetArgumentsCollection`.  
  
 Observe que la resolución de argumento se puede realizar mediante una clase <xref:System.Activities.RuntimeArgument>, como en el caso de `resultArgument` o el argumento proporcionado por usuario, como en el caso de la colección `Parameters`.  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Mediante [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo DynamicArguments.sln.  
  
2.  Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
3.  Para ejecutar la solución, presione CTRL+F5.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\DynamicArguments`