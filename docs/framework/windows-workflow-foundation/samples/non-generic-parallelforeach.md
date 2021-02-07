---
description: 'Más información sobre: ParallelForEach no genéricos'
title: ParallelForEach no genérico
ms.date: 03/30/2017
ms.assetid: de17e7a2-257b-48b3-91a1-860e2e9bf6e6
ms.openlocfilehash: 9eaa4ed565fa00a0479f21d907fe5433317d88f8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741944"
---
# <a name="non-generic-parallelforeach"></a>ParallelForEach no genérico

[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] incluye en su cuadro de herramientas un conjunto de actividades Control Flow, como la actividad <xref:System.Activities.Statements.ParallelForEach%601>, que permite recorrer en iteración colecciones <xref:System.Collections.Generic.IEnumerable%601>.

<xref:System.Activities.Statements.ParallelForEach%601> requiere <xref:System.Activities.Statements.ParallelForEach%601.Values%2A> que su propiedad sea del tipo  <xref:System.Collections.Generic.IEnumerable%601> . Esto impide a los usuarios recorrer en iteración estructuras de datos que implementan la interfaz <xref:System.Collections.Generic.IEnumerable%601> (por ejemplo, <xref:System.Collections.ArrayList>). La versión no genérica de <xref:System.Activities.Statements.ParallelForEach%601> supera este requisito, a costa de una mayor complejidad del tiempo de ejecución para garantizar la compatibilidad de los tipos de los valores de la colección.

En este ejemplo se muestra cómo implementar una actividad <xref:System.Activities.Statements.ParallelForEach%601> no genérica y su diseñador. Esta actividad se puede utilizar para recorrer en iteración <xref:System.Collections.ArrayList>.

## <a name="parallelforeach-activity"></a>Actividad ParallelForEach

La instrucción de C#/Visual Basic `foreach` enumera los elementos de una colección y ejecuta una instrucción incrustada para cada elemento de la colección. Las actividades equivalentes de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] son <xref:System.Activities.Statements.ForEach%601> y <xref:System.Activities.Statements.ParallelForEach%601>. La actividad <xref:System.Activities.Statements.ForEach%601> contiene una lista de valores y un cuerpo. En el tiempo de ejecución, la lista se recorre en iteración y se ejecuta el cuerpo para cada valor de la lista.

<xref:System.Activities.Statements.ParallelForEach%601> tiene una condición <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>, para que la actividad <xref:System.Activities.Statements.ParallelForEach%601> se pueda completar antes si la evaluación de la condición <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> devuelve `true`. La propiedad <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> se evalúa después de completar cada iteración.

En la mayoría de los casos, la versión genérica de la actividad debe ser la solución preferida, porque abarca la mayoría de los escenarios en los que se utiliza y proporciona comprobación de tipos en tiempo de compilación. La versión no genérica se puede utilizar para recorrer en iteración tipos que implementan la interfaz <xref:System.Collections.IEnumerable> no genérica.

## <a name="class-definition"></a>Definición de clase

El siguiente ejemplo de código muestra la definición de una actividad `ParallelForEach` no genérica.

```csharp
[ContentProperty("Body")]
public class ParallelForEach : NativeActivity
{
    [RequiredArgument]
    [DefaultValue(null)]
    InArgument<IEnumerable> Values { get; set; }

    [DefaultValue(null)]
    [DependsOn("Values")]
    public Activity<bool> CompletionCondition
    [DefaultValue(null)]
    [DependsOn("CompletionCondition")]
    ActivityAction<object> Body { get; set; }
}
```

Cuerpo (opcional) \
<xref:System.Activities.ActivityAction> de tipo <xref:System.Object>, que se ejecuta para cada elemento en la colección. Cada elemento individual se pasa al cuerpo a través de su propiedad Argument.

Valores (opcional) \
La colección de elementos que se recorre en iteración. La verificación de que todos los elementos de la colección son de tipos compatibles se realiza en el tiempo de ejecución.

CompletionCondition (opcional) \
La propiedad <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> se evalúa después de completarse cada iteración. Si se evalúa como `true`, se cancelan las iteraciones programadas pendientes. Si esta propiedad no está establecida, todas las actividades de la colección Branches se ejecutan hasta su finalización.

## <a name="example-of-using-parallelforeach"></a>Ejemplo del uso de ParallelForEach

El siguiente código muestra cómo utilizar la actividad ParallelForEach en una aplicación.

```csharp
string[] names = { "bill", "steve", "ray" };

DelegateInArgument<object> iterationVariable = new DelegateInArgument<object>() { Name = "iterationVariable" };

Activity sampleUsage =
    new ParallelForEach
    {
       Values = new InArgument<IEnumerable>(c=> names),
       Body = new ActivityAction<object>
       {
           Argument = iterationVariable,
           Handler = new WriteLine
           {
               Text = new InArgument<string>(env => string.Format("Hello {0}",                                                               iterationVariable.Get(env)))
           }
       }
   };
```

## <a name="parallelforeach-designer"></a>Diseñador de ParallelForEach

El diseñador de actividad del ejemplo es similar en aspecto al diseñador proporcionado para la actividad <xref:System.Activities.Statements.ParallelForEach%601> integrada. El diseñador aparece en el cuadro de herramientas en la categoría **ejemplos**, **actividades no genéricas** . El diseñador se denomina **ParallelForEachWithBodyFactory** en el cuadro de herramientas, porque la actividad expone un <xref:System.Activities.Presentation.IActivityTemplateFactory> en el cuadro de herramientas que crea la actividad con un configurado correctamente <xref:System.Activities.ActivityAction> .

```csharp
public sealed class ParallelForEachWithBodyFactory : IActivityTemplateFactory
{
    public Activity Create(DependencyObject target)
    {
        return new Microsoft.Samples.Activities.Statements.ParallelForEach()
        {
            Body = new ActivityAction<object>()
            {
                Argument = new DelegateInArgument<object>()
                {
                    Name = "item"
                }
            }
        };
    }
}
```

## <a name="to-run-the-sample"></a>Para ejecutar el ejemplo

1. Establezca el proyecto que desee como el proyecto de inicio de la solución.

    1. **CodeTestClient** muestra cómo utilizar la actividad mediante código.

    2. **DesignerTestClient** muestra cómo utilizar la actividad en el diseñador.

2. Compile y ejecute el proyecto.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NonGenericParallelForEach`
