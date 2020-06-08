---
title: 'Cómo: Implementar un observador'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- observers [.NET Framework], observer design pattern
- observer design pattern [.NET Framework], implementing observers
ms.assetid: 8ecfa9f5-b500-473d-bcf0-5652ffb1e53d
ms.openlocfilehash: 969b83bcd11159509a2cc1ed843836679ffd1705
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289725"
---
# <a name="how-to-implement-an-observer"></a><span data-ttu-id="17eb9-102">Cómo: Implementar un observador</span><span class="sxs-lookup"><span data-stu-id="17eb9-102">How to: Implement an Observer</span></span>
<span data-ttu-id="17eb9-103">El modelo de diseño de observador requiere una división entre un observador, que registra notificaciones, y un proveedor, que controla los datos y envía notificaciones a uno o varios observadores.</span><span class="sxs-lookup"><span data-stu-id="17eb9-103">The observer design pattern requires a division between an observer, which registers for notifications, and a provider, which monitors data and sends notifications to one or more observers.</span></span> <span data-ttu-id="17eb9-104">En este tema se describe cómo crear un observador.</span><span class="sxs-lookup"><span data-stu-id="17eb9-104">This topic discusses how to create an observer.</span></span> <span data-ttu-id="17eb9-105">En un tema relacionado, [Cómo: Implementar un proveedor](how-to-implement-a-provider.md), se describe cómo crear un proveedor.</span><span class="sxs-lookup"><span data-stu-id="17eb9-105">A related topic, [How to: Implement a Provider](how-to-implement-a-provider.md), discusses how to create an provider.</span></span>  
  
### <a name="to-create-an-observer"></a><span data-ttu-id="17eb9-106">Para crear un observador</span><span class="sxs-lookup"><span data-stu-id="17eb9-106">To create an observer</span></span>  
  
1. <span data-ttu-id="17eb9-107">Defina el observador, que es un tipo que implementa la interfaz <xref:System.IObserver%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="17eb9-107">Define the observer, which is a type that implements the <xref:System.IObserver%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="17eb9-108">Por ejemplo, el código siguiente define un tipo llamado `TemperatureReporter`, que es una implementación <xref:System.IObserver%601?displayProperty=nameWithType> construida con un argumento de tipo genérico de `Temperature`.</span><span class="sxs-lookup"><span data-stu-id="17eb9-108">For example, the following code defines a type named `TemperatureReporter` that is a constructed <xref:System.IObserver%601?displayProperty=nameWithType> implementation with a generic type argument of `Temperature`.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#8)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#8)]  
  
2. <span data-ttu-id="17eb9-109">Si el observador puede dejar de recibir notificaciones antes de que el proveedor llame a su implementación <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>, defina una variable privada que contenga la implementación <xref:System.IDisposable> devuelta por el método <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> del proveedor.</span><span class="sxs-lookup"><span data-stu-id="17eb9-109">If the observer can stop receiving notifications before the provider calls its <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> implementation, define a private variable that will hold the <xref:System.IDisposable> implementation returned by the provider's <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="17eb9-110">También debe definir un método de suscripción que llame al método <xref:System.IObservable%601.Subscribe%2A> del proveedor y almacene el objeto <xref:System.IDisposable> devuelto.</span><span class="sxs-lookup"><span data-stu-id="17eb9-110">You should also define a subscription method that calls the provider's <xref:System.IObservable%601.Subscribe%2A> method and stores the returned <xref:System.IDisposable> object.</span></span> <span data-ttu-id="17eb9-111">Por ejemplo, el código siguiente define una variable privada denominada `unsubscriber` y define un método `Subscribe` que llama al método <xref:System.IObservable%601.Subscribe%2A> del proveedor y asigna el objeto devuelto a la variable `unsubscriber`.</span><span class="sxs-lookup"><span data-stu-id="17eb9-111">For example, the following code defines a private variable named `unsubscriber` and defines a `Subscribe` method that calls the provider's <xref:System.IObservable%601.Subscribe%2A> method and assigns the returned object to the `unsubscriber` variable.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#9)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#9)]  
  
