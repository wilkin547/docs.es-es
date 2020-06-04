---
title: 'Procedimiento Publicar eventos que cumplan las directrices de .NET Framework: Guía de programación de C#'
ms.date: 05/26/2020
helpviewer_keywords:
- events [C#], implementation guidelines
ms.assetid: 9310ae16-8627-44a2-b08c-05e5976202b1
ms.openlocfilehash: 137e52b80703491a4528a3eddc7fa12f9dce6f52
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144804"
---
# <a name="how-to-publish-events-that-conform-to-net-framework-guidelines-c-programming-guide"></a>Procedimiento Publicar eventos que cumplan las directrices de .NET Framework (Guía de programación de C#)

En el siguiente procedimiento se muestra cómo agregar eventos que cumplan el patrón de .NET Framework estándar para las clases y los structs. Todos los eventos de la biblioteca de clases de .NET Framework se basan en el delegado <xref:System.EventHandler>, que se define de la siguiente manera:

```csharp
public delegate void EventHandler(object sender, EventArgs e);
```

> [!NOTE]
> .NET Framework 2.0 incluye una versión genérica de este delegado, <xref:System.EventHandler%601>. En los siguientes ejemplos se muestra cómo usar las dos versiones.

Aunque los eventos de las clases que defina se pueden basar en cualquier tipo de delegado válido, incluidos los delegados que devuelven un valor, por lo general se recomienda basar los eventos en el patrón de .NET Framework mediante <xref:System.EventHandler>, como se muestra en el ejemplo siguiente.

El nombre `EventHandler` puede dar lugar a un poco de confusión, ya que realmente no controla el evento. <xref:System.EventHandler> y <xref:System.EventHandler%601> genérico son tipos de delegado. Un método o una expresión lambda cuya firma coincide con la definición de delegado es el *controlador de eventos* y se invocará cuando se genere el evento.

### <a name="to-publish-events-based-on-the-eventhandler-pattern"></a>Para publicar eventos basados en el patrón EventHandler

1. (Omita este paso y vaya al paso 3a si no tiene que enviar datos personalizados con el evento). Declare la clase de los datos personalizados en un ámbito que sea visible para las clases de publicador y suscriptor. Luego, agregue los miembros necesarios para almacenar los datos de eventos personalizados. En este ejemplo se devuelve una cadena simple.

    ```csharp
    public class CustomEventArgs : EventArgs
    {
        public CustomEventArgs(string message)
        {
            Message = message;
        }

        public string Message { get; set; }
    }
    ```

2. (Omita este paso si usa la versión genérica de <xref:System.EventHandler%601>). Declare un delegado en la clase de publicación. Asígnele un nombre que termine con `EventHandler`. El segundo parámetro especifica el tipo `EventArgs` personalizado.

    ```csharp
    public delegate void CustomEventHandler(object sender, CustomEventArgs args);
    ```

3. Declare el evento en la clase de publicación llevando a cabo uno de los siguientes pasos.

    1. Si no tiene ninguna clase EventArgs personalizada, el tipo Event será el delegado EventHandler no genérico. No es necesario declarar el delegado, porque ya está declarado en el espacio de nombres <xref:System> que se incluye al crear el proyecto de C#. Agregue el código siguiente a la clase de publicador.

        ```csharp
        public event EventHandler RaiseCustomEvent;
        ```

    2. Si usa la versión no genérica de <xref:System.EventHandler> y tiene una clase personalizada derivada de <xref:System.EventArgs>, declare el evento dentro de la clase de publicación y use el delegado del paso 2 como tipo.

        ```csharp
        public event CustomEventHandler RaiseCustomEvent;
        ```

    3. Si usa la versión genérica, no necesita ningún delegado personalizado. En su lugar, en la clase de publicación, especifique el tipo de evento como `EventHandler<CustomEventArgs>`, sustituyendo el nombre de su propia clase que aparece entre corchetes angulares.

        ```csharp
        public event EventHandler<CustomEventArgs> RaiseCustomEvent;
        ```

## <a name="example"></a>Ejemplo

En el siguiente ejemplo se muestran los pasos anteriores mediante el uso de una clase EventArgs personalizada y <xref:System.EventHandler%601> como tipo de evento.

[!code-csharp[csProgGuideEvents#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#2)]

## <a name="see-also"></a>Vea también

- <xref:System.Delegate>
- [Guía de programación de C#](../index.md)
- [Eventos](index.md)
- [Delegados](../delegates/index.md)
