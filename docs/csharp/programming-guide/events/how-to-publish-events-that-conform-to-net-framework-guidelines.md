---
title: 'Procedimiento Publicar eventos que cumplan las directrices de .NET Framework: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], implementation guidelines
ms.assetid: 9310ae16-8627-44a2-b08c-05e5976202b1
ms.openlocfilehash: f67789159cee64e928ae88cede9f4dbf33df1b40
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64608697"
---
# <a name="how-to-publish-events-that-conform-to-net-framework-guidelines-c-programming-guide"></a><span data-ttu-id="de1cb-102">Procedimiento Publicar eventos que cumplan las directrices de .NET Framework (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="de1cb-102">How to: Publish Events that Conform to .NET Framework Guidelines (C# Programming Guide)</span></span>
<span data-ttu-id="de1cb-103">En el siguiente procedimiento se muestra cómo agregar eventos que cumplan el patrón [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] estándar a las clases y structs.</span><span class="sxs-lookup"><span data-stu-id="de1cb-103">The following procedure demonstrates how to add events that follow the standard [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] pattern to your classes and structs.</span></span> <span data-ttu-id="de1cb-104">Todos los eventos de la biblioteca de clases [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] se basan en el delegado <xref:System.EventHandler>, que se define de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="de1cb-104">All events in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] class library are based on the <xref:System.EventHandler> delegate, which is defined as follows:</span></span>  
  
```csharp  
public delegate void EventHandler(object sender, EventArgs e);  
```  
  
> [!NOTE]
>  <span data-ttu-id="de1cb-105">[!INCLUDE[dnprdnlong](~/includes/dnprdnlong-md.md)] incluye una versión genérica de este delegado, <xref:System.EventHandler%601>.</span><span class="sxs-lookup"><span data-stu-id="de1cb-105">The [!INCLUDE[dnprdnlong](~/includes/dnprdnlong-md.md)] introduces a generic version of this delegate, <xref:System.EventHandler%601>.</span></span> <span data-ttu-id="de1cb-106">En los siguientes ejemplos se muestra cómo usar las dos versiones.</span><span class="sxs-lookup"><span data-stu-id="de1cb-106">The following examples show how to use both versions.</span></span>  
  
 <span data-ttu-id="de1cb-107">Aunque los eventos de las clases que defina se pueden basar en cualquier tipo de delegado válido, incluidos los delegados que devuelven un valor, por lo general se recomienda que base los eventos en el patrón [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] mediante <xref:System.EventHandler>, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="de1cb-107">Although events in classes that you define can be based on any valid delegate type, even delegates that return a value, it is generally recommended that you base your events on the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] pattern by using <xref:System.EventHandler>, as shown in the following example.</span></span>  
  
### <a name="to-publish-events-based-on-the-eventhandler-pattern"></a><span data-ttu-id="de1cb-108">Para publicar eventos basados en el patrón EventHandler</span><span class="sxs-lookup"><span data-stu-id="de1cb-108">To publish events based on the EventHandler pattern</span></span>  
  
1. <span data-ttu-id="de1cb-109">(Omita este paso y vaya al paso 3a si no tiene que enviar datos personalizados con el evento). Declare la clase de los datos personalizados en un ámbito que sea visible para las clases de publicador y suscriptor.</span><span class="sxs-lookup"><span data-stu-id="de1cb-109">(Skip this step and go to Step 3a if you do not have to send custom data with your event.) Declare the class for your custom data at a scope that is visible to both your publisher and subscriber classes.</span></span> <span data-ttu-id="de1cb-110">Luego, agregue los miembros necesarios para almacenar los datos de eventos personalizados.</span><span class="sxs-lookup"><span data-stu-id="de1cb-110">Then add the required members to hold your custom event data.</span></span> <span data-ttu-id="de1cb-111">En este ejemplo se devuelve una cadena simple.</span><span class="sxs-lookup"><span data-stu-id="de1cb-111">In this example, a simple string is returned.</span></span>  
  
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
  
