---
title: "Cómo: Implementar un observador"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- observers [.NET Framework], observer design pattern
- observer design pattern [.NET Framework], implementing observers
ms.assetid: 8ecfa9f5-b500-473d-bcf0-5652ffb1e53d
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a964bd031f6f8a7fc029b2b209b9693b72e688af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-an-observer"></a><span data-ttu-id="227dd-102">Cómo: Implementar un observador</span><span class="sxs-lookup"><span data-stu-id="227dd-102">How to: Implement an Observer</span></span>
<span data-ttu-id="227dd-103">El modelo de diseño de observador requiere una división entre un observador, que se registra para las notificaciones, y un proveedor, que supervisa los datos y envía notificaciones a los observadores de uno o más.</span><span class="sxs-lookup"><span data-stu-id="227dd-103">The observer design pattern requires a division between an observer, which registers for notifications, and a provider, which monitors data and sends notifications to one or more observers.</span></span> <span data-ttu-id="227dd-104">En este tema se describe cómo crear un observador.</span><span class="sxs-lookup"><span data-stu-id="227dd-104">This topic discusses how to create an observer.</span></span> <span data-ttu-id="227dd-105">Un tema relacionado, [Cómo: implementar un proveedor de](../../../docs/standard/events/how-to-implement-a-provider.md), se describe cómo crear un proveedor.</span><span class="sxs-lookup"><span data-stu-id="227dd-105">A related topic, [How to: Implement a Provider](../../../docs/standard/events/how-to-implement-a-provider.md), discusses how to create an provider.</span></span>  
  
### <a name="to-create-an-observer"></a><span data-ttu-id="227dd-106">Para crear un observador</span><span class="sxs-lookup"><span data-stu-id="227dd-106">To create an observer</span></span>  
  
1.  <span data-ttu-id="227dd-107">Definir el observador, que es un tipo que implementa el <xref:System.IObserver%601?displayProperty=nameWithType> interfaz.</span><span class="sxs-lookup"><span data-stu-id="227dd-107">Define the observer, which is a type that implements the <xref:System.IObserver%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="227dd-108">Por ejemplo, el código siguiente define un tipo denominado `TemperatureReporter` que es un construido <xref:System.IObserver%601?displayProperty=nameWithType> implementación con un argumento de tipo genérico de `Temperature`.</span><span class="sxs-lookup"><span data-stu-id="227dd-108">For example, the following code defines a type named `TemperatureReporter` that is a constructed <xref:System.IObserver%601?displayProperty=nameWithType> implementation with a generic type argument of `Temperature`.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#8)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#8)]  
  
2.  <span data-ttu-id="227dd-109">Si el observador puede dejar de recibir notificaciones antes de realizar la llamada de proveedor su <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> implementación, definir una variable privada que contendrá el <xref:System.IDisposable> devuelto por el proveedor de implementación <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="227dd-109">If the observer can stop receiving notifications before the provider calls its <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> implementation, define a private variable that will hold the <xref:System.IDisposable> implementation returned by the provider's <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="227dd-110">También debe definir un método de suscripción que llame al proveedor <xref:System.IObservable%601.Subscribe%2A> (método) y almacena el valor devuelto <xref:System.IDisposable> objeto.</span><span class="sxs-lookup"><span data-stu-id="227dd-110">You should also define a subscription method that calls the provider's <xref:System.IObservable%601.Subscribe%2A> method and stores the returned <xref:System.IDisposable> object.</span></span> <span data-ttu-id="227dd-111">Por ejemplo, el código siguiente define una variable privada denominada `unsubscriber` y define un `Subscribe` método que llame al proveedor <xref:System.IObservable%601.Subscribe%2A> método y se asigna el objeto devuelto a la `unsubscriber` variable.</span><span class="sxs-lookup"><span data-stu-id="227dd-111">For example, the following code defines a private variable named `unsubscriber` and defines a `Subscribe` method that calls the provider's <xref:System.IObservable%601.Subscribe%2A> method and assigns the returned object to the `unsubscriber` variable.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#9)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#9)]  
  
