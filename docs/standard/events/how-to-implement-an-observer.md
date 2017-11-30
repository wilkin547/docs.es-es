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
# <a name="how-to-implement-an-observer"></a>Cómo: Implementar un observador
El modelo de diseño de observador requiere una división entre un observador, que se registra para las notificaciones, y un proveedor, que supervisa los datos y envía notificaciones a los observadores de uno o más. En este tema se describe cómo crear un observador. Un tema relacionado, [Cómo: implementar un proveedor de](../../../docs/standard/events/how-to-implement-a-provider.md), se describe cómo crear un proveedor.  
  
### <a name="to-create-an-observer"></a>Para crear un observador  
  
1.  Definir el observador, que es un tipo que implementa el <xref:System.IObserver%601?displayProperty=nameWithType> interfaz. Por ejemplo, el código siguiente define un tipo denominado `TemperatureReporter` que es un construido <xref:System.IObserver%601?displayProperty=nameWithType> implementación con un argumento de tipo genérico de `Temperature`.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#8)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#8)]  
  
2.  Si el observador puede dejar de recibir notificaciones antes de realizar la llamada de proveedor su <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> implementación, definir una variable privada que contendrá el <xref:System.IDisposable> devuelto por el proveedor de implementación <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> método. También debe definir un método de suscripción que llame al proveedor <xref:System.IObservable%601.Subscribe%2A> (método) y almacena el valor devuelto <xref:System.IDisposable> objeto. Por ejemplo, el código siguiente define una variable privada denominada `unsubscriber` y define un `Subscribe` método que llame al proveedor <xref:System.IObservable%601.Subscribe%2A> método y se asigna el objeto devuelto a la `unsubscriber` variable.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#9)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#9)]  
  
3.  Defina un método que permite al observador dejar de recibir notificaciones antes de realizar la llamada de proveedor su <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> implementación, si esta característica es necesaria. En el ejemplo siguiente se define un `Unsubscribe` método.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#10)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#10)]  
  
4.  Proporcionar implementaciones de los tres métodos definidos por el <xref:System.IObserver%601> interfaz: <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>, y <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>. Según el proveedor y las necesidades de la aplicación, el <xref:System.IObserver%601.OnError%2A> y <xref:System.IObserver%601.OnCompleted%2A> métodos pueden ser implementaciones de código auxiliar. Tenga en cuenta que la <xref:System.IObserver%601.OnError%2A> método no debería administrar el pasado <xref:System.Exception> objeto como una excepción y la <xref:System.IObserver%601.OnCompleted%2A> método es gratuito llamar al proveedor <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementación. El siguiente ejemplo se muestra la <xref:System.IObserver%601> implementación de la `TemperatureReporter` clase.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#11)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#11)]  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente contiene el código fuente completo para la `TemperatureReporter` (clase), que proporciona el <xref:System.IObserver%601> implementación para una aplicación de supervisión de temperatura.  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#12)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#12)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IObserver%601>  
 [Modelo de diseño de observador](../../../docs/standard/events/observer-design-pattern.md)  
 [Implementar un proveedor](../../../docs/standard/events/how-to-implement-a-provider.md)  
 [Procedimientos recomendados para modelos de diseño de observador](../../../docs/standard/events/observer-design-pattern-best-practices.md)
