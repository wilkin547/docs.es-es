---
title: "Cómo: Implementar un proveedor"
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
- observer design pattern [.NET Framework], implementing providers
- providers [.NET Framework], in observer design pattern
- observables [.NET Framework], in observer design pattern
ms.assetid: 790b5d8b-d546-40a6-beeb-151b574e5ee5
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b9d8f96de8cb3d13568e755f1d5e885e0474d891
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-a-provider"></a>Cómo: Implementar un proveedor
El modelo de diseño de observador requiere una división entre un proveedor, que supervisa los datos y envía notificaciones, y uno o varios observadores, que reciben notificaciones (devoluciones de llamada) del proveedor. Este tema describe cómo crear un proveedor. Un tema relacionado, [Cómo: implementar un observador](../../../docs/standard/events/how-to-implement-an-observer.md), se describe cómo crear un observador.  
  
### <a name="to-create-a-provider"></a>Para crear un proveedor  
  
1.  Definir los datos que el proveedor se encarga de enviar a los observadores. Aunque el proveedor y los datos que envía a los observadores pueden ser un tipo único, por lo general se representan mediante distintos tipos. Por ejemplo, en una aplicación de supervisión de temperatura del `Temperature` estructura define los datos que el proveedor (lo que se representa mediante la `TemperatureMonitor` clase definida en el paso siguiente) supervisa y a los observadores suscribirse.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/data.cs#1)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/data.vb#1)]  
  
2.  Definir el proveedor de datos, que es un tipo que implementa el <xref:System.IObservable%601?displayProperty=nameWithType> interfaz. Argumento de tipo genérico del proveedor es el tipo que el proveedor envía a los observadores. En el ejemplo siguiente se define un `TemperatureMonitor` (clase), que es un construido <xref:System.IObservable%601?displayProperty=nameWithType> implementación con un argumento de tipo genérico de `Temperature`.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#2)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#2)]  
  
3.  Determinar cómo el proveedor de almacenar las referencias a los observadores para que cada observador puede recibir una notificación cuando corresponda. Normalmente, un objeto de colección como un tipo genérico <xref:System.Collections.Generic.List%601> objeto se usa para este propósito. En el ejemplo siguiente se define una privada <xref:System.Collections.Generic.List%601> objeto cuyas instancias se crean en el `TemperatureMonitor` constructor de clase.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#3)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#3)]  
  
4.  Definir una <xref:System.IDisposable> implementación que el proveedor puede devolver a los suscriptores para que puede dejar de recibir notificaciones en cualquier momento. En el ejemplo siguiente se define una anidada `Unsubscriber` clase que se pasa una referencia a la colección de los suscriptores y al suscriptor cuando se crea una instancia de la clase. Este código permite que el suscriptor llamar al objeto <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementación a quitarse de la colección de suscriptores.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#4)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#4)]  
  
5.  Implemente el método <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType>. El método se pasa una referencia a la <xref:System.IObserver%601?displayProperty=nameWithType> de interfaz y se deben almacenar en el objeto que se ha diseñado para ese propósito en el paso 3. El método, a continuación, debe devolver el <xref:System.IDisposable> implementación desarrollado en el paso 4. En el ejemplo siguiente se muestra la implementación de la <xref:System.IObservable%601.Subscribe%2A> método en la `TemperatureMonitor` clase.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#5)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#5)]  
  
6.  Notificar a los observadores según corresponda mediante una llamada a sus <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>, y <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> las implementaciones. En algunos casos, un proveedor no puede llamar a la <xref:System.IObserver%601.OnError%2A> método cuando se produce un error. Por ejemplo, la siguiente `GetTemperature` método simula un monitor que lee los datos de temperatura cada cinco segundos y notifica a los observadores si la temperatura ha cambiado por al menos.1 grado desde la lectura anterior. Si el dispositivo no informa de una temperatura (es decir, si su valor es null), el proveedor notifica a observadores a que la transmisión está completa. Tenga en cuenta que, además de llamar a cada observador <xref:System.IObserver%601.OnCompleted%2A> método, el `GetTemperature` método borra el <xref:System.Collections.Generic.List%601> colección. En este caso, el proveedor no hace que llamadas posteriores a la <xref:System.IObserver%601.OnError%2A> método de sus observadores.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#6)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#6)]  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente contiene el código fuente completo para definir un <xref:System.IObservable%601> implementación para una aplicación de supervisión de temperatura. Incluye el `Temperature` estructura, que es los datos enviados a los observadores, y el `TemperatureMonitor` (clase), que es el <xref:System.IObservable%601> implementación.  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#7)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#7)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IObservable%601>  
 [Modelo de diseño de observador](../../../docs/standard/events/observer-design-pattern.md)  
 [Implementar un observador](../../../docs/standard/events/how-to-implement-an-observer.md)  
 [Procedimientos recomendados para modelos de diseño de observador](../../../docs/standard/events/observer-design-pattern-best-practices.md)