3.  <span data-ttu-id="227dd-112">Defina un método que permite al observador dejar de recibir notificaciones antes de realizar la llamada de proveedor su <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> implementación, si esta característica es necesaria.</span><span class="sxs-lookup"><span data-stu-id="227dd-112">Define a method that enables the observer to stop receiving notifications before the provider calls its <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> implementation, if this feature is required.</span></span> <span data-ttu-id="227dd-113">En el ejemplo siguiente se define un `Unsubscribe` método.</span><span class="sxs-lookup"><span data-stu-id="227dd-113">The following example defines an `Unsubscribe` method.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#10)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#10)]  
  
4.  <span data-ttu-id="227dd-114">Proporcionar implementaciones de los tres métodos definidos por el <xref:System.IObserver%601> interfaz: <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>, y <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="227dd-114">Provide implementations of the three methods defined by the <xref:System.IObserver%601> interface: <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>, and <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="227dd-115">Según el proveedor y las necesidades de la aplicación, el <xref:System.IObserver%601.OnError%2A> y <xref:System.IObserver%601.OnCompleted%2A> métodos pueden ser implementaciones de código auxiliar.</span><span class="sxs-lookup"><span data-stu-id="227dd-115">Depending on the provider and the needs of the application, the <xref:System.IObserver%601.OnError%2A> and <xref:System.IObserver%601.OnCompleted%2A> methods can be stub implementations.</span></span> <span data-ttu-id="227dd-116">Tenga en cuenta que la <xref:System.IObserver%601.OnError%2A> método no debería administrar el pasado <xref:System.Exception> objeto como una excepción y la <xref:System.IObserver%601.OnCompleted%2A> método es gratuito llamar al proveedor <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementación.</span><span class="sxs-lookup"><span data-stu-id="227dd-116">Note that the <xref:System.IObserver%601.OnError%2A> method should not handle the passed <xref:System.Exception> object as an exception, and the <xref:System.IObserver%601.OnCompleted%2A> method is free to call the provider's <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="227dd-117">El siguiente ejemplo se muestra la <xref:System.IObserver%601> implementación de la `TemperatureReporter` clase.</span><span class="sxs-lookup"><span data-stu-id="227dd-117">The following example shows the <xref:System.IObserver%601> implementation of the `TemperatureReporter` class.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#11)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#11)]  
  
## <a name="example"></a><span data-ttu-id="227dd-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="227dd-118">Example</span></span>  
 <span data-ttu-id="227dd-119">El ejemplo siguiente contiene el código fuente completo para la `TemperatureReporter` (clase), que proporciona el <xref:System.IObserver%601> implementación para una aplicación de supervisión de temperatura.</span><span class="sxs-lookup"><span data-stu-id="227dd-119">The following example contains the complete source code for the `TemperatureReporter` class, which provides the <xref:System.IObserver%601> implementation for a temperature monitoring application.</span></span>  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#12)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="227dd-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="227dd-120">See Also</span></span>  
 <xref:System.IObserver%601>  
 [<span data-ttu-id="227dd-121">Modelo de diseño de observador</span><span class="sxs-lookup"><span data-stu-id="227dd-121">Observer Design Pattern</span></span>](../../../docs/standard/events/observer-design-pattern.md)  
 [<span data-ttu-id="227dd-122">Implementar un proveedor</span><span class="sxs-lookup"><span data-stu-id="227dd-122">How to: Implement a Provider</span></span>](../../../docs/standard/events/how-to-implement-a-provider.md)  
 [<span data-ttu-id="227dd-123">Procedimientos recomendados para modelos de diseño de observador</span><span class="sxs-lookup"><span data-stu-id="227dd-123">Observer Design Pattern Best Practices</span></span>](../../../docs/standard/events/observer-design-pattern-best-practices.md)