2. <span data-ttu-id="de1cb-112">(Omita este paso si usa la versión genérica de <xref:System.EventHandler%601>). Declare un delegado en la clase de publicación.</span><span class="sxs-lookup"><span data-stu-id="de1cb-112">(Skip this step if you are using the generic version of <xref:System.EventHandler%601> .) Declare a delegate in your publishing class.</span></span> <span data-ttu-id="de1cb-113">Asígnele un nombre que acabe por *EventHandler*.</span><span class="sxs-lookup"><span data-stu-id="de1cb-113">Give it a name that ends with *EventHandler*.</span></span> <span data-ttu-id="de1cb-114">El segundo parámetro especifica el tipo EventArgs personalizado.</span><span class="sxs-lookup"><span data-stu-id="de1cb-114">The second parameter specifies your custom EventArgs type.</span></span>  
  
    ```csharp  
    public delegate void CustomEventHandler(object sender, CustomEventArgs a);  
    ```  
  
3. <span data-ttu-id="de1cb-115">Declare el evento en la clase de publicación llevando a cabo uno de los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="de1cb-115">Declare the event in your publishing class by using one of the following steps.</span></span>  
  
    1. <span data-ttu-id="de1cb-116">Si no tiene ninguna clase EventArgs personalizada, el tipo Event será el delegado EventHandler no genérico.</span><span class="sxs-lookup"><span data-stu-id="de1cb-116">If you have no custom EventArgs class, your Event type will be the non-generic EventHandler delegate.</span></span> <span data-ttu-id="de1cb-117">No es necesario declarar el delegado, porque ya está declarado en el espacio de nombres <xref:System> que se incluye al crear el proyecto de C#.</span><span class="sxs-lookup"><span data-stu-id="de1cb-117">You do not have to declare the delegate because it is already declared in the <xref:System> namespace that is included when you create your C# project.</span></span> <span data-ttu-id="de1cb-118">Agregue el código siguiente a la clase de publicador.</span><span class="sxs-lookup"><span data-stu-id="de1cb-118">Add the following code to your publisher class.</span></span>  
  
        ```csharp  
        public event EventHandler RaiseCustomEvent;  
        ```  
  
    2. <span data-ttu-id="de1cb-119">Si usa la versión no genérica de <xref:System.EventHandler> y tiene una clase personalizada derivada de <xref:System.EventArgs>, declare el evento dentro de la clase de publicación y use el delegado del paso 2 como tipo.</span><span class="sxs-lookup"><span data-stu-id="de1cb-119">If you are using the non-generic version of <xref:System.EventHandler> and you have a custom class derived from <xref:System.EventArgs>, declare your event inside your publishing class and use your delegate from step 2 as the type.</span></span>  
  
        ```csharp  
        public event CustomEventHandler RaiseCustomEvent;  
        ```  
  
    3. <span data-ttu-id="de1cb-120">Si usa la versión genérica, no necesita ningún delegado personalizado.</span><span class="sxs-lookup"><span data-stu-id="de1cb-120">If you are using the generic version, you do not need a custom delegate.</span></span> <span data-ttu-id="de1cb-121">En su lugar, en la clase de publicación, especifique el tipo de evento como `EventHandler<CustomEventArgs>`, sustituyendo el nombre de su propia clase que aparece entre corchetes angulares.</span><span class="sxs-lookup"><span data-stu-id="de1cb-121">Instead, in your publishing class, you specify your event type as `EventHandler<CustomEventArgs>`, substituting the name of your own class between the angle brackets.</span></span>  
  
        ```csharp  
        public event EventHandler<CustomEventArgs> RaiseCustomEvent;  
        ```  
  
## <a name="example"></a><span data-ttu-id="de1cb-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="de1cb-122">Example</span></span>  
 <span data-ttu-id="de1cb-123">En el siguiente ejemplo se muestran los pasos anteriores mediante el uso de una clase EventArgs personalizada y <xref:System.EventHandler%601> como tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="de1cb-123">The following example demonstrates the previous steps by using a custom EventArgs class and <xref:System.EventHandler%601> as the event type.</span></span>  
  
 [!code-csharp[csProgGuideEvents#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#2)]  
  
## <a name="see-also"></a><span data-ttu-id="de1cb-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="de1cb-124">See also</span></span>

- <xref:System.Delegate>
- [<span data-ttu-id="de1cb-125">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="de1cb-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="de1cb-126">Eventos</span><span class="sxs-lookup"><span data-stu-id="de1cb-126">Events</span></span>](../../../csharp/programming-guide/events/index.md)
- [<span data-ttu-id="de1cb-127">Delegados</span><span class="sxs-lookup"><span data-stu-id="de1cb-127">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
