---
title: "C&#243;mo: Implementar un observador | Microsoft Docs"
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
  - "observadores [.NET Framework], modelo de diseño de observador"
  - "modelo de diseño de observador [.NET Framework], implementar observadores"
ms.assetid: 8ecfa9f5-b500-473d-bcf0-5652ffb1e53d
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Implementar un observador
El modelo de diseño de observador necesita una división entre un observador, que efectúa el registro para las notificaciones, y un proveedor, que supervisa los datos y envía notificaciones a uno o más observadores.  En este tema se explica cómo crear un observador.  En un tema relacionado, [Cómo: Implementar un proveedor](../../../docs/standard/events/how-to-implement-a-provider.md), se explica cómo crear un proveedor.  
  
### Para crear un observador  
  
1.  Defina el observador, que es un tipo que implementa la interfaz <xref:System.IObserver%601?displayProperty=fullName>.  Por ejemplo, en el código siguiente se define un tipo denominado `TemperatureReporter` que es una implementación de <xref:System.IObserver%601?displayProperty=fullName> construida con un argumento de tipo genérico de `Temperature`.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#8)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#8)]  
  
2.  Si el observador puede dejar de recibir notificaciones antes de que el proveedor llame a su implementación de <xref:System.IObserver%601.OnCompleted%2A?displayProperty=fullName>, defina una variable privada que contendrá la implementación de <xref:System.IDisposable> devuelta por el método <xref:System.IObservable%601.Subscribe%2A?displayProperty=fullName> del proveedor.  También debe definir un método de suscripción que llame al método <xref:System.IObservable%601.Subscribe%2A> del proveedor y almacene el objeto <xref:System.IDisposable> devuelto.  Por ejemplo, en el código siguiente se define una variable privada denominada `unsubscriber` y un método `Subscribe` que llama al método <xref:System.IObservable%601.Subscribe%2A> del proveedor y asigna el objeto devuelto a la variable `unsubscriber`.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#9)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#9)]  
  
3.  Defina un método que permita al observador dejar de recibir notificaciones antes de que el proveedor llame a su implementación de <xref:System.IObserver%601.OnCompleted%2A?displayProperty=fullName>, si se necesita esta característica.  En el ejemplo siguiente se define un método `Unsubscribe`.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#10)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#10)]  
  
4.  Proporcione implementaciones de los tres métodos definidos por la interfaz <xref:System.IObserver%601>: <xref:System.IObserver%601.OnNext%2A?displayProperty=fullName>, <xref:System.IObserver%601.OnError%2A?displayProperty=fullName> y <xref:System.IObserver%601.OnCompleted%2A?displayProperty=fullName>.  Dependiendo del proveedor y los requisitos de la aplicación, los métodos <xref:System.IObserver%601.OnError%2A> y <xref:System.IObserver%601.OnCompleted%2A> pueden ser implementaciones de código auxiliar.  Tenga en cuenta que el método <xref:System.IObserver%601.OnError%2A> no debe controlar el objeto <xref:System.Exception> pasado como una excepción y que el método <xref:System.IObserver%601.OnCompleted%2A> puede llamar a la implementación de <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> del proveedor.  En el ejemplo siguiente se muestra la implementación de <xref:System.IObserver%601> de la clase `TemperatureReporter`.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#11)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#11)]  
  
## Ejemplo  
 El ejemplo siguiente contiene el código fuente completo de la clase `TemperatureReporter`, que proporciona la implementación de <xref:System.IObserver%601> para una aplicación de control de temperatura.  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#12)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#12)]  
  
## Vea también  
 <xref:System.IObserver%601>   
 [Modelo de diseño de observador](../../../docs/standard/events/observer-design-pattern.md)   
 [Cómo: Implementar un proveedor](../../../docs/standard/events/how-to-implement-a-provider.md)   
 [Procedimientos recomendados para modelos de diseño de observador](../../../docs/standard/events/observer-design-pattern-best-practices.md)