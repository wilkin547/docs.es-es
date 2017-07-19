---
title: "C&#243;mo: Implementar un proveedor | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "patrón de diseño de observador [.NET Framework], implementar proveedores"
  - "proveedores [.NET Framework], en patrón de diseño de observador"
  - "observables [.NET Framework], en patrón de diseño de observador"
ms.assetid: 790b5d8b-d546-40a6-beeb-151b574e5ee5
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Implementar un proveedor
El modelo de diseño de observador necesita una división entre un proveedor, que supervisa los datos y envía notificaciones, y uno o más observadores, que reciben notificaciones \(devoluciones de llamada\) del proveedor.  En este tema se explica cómo crear un proveedor.  En un tema relacionado, [Cómo: Implementar un observador](../../../docs/standard/events/how-to-implement-an-observer.md), se explica cómo crear un observador.  
  
### Para crear un proveedor  
  
1.  Defina los datos que el proveedor es responsable de enviar a los observadores.  Aunque el proveedor y los datos que envía a los observadores pueden ser de un tipo único, normalmente se representan mediante tipos diferentes.  Por ejemplo, en una aplicación de control de temperatura, la estructura `Temperature` define los datos que el proveedor \(que se representa mediante la clase `TemperatureMonitor` definida en el paso siguiente\) supervisa y a los que los observadores se suscriben.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/data.cs#1)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/data.vb#1)]  
  
2.  Defina el proveedor de datos, que es un tipo que implementa la interfaz <xref:System.IObservable%601?displayProperty=fullName>.  El argumento de tipo genérico del proveedor es el tipo que el proveedor envía a los observadores.  En el ejemplo siguiente se define una clase `TemperatureMonitor`, que es una implementación construida de <xref:System.IObservable%601?displayProperty=fullName> con un argumento de tipo genérico de `Temperature`.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#2)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#2)]  
  
3.  Determine cómo almacenará el proveedor las referencias a los observadores para poder notificar a cada observador cuando sea necesario.  Normalmente se usa para este fin un objeto de colección como un objeto genérico <xref:System.Collections.Generic.List%601>.  En el ejemplo siguiente se define un objeto <xref:System.Collections.Generic.List%601> privado del que se crea una instancia en el constructor de la clase `TemperatureMonitor`.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#3)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#3)]  
  
4.  Defina una implementación de <xref:System.IDisposable> que el proveedor puede devolver a los suscriptores para que puedan dejar de recibir notificaciones en cualquier momento.  En el ejemplo siguiente se define una clase `Unsubscriber` anidada a la que se pasa una referencia a la colección de los suscriptores y al suscriptor cuando se crea una instancia de la clase.  Este código permite al suscriptor llamar a la implementación de <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> del objeto para quitarse a sí mismo de la colección de suscriptores.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#4)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#4)]  
  
5.  Implemente el método <xref:System.IObservable%601.Subscribe%2A?displayProperty=fullName>.  Se pasa al método una referencia a la interfaz <xref:System.IObserver%601?displayProperty=fullName> y este método debe almacenarse en el objeto diseñado para ese fin en el paso 3.  A continuación, el método debe devolver la implementación de <xref:System.IDisposable> desarrollada en el paso 4.  En el ejemplo siguiente se muestra la implementación del método <xref:System.IObservable%601.Subscribe%2A> en la clase `TemperatureMonitor`.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#5)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#5)]  
  
6.  Notifique a los observadores según corresponda llamando a sus implementaciones de <xref:System.IObserver%601.OnNext%2A?displayProperty=fullName>, <xref:System.IObserver%601.OnError%2A?displayProperty=fullName> y <xref:System.IObserver%601.OnCompleted%2A?displayProperty=fullName>.  En algunos casos, un proveedor no puede llamar al método <xref:System.IObserver%601.OnError%2A> cuando se produce un error.  Por ejemplo, en el siguiente método `GetTemperature` se simula un monitor que lee datos de temperatura cada cinco segundos y notifica a los observadores si la temperatura ha cambiado menos 0,1 grado con respecto a la lectura anterior.  Si el dispositivo no indica ninguna temperatura \(es decir, si su valor es NULL\), el proveedor notifica a los observadores que la transmisión se ha completado.  Tenga en cuenta que, además de llamar al método <xref:System.IObserver%601.OnCompleted%2A> de cada observador, el método `GetTemperature` borra la colección <xref:System.Collections.Generic.List%601>.  En este caso, el proveedor no realiza ninguna llamada al método <xref:System.IObserver%601.OnError%2A> de sus observadores.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#6)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#6)]  
  
## Ejemplo  
 El ejemplo siguiente contiene el código fuente completo para definir una implementación de <xref:System.IObservable%601> para una aplicación de control de temperatura.  Incluye la estructura `Temperature`, que es los datos enviados a los observadores, y la clase `TemperatureMonitor`, que es la implementación de <xref:System.IObservable%601>.  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#7)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#7)]  
  
## Vea también  
 <xref:System.IObservable%601>   
 [Modelo de diseño de observador](../../../docs/standard/events/observer-design-pattern.md)   
 [Cómo: Implementar un observador](../../../docs/standard/events/how-to-implement-an-observer.md)   
 [Procedimientos recomendados para modelos de diseño de observador](../../../docs/standard/events/observer-design-pattern-best-practices.md)