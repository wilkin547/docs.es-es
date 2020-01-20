---
title: 'Procedimiento Publicar eventos que cumplan las directrices de .NET Framework: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], implementation guidelines
ms.assetid: 9310ae16-8627-44a2-b08c-05e5976202b1
ms.openlocfilehash: 0ae240d0c078b5eaa690f128c037ee2471325872
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705345"
---
# <a name="how-to-publish-events-that-conform-to-net-framework-guidelines-c-programming-guide"></a><span data-ttu-id="edba8-102">Procedimiento Publicar eventos que cumplan las directrices de .NET Framework (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="edba8-102">How to publish events that conform to .NET Framework Guidelines (C# Programming Guide)</span></span>
<span data-ttu-id="edba8-103">En el siguiente procedimiento se muestra cómo agregar eventos que cumplan el patrón de .NET Framework estándar para las clases y los structs.</span><span class="sxs-lookup"><span data-stu-id="edba8-103">The following procedure demonstrates how to add events that follow the standard .NET Framework pattern to your classes and structs.</span></span> <span data-ttu-id="edba8-104">Todos los eventos de la biblioteca de clases de .NET Framework se basan en el delegado <xref:System.EventHandler>, que se define de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="edba8-104">All events in the .NET Framework class library are based on the <xref:System.EventHandler> delegate, which is defined as follows:</span></span>  
  
```csharp  
public delegate void EventHandler(object sender, EventArgs e);  
```  
  
> [!NOTE]
> <span data-ttu-id="edba8-105">.NET Framework 2.0 incluye una versión genérica de este delegado, <xref:System.EventHandler%601>.</span><span class="sxs-lookup"><span data-stu-id="edba8-105">The .NET Framework 2.0 introduces a generic version of this delegate, <xref:System.EventHandler%601>.</span></span> <span data-ttu-id="edba8-106">En los siguientes ejemplos se muestra cómo usar las dos versiones.</span><span class="sxs-lookup"><span data-stu-id="edba8-106">The following examples show how to use both versions.</span></span>  
  
 <span data-ttu-id="edba8-107">Aunque los eventos de las clases que defina se pueden basar en cualquier tipo de delegado válido, incluidos los delegados que devuelven un valor, por lo general se recomienda basar los eventos en el patrón de .NET Framework mediante <xref:System.EventHandler>, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="edba8-107">Although events in classes that you define can be based on any valid delegate type, even delegates that return a value, it is generally recommended that you base your events on the .NET Framework pattern by using <xref:System.EventHandler>, as shown in the following example.</span></span>  
  
### <a name="to-publish-events-based-on-the-eventhandler-pattern"></a><span data-ttu-id="edba8-108">Para publicar eventos basados en el patrón EventHandler</span><span class="sxs-lookup"><span data-stu-id="edba8-108">To publish events based on the EventHandler pattern</span></span>  
  
1. <span data-ttu-id="edba8-109">(Omita este paso y vaya al paso 3a si no tiene que enviar datos personalizados con el evento). Declare la clase de los datos personalizados en un ámbito que sea visible para las clases de publicador y suscriptor.</span><span class="sxs-lookup"><span data-stu-id="edba8-109">(Skip this step and go to Step 3a if you do not have to send custom data with your event.) Declare the class for your custom data at a scope that is visible to both your publisher and subscriber classes.</span></span> <span data-ttu-id="edba8-110">Luego, agregue los miembros necesarios para almacenar los datos de eventos personalizados.</span><span class="sxs-lookup"><span data-stu-id="edba8-110">Then add the required members to hold your custom event data.</span></span> <span data-ttu-id="edba8-111">En este ejemplo se devuelve una cadena simple.</span><span class="sxs-lookup"><span data-stu-id="edba8-111">In this example, a simple string is returned.</span></span>  
  
    ```csharp  
    public class CustomEventArgs : EventArgs  
    {  
        public CustomEventArgs(string s)  
        {  
            msg = s;  
        }  
        private string msg;  
        public string Message  
        {  
            get { return msg; }  
        }   
    }  
    ```  
  
