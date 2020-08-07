---
title: Publicación de eventos que cumplan las directrices de .NET Framework (guía de programación de C#)
description: Aprenda a publicar eventos que cumplan las instrucciones de .NET. Todos los eventos de la biblioteca de clases de .NET Framework se basan en el delegado EventHandler.
ms.date: 05/26/2020
helpviewer_keywords:
- events [C#], implementation guidelines
ms.assetid: 9310ae16-8627-44a2-b08c-05e5976202b1
ms.openlocfilehash: 1b802e236026911b55bafcb3f48d487c43bba174
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302118"
---
# <a name="how-to-publish-events-that-conform-to-net-guidelines-c-programming-guide"></a><span data-ttu-id="7582e-104">Procedimiento Publicar eventos que cumplan las directrices de .NET (guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="7582e-104">How to publish events that conform to .NET Guidelines (C# Programming Guide)</span></span>

<span data-ttu-id="7582e-105">En el siguiente procedimiento se muestra cómo agregar eventos que cumplan el patrón de .NET estándar a las clases y structs.</span><span class="sxs-lookup"><span data-stu-id="7582e-105">The following procedure demonstrates how to add events that follow the standard .NET pattern to your classes and structs.</span></span> <span data-ttu-id="7582e-106">Todos los eventos de la biblioteca de clases de .NET Framework se basan en el delegado <xref:System.EventHandler>, que se define de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="7582e-106">All events in the .NET Framework class library are based on the <xref:System.EventHandler> delegate, which is defined as follows:</span></span>

```csharp
public delegate void EventHandler(object sender, EventArgs e);
```

> [!NOTE]
> <span data-ttu-id="7582e-107">.NET Framework 2.0 incluye una versión genérica de este delegado, <xref:System.EventHandler%601>.</span><span class="sxs-lookup"><span data-stu-id="7582e-107">.NET Framework 2.0 introduces a generic version of this delegate, <xref:System.EventHandler%601>.</span></span> <span data-ttu-id="7582e-108">En los siguientes ejemplos se muestra cómo usar las dos versiones.</span><span class="sxs-lookup"><span data-stu-id="7582e-108">The following examples show how to use both versions.</span></span>

<span data-ttu-id="7582e-109">Aunque los eventos de las clases que defina se pueden basar en cualquier tipo de delegado válido, incluidos los delegados que devuelven un valor, por lo general se recomienda que base los eventos en el patrón de .NET mediante <xref:System.EventHandler>, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="7582e-109">Although events in classes that you define can be based on any valid delegate type, even delegates that return a value, it is generally recommended that you base your events on the .NET pattern by using <xref:System.EventHandler>, as shown in the following example.</span></span>

<span data-ttu-id="7582e-110">El nombre `EventHandler` puede dar lugar a un poco de confusión, ya que realmente no controla el evento.</span><span class="sxs-lookup"><span data-stu-id="7582e-110">The name `EventHandler` can lead to a bit of confusion as it doesn't actually handle the event.</span></span> <span data-ttu-id="7582e-111"><xref:System.EventHandler> y <xref:System.EventHandler%601> genérico son tipos de delegado.</span><span class="sxs-lookup"><span data-stu-id="7582e-111">The <xref:System.EventHandler>, and generic <xref:System.EventHandler%601> are delegate types.</span></span> <span data-ttu-id="7582e-112">Un método o una expresión lambda cuya firma coincide con la definición de delegado es el *controlador de eventos* y se invocará cuando se genere el evento.</span><span class="sxs-lookup"><span data-stu-id="7582e-112">A method or lambda expression whose signature matches the delegate definition is the *event handler* and will be invoked when the event is raised.</span></span>

## <a name="publish-events-based-on-the-eventhandler-pattern"></a><span data-ttu-id="7582e-113">Publicación de eventos basados en el patrón EventHandler</span><span class="sxs-lookup"><span data-stu-id="7582e-113">Publish events based on the EventHandler pattern</span></span>

1. <span data-ttu-id="7582e-114">(Omita este paso y vaya al paso 3a si no tiene que enviar datos personalizados con el evento). Declare la clase de los datos personalizados en un ámbito que sea visible para las clases de publicador y suscriptor.</span><span class="sxs-lookup"><span data-stu-id="7582e-114">(Skip this step and go to Step 3a if you do not have to send custom data with your event.) Declare the class for your custom data at a scope that is visible to both your publisher and subscriber classes.</span></span> <span data-ttu-id="7582e-115">Luego, agregue los miembros necesarios para almacenar los datos de eventos personalizados.</span><span class="sxs-lookup"><span data-stu-id="7582e-115">Then add the required members to hold your custom event data.</span></span> <span data-ttu-id="7582e-116">En este ejemplo se devuelve una cadena simple.</span><span class="sxs-lookup"><span data-stu-id="7582e-116">In this example, a simple string is returned.</span></span>

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

2. <span data-ttu-id="7582e-117">(Omita este paso si usa la versión genérica de <xref:System.EventHandler%601>). Declare un delegado en la clase de publicación.</span><span class="sxs-lookup"><span data-stu-id="7582e-117">(Skip this step if you are using the generic version of <xref:System.EventHandler%601>.) Declare a delegate in your publishing class.</span></span> <span data-ttu-id="7582e-118">Asígnele un nombre que termine con `EventHandler`.</span><span class="sxs-lookup"><span data-stu-id="7582e-118">Give it a name that ends with `EventHandler`.</span></span> <span data-ttu-id="7582e-119">El segundo parámetro especifica el tipo `EventArgs` personalizado.</span><span class="sxs-lookup"><span data-stu-id="7582e-119">The second parameter specifies your custom `EventArgs` type.</span></span>

    ```csharp
    public delegate void CustomEventHandler(object sender, CustomEventArgs args);
    ```

3. <span data-ttu-id="7582e-120">Declare el evento en la clase de publicación llevando a cabo uno de los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="7582e-120">Declare the event in your publishing class by using one of the following steps.</span></span>

    1. <span data-ttu-id="7582e-121">Si no tiene ninguna clase EventArgs personalizada, el tipo Event será el delegado EventHandler no genérico.</span><span class="sxs-lookup"><span data-stu-id="7582e-121">If you have no custom EventArgs class, your Event type will be the non-generic EventHandler delegate.</span></span> <span data-ttu-id="7582e-122">No es necesario declarar el delegado, porque ya está declarado en el espacio de nombres <xref:System> que se incluye al crear el proyecto de C#.</span><span class="sxs-lookup"><span data-stu-id="7582e-122">You do not have to declare the delegate because it is already declared in the <xref:System> namespace that is included when you create your C# project.</span></span> <span data-ttu-id="7582e-123">Agregue el código siguiente a la clase de publicador.</span><span class="sxs-lookup"><span data-stu-id="7582e-123">Add the following code to your publisher class.</span></span>

        ```csharp
        public event EventHandler RaiseCustomEvent;
        ```

    2. <span data-ttu-id="7582e-124">Si usa la versión no genérica de <xref:System.EventHandler> y tiene una clase personalizada derivada de <xref:System.EventArgs>, declare el evento dentro de la clase de publicación y use el delegado del paso 2 como tipo.</span><span class="sxs-lookup"><span data-stu-id="7582e-124">If you are using the non-generic version of <xref:System.EventHandler> and you have a custom class derived from <xref:System.EventArgs>, declare your event inside your publishing class and use your delegate from step 2 as the type.</span></span>

        ```csharp
        public event CustomEventHandler RaiseCustomEvent;
        ```

    3. <span data-ttu-id="7582e-125">Si usa la versión genérica, no necesita ningún delegado personalizado.</span><span class="sxs-lookup"><span data-stu-id="7582e-125">If you are using the generic version, you do not need a custom delegate.</span></span> <span data-ttu-id="7582e-126">En su lugar, en la clase de publicación, especifique el tipo de evento como `EventHandler<CustomEventArgs>`, sustituyendo el nombre de su propia clase que aparece entre corchetes angulares.</span><span class="sxs-lookup"><span data-stu-id="7582e-126">Instead, in your publishing class, you specify your event type as `EventHandler<CustomEventArgs>`, substituting the name of your own class between the angle brackets.</span></span>

        ```csharp
        public event EventHandler<CustomEventArgs> RaiseCustomEvent;
        ```

## <a name="example"></a><span data-ttu-id="7582e-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7582e-127">Example</span></span>

<span data-ttu-id="7582e-128">En el siguiente ejemplo se muestran los pasos anteriores mediante el uso de una clase EventArgs personalizada y <xref:System.EventHandler%601> como tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="7582e-128">The following example demonstrates the previous steps by using a custom EventArgs class and <xref:System.EventHandler%601> as the event type.</span></span>

[!code-csharp[csProgGuideEvents#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#2)]

## <a name="see-also"></a><span data-ttu-id="7582e-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="7582e-129">See also</span></span>

- <xref:System.Delegate>
- [<span data-ttu-id="7582e-130">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="7582e-130">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="7582e-131">Eventos</span><span class="sxs-lookup"><span data-stu-id="7582e-131">Events</span></span>](index.md)
- [<span data-ttu-id="7582e-132">Delegados</span><span class="sxs-lookup"><span data-stu-id="7582e-132">Delegates</span></span>](../delegates/index.md)
