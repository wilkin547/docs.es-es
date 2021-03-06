---
description: Más información acerca de cómo exponer datos con CacheMetadata
title: Exponer datos con CacheMetadata
ms.date: 03/30/2017
ms.assetid: 34832f23-e93b-40e6-a80b-606a855a00d9
ms.openlocfilehash: e3f4dc83a0e268ae548c904a714753fa025c77ae
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102259790"
---
# <a name="exposing-data-with-cachemetadata"></a>Exponer datos con CacheMetadata

Antes de ejecutar una actividad, el runtime de flujo de trabajo obtiene toda la información sobre la actividad que necesita para mantener su ejecución. El runtime de flujo de trabajo obtiene esta información durante la ejecución del método <xref:System.Activities.Activity.CacheMetadata%2A>. La implementación predeterminada de este método proporciona al runtime todas las actividades secundarias, variables y argumentos públicos expuestos por la actividad en el momento de su ejecución; si la actividad necesita proporcionar más información al runtime que la especificada (como miembros privados o actividades que va a programar la actividad), este método se puede reemplazar para proporcionarla.

## <a name="default-cachemetadata-behavior"></a>Comportamiento de CacheMetadata predeterminado

La implementación predeterminada de <xref:System.Activities.NativeActivity.CacheMetadata%2A> para las actividades que derivan de <xref:System.Activities.NativeActivity> procesa los tipos de métodos siguientes de las maneras siguientes:

- <xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601> o <xref:System.Activities.InOutArgument%601> (argumentos genéricos): estos argumentos se exponen al runtime como argumentos con un nombre y un tipo iguales al nombre y el tipo de la propiedad expuesta, la dirección de argumento apropiada y algunos datos de validación.

- <xref:System.Activities.Variable> o cualquier subclase de ella: estos miembros se exponen al runtime como variables públicas.

- <xref:System.Activities.Activity> o cualquier subclase de ella: estos miembros se exponen al runtime como actividades secundarias públicas. El comportamiento predeterminado se puede implementar explícitamente llamando a <xref:System.Activities.ActivityMetadata.AddImportedChild%2A> , pasando la actividad secundaria.

- <xref:System.Activities.ActivityDelegate> o cualquier subclase de ella: estos miembros se exponen al runtime como delegados públicos.

- <xref:System.Collections.ICollection> de tipo <xref:System.Activities.Variable>: todos los elementos de la colección se exponen al runtime como variables públicas.

- <xref:System.Collections.ICollection> de tipo <xref:System.Activities.Activity>: todos los elementos de la colección se exponen al runtime como elementos secundarios públicos.

- <xref:System.Collections.ICollection> de tipo <xref:System.Activities.ActivityDelegate>: todos los elementos de la colección se exponen al runtime como delegados públicos.

El método <xref:System.Activities.Activity.CacheMetadata%2A> para las actividades que derivan de <xref:System.Activities.Activity>, <xref:System.Workflow.Activities.CodeActivity> y <xref:System.Activities.AsyncCodeActivity> también funciona como en los casos anteriores, exceptuando las diferencias siguientes:

- Las clases que derivan de <xref:System.Activities.Activity> no pueden programar actividades secundarias ni delegados, por lo que dichos miembros se exponen como elementos secundarios y delegados importados.

- Las clases que derivan de <xref:System.Activities.CodeActivity> y <xref:System.Activities.AsyncCodeActivity> no admiten variables, elementos secundarios o delegados, por lo que solo se expondrán argumentos.

## <a name="overriding-cachemetadata-to-provide-information-to-the-runtime"></a>Reemplazar CacheMetadata para proporcionar información al runtime

El siguiente fragmento de código muestra cómo agregar información sobre miembros a los metadatos de una actividad durante la ejecución del método <xref:System.Activities.Activity.CacheMetadata%2A>. Observe que se llama a la base del método para almacenar en memoria caché todos los datos públicos sobre la actividad.

```csharp
protected override void CacheMetadata(NativeActivityMetadata metadata)
{
    base.CacheMetadata(metadata);
    metadata.AddImplementationChild(this._writeLine);
    metadata.AddVariable(this._myVariable);
    metadata.AddImplementationVariable(this._myImplementationVariable);

    RuntimeArgument argument = new RuntimeArgument("MyArgument", ArgumentDirection.In, typeof(SomeType));
    metadata.Bind(argument, this.SomeName);
    metadata.AddArgument(argument);
}
```

## <a name="using-cachemetadata-to-expose-implementation-children"></a>Utilizar CacheMetadata para exponer los elementos secundarios de implementación

Para pasar datos a actividades secundarias que van a ser programadas por una actividad utilizando variables, es necesario agregar las variables como variables de implementación; las variables públicas no pueden tener establecidos sus valores de esta manera. La razón de ello es que las actividades están previstas para ser ejecutadas como implementaciones de funciones (que tienen parámetros), en lugar de clases encapsuladas (que tienen propiedades). Sin embargo, hay situaciones en que los argumentos se deben establecer explícitamente, como cuando se utiliza <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>, ya que la actividad programada no tiene acceso a los argumentos de la actividad principal de la manera que una actividad secundaria lo tendría.

En el fragmento de código siguiente se muestra cómo pasar un argumento de una actividad nativa a una actividad programada mediante <xref:System.Activities.Activity.CacheMetadata%2A> .

```csharp
public sealed class ChildActivity : NativeActivity
{
    public WriteLine _writeLine;
    public InArgument<string> Message { get; set; }
    private Variable<string> MessageVariable { get; set; }
    public ChildActivity()
    {
        MessageVariable = new Variable<string>();
        _writeLine = new WriteLine
        {
            Text = new InArgument<string>(MessageVariable),
        };
    }
    protected override void CacheMetadata(NativeActivityMetadata metadata)
    {
        base.CacheMetadata(metadata);
        metadata.AddImplementationVariable(this.MessageVariable);
        metadata.AddImplementationChild(this._writeLine);
    }
    protected override void Execute(NativeActivityContext context)
    {
        string configuredMessage = context.GetValue(Message);
        context.SetValue(MessageVariable, configuredMessage);
        context.ScheduleActivity(this._writeLine);
    }
}
```