2. <span data-ttu-id="edba8-112">(Omita este paso si usa la versión genérica de <xref:System.EventHandler%601>). Declare un delegado en la clase de publicación.</span><span class="sxs-lookup"><span data-stu-id="edba8-112">(Skip this step if you are using the generic version of <xref:System.EventHandler%601> .) Declare a delegate in your publishing class.</span></span> <span data-ttu-id="edba8-113">Asígnele un nombre que acabe por *EventHandler*.</span><span class="sxs-lookup"><span data-stu-id="edba8-113">Give it a name that ends with *EventHandler*.</span></span> <span data-ttu-id="edba8-114">El segundo parámetro especifica el tipo EventArgs personalizado.</span><span class="sxs-lookup"><span data-stu-id="edba8-114">The second parameter specifies your custom EventArgs type.</span></span>  
  
    ```csharp  
    public delegate void CustomEventHandler(object sender, CustomEventArgs a);  
    ```  
  
3. <span data-ttu-id="edba8-115">Declare el evento en la clase de publicación llevando a cabo uno de los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="edba8-115">Declare the event in your publishing class by using one of the following steps.</span></span>  
  
    1. <span data-ttu-id="edba8-116">Si no tiene ninguna clase EventArgs personalizada, el tipo Event será el delegado EventHandler no genérico.</span><span class="sxs-lookup"><span data-stu-id="edba8-116">If you have no custom EventArgs class, your Event type will be the non-generic EventHandler delegate.</span></span> <span data-ttu-id="edba8-117">No es necesario declarar el delegado, porque ya está declarado en el espacio de nombres <xref:System> que se incluye al crear el proyecto de C#.</span><span class="sxs-lookup"><span data-stu-id="edba8-117">You do not have to declare the delegate because it is already declared in the <xref:System> namespace that is included when you create your C# project.</span></span> <span data-ttu-id="edba8-118">Agregue el código siguiente a la clase de publicador.</span><span class="sxs-lookup"><span data-stu-id="edba8-118">Add the following code to your publisher class.</span></span>  
  
        ```csharp  
        public event EventHandler RaiseCustomEvent;  
        ```  
  
    2. <span data-ttu-id="edba8-119">Si usa la versión no genérica de <xref:System.EventHandler> y tiene una clase personalizada derivada de <xref:System.EventArgs>, declare el evento dentro de la clase de publicación y use el delegado del paso 2 como tipo.</span><span class="sxs-lookup"><span data-stu-id="edba8-119">If you are using the non-generic version of <xref:System.EventHandler> and you have a custom class derived from <xref:System.EventArgs>, declare your event inside your publishing class and use your delegate from step 2 as the type.</span></span>  
  
        ```csharp  
        public event CustomEventHandler RaiseCustomEvent;  
        ```  
  
    3. <span data-ttu-id="edba8-120">Si usa la versión genérica, no necesita ningún delegado personalizado.</span><span class="sxs-lookup"><span data-stu-id="edba8-120">If you are using the generic version, you do not need a custom delegate.</span></span> <span data-ttu-id="edba8-121">En su lugar, en la clase de publicación, especifique el tipo de evento como `EventHandler<CustomEventArgs>`, sustituyendo el nombre de su propia clase que aparece entre corchetes angulares.</span><span class="sxs-lookup"><span data-stu-id="edba8-121">Instead, in your publishing class, you specify your event type as `EventHandler<CustomEventArgs>`, substituting the name of your own class between the angle brackets.</span></span>  
  
        ```csharp  
        public event EventHandler<CustomEventArgs> RaiseCustomEvent;  
        ```  
  
## <a name="example"></a><span data-ttu-id="edba8-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="edba8-122">Example</span></span>  
 <span data-ttu-id="edba8-123">En el siguiente ejemplo se muestran los pasos anteriores mediante el uso de una clase EventArgs personalizada y <xref:System.EventHandler%601> como tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="edba8-123">The following example demonstrates the previous steps by using a custom EventArgs class and <xref:System.EventHandler%601> as the event type.</span></span>  
  
 [!code-csharp[csProgGuideEvents#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#2)]  
  
## <a name="see-also"></a><span data-ttu-id="edba8-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="edba8-124">See also</span></span>

- <xref:System.Delegate>
- [<span data-ttu-id="edba8-125">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="edba8-125">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="edba8-126">Eventos</span><span class="sxs-lookup"><span data-stu-id="edba8-126">Events</span></span>](./index.md)
- [<span data-ttu-id="edba8-127">Delegados</span><span class="sxs-lookup"><span data-stu-id="edba8-127">Delegates</span></span>](../delegates/index.md)