3. <span data-ttu-id="17eb9-112">Defina un método que permita al observador dejar de recibir notificaciones antes de que el proveedor llame a su implementación <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>, en caso de que esta característica sea necesaria.</span><span class="sxs-lookup"><span data-stu-id="17eb9-112">Define a method that enables the observer to stop receiving notifications before the provider calls its <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> implementation, if this feature is required.</span></span> <span data-ttu-id="17eb9-113">En el ejemplo siguiente, se define un método `Unsubscribe`.</span><span class="sxs-lookup"><span data-stu-id="17eb9-113">The following example defines an `Unsubscribe` method.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#10)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#10)]  
  
4. <span data-ttu-id="17eb9-114">Proporcione implementaciones de los tres métodos definidos en la interfaz <xref:System.IObserver%601>: <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType> y <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="17eb9-114">Provide implementations of the three methods defined by the <xref:System.IObserver%601> interface: <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>, and <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="17eb9-115">En función del proveedor y de las necesidades de la aplicación, los métodos <xref:System.IObserver%601.OnError%2A> y <xref:System.IObserver%601.OnCompleted%2A> pueden ser implementaciones de código auxiliar.</span><span class="sxs-lookup"><span data-stu-id="17eb9-115">Depending on the provider and the needs of the application, the <xref:System.IObserver%601.OnError%2A> and <xref:System.IObserver%601.OnCompleted%2A> methods can be stub implementations.</span></span> <span data-ttu-id="17eb9-116">Tenga en cuenta que el método <xref:System.IObserver%601.OnError%2A> no debe controlar el objeto <xref:System.Exception> pasado como una excepción y que el método <xref:System.IObserver%601.OnCompleted%2A> es libre de llamar a la implementación <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> del proveedor.</span><span class="sxs-lookup"><span data-stu-id="17eb9-116">Note that the <xref:System.IObserver%601.OnError%2A> method should not handle the passed <xref:System.Exception> object as an exception, and the <xref:System.IObserver%601.OnCompleted%2A> method is free to call the provider's <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="17eb9-117">El siguiente ejemplo muestra la implementación <xref:System.IObserver%601> de la clase `TemperatureReporter`.</span><span class="sxs-lookup"><span data-stu-id="17eb9-117">The following example shows the <xref:System.IObserver%601> implementation of the `TemperatureReporter` class.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#11)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#11)]  
  
## <a name="example"></a><span data-ttu-id="17eb9-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="17eb9-118">Example</span></span>  
 <span data-ttu-id="17eb9-119">El siguiente ejemplo contiene el código fuente completo para la clase `TemperatureReporter`, que ofrece la implementación <xref:System.IObserver%601> de una aplicación de supervisión de temperatura.</span><span class="sxs-lookup"><span data-stu-id="17eb9-119">The following example contains the complete source code for the `TemperatureReporter` class, which provides the <xref:System.IObserver%601> implementation for a temperature monitoring application.</span></span>  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#12)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="17eb9-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="17eb9-120">See also</span></span>

- <xref:System.IObserver%601>
- [<span data-ttu-id="17eb9-121">Modelo de diseño de observador</span><span class="sxs-lookup"><span data-stu-id="17eb9-121">Observer Design Pattern</span></span>](observer-design-pattern.md)
- [<span data-ttu-id="17eb9-122">Implementar un proveedor</span><span class="sxs-lookup"><span data-stu-id="17eb9-122">How to: Implement a Provider</span></span>](how-to-implement-a-provider.md)
- [<span data-ttu-id="17eb9-123">Procedimientos recomendados para modelos de diseño de observador</span><span class="sxs-lookup"><span data-stu-id="17eb9-123">Observer Design Pattern Best Practices</span></span>](observer-design-pattern-best-practices.md)
