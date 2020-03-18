---
title: Procedimientos recomendados para modelos de diseño de observador
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- observer design pattern [.NET Framework], best practices
- best practices [.NET Framework], observer design pattern
ms.assetid: c834760f-ddd4-417f-abb7-a059679d5b8c
ms.openlocfilehash: 2da29e0baf429142707d0ddd39b1a11c13a17a90
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73141537"
---
# <a name="observer-design-pattern-best-practices"></a>Procedimientos recomendados para modelos de diseño de observador
En .NET Framework, el patrón de diseño de observador se implementa como un conjunto de interfaces. La interfaz <xref:System.IObservable%601?displayProperty=nameWithType> representa al proveedor de datos, que también es responsable de proporcionar una implementación <xref:System.IDisposable> que permite a los observadores cancelar la suscripción a las notificaciones. La interfaz <xref:System.IObserver%601?displayProperty=nameWithType> representa al observador. En este tema se describen los procedimientos recomendados que los desarrolladores deben seguir al implementar el patrón de diseño de observador con estas interfaces.  
  
## <a name="threading"></a>Subprocesos  
 Normalmente, para implementar el método <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType>, un proveedor agrega un observador determinado a una lista de suscriptores que se representa mediante un objeto de colección; por su parte, para implementar el método <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>, el proveedor quita un observador determinado de la lista de suscriptores. Un observador puede llamar a estos métodos en cualquier momento. Además, dado que el contrato de proveedor/observador no especifica quién es el responsable de cancelar la suscripción después del método de devolución de llamada <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>, el proveedor y el observador pueden intentar quitar el mismo miembro de la lista. Debido a esta posibilidad, ambos métodos <xref:System.IObservable%601.Subscribe%2A> y <xref:System.IDisposable.Dispose%2A> deben ser seguros para subprocesos. Normalmente, esto implica el uso de una [colección simultánea](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md) o un bloqueo. Las implementaciones que no son seguras para subprocesos deben documentar explícitamente que no lo son.  
  
 Las posibles garantías adicionales deben especificarse en un nivel por encima del contrato de proveedor/observador. Los implementadores deben dejar claro que imponen requisitos adicionales para evitar confusiones al usuario sobre el contrato de observador.  
  
## <a name="handling-exceptions"></a>Controlar las excepciones  
 Debido al acoplamiento flexible entre un proveedor de datos y un observador, las excepciones en el patrón de diseño de observador tienen un carácter informativo. Esto afecta a cómo los proveedores y observadores controlan las excepciones en el patrón de diseño de observador.  
  
### <a name="the-provider----calling-the-onerror-method"></a>El proveedor: llamada al método OnError  
 El propósito del método <xref:System.IObserver%601.OnError%2A> es servir de mensaje informativo para el observador, de modo parecido al método <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>. Sin embargo, el método <xref:System.IObserver%601.OnNext%2A> está diseñado para proporcionarle a un observador información actual o actualizada, mientras que el método <xref:System.IObserver%601.OnError%2A> está diseñado para indicar que el proveedor no puede proporcionar datos válidos.  
  
 El proveedor debe seguir estas recomendaciones a la hora de controlar las excepciones y llamar al método <xref:System.IObserver%601.OnError%2A>:  
  
- El proveedor debe controlar sus propias excepciones si tiene requisitos específicos.  
  
- El proveedor no debe esperar ni exigir que los observadores controlen las excepciones en ningún modo en particular.  
  
- El proveedor debe llamar al método <xref:System.IObserver%601.OnError%2A> cuando controla una excepción que pone en peligro su capacidad para proporcionar actualizaciones. La información sobre este tipo de excepciones se puede pasar al observador. En otros casos, no es necesario informar a los observadores de una excepción.  
  
 Una vez que el proveedor llama al método <xref:System.IObserver%601.OnError%2A> o <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>, no debe haber más notificaciones y el proveedor puede cancelar la suscripción de sus observadores. No obstante, también los observadores pueden cancelar ellos mismos su suscripción en cualquier momento, incluso antes y después de recibir una notificación <xref:System.IObserver%601.OnError%2A> o <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>. El patrón de diseño de observador no indica si el proveedor o el observador son responsables de cancelar la suscripción; por lo tanto, es posible que ambos traten de cancelar la suscripción. Normalmente, cuando los observadores cancelan su suscripción, se quitan de una colección de los suscriptores. En una aplicación de un único subproceso, la implementación de <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> debe asegurarse de la validez de una referencia de objeto y de que el objeto es miembro de la colección de suscriptores antes de intentar quitarlo. En una aplicación multiproceso, debe utilizarse un objeto de colección seguro para subprocesos, por ejemplo, un objeto <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType>.  
  
### <a name="the-observer----implementing-the-onerror-method"></a>El observador: implementación del método OnError  
 Cuando un observador recibe una notificación de error de un proveedor, debe considerar solo el valor informativo de la excepción sin que sea necesario realizar ninguna acción especial.  
  
 El observador debe seguir estas recomendaciones al responder a una llamada de método <xref:System.IObserver%601.OnError%2A> de un proveedor:  
  
- El observador no debe generar excepciones desde sus implementaciones de interfaz, como <xref:System.IObserver%601.OnNext%2A> o <xref:System.IObserver%601.OnError%2A>. No obstante, si el observador genera excepciones, no debe esperar que se controlen.  
  
- Para conservar la pila de llamadas, un observador que desee producir un objeto <xref:System.Exception> pasado a su método <xref:System.IObserver%601.OnError%2A>, debe encapsular la excepción antes generarla. Para este propósito, debe usarse un objeto de excepción estándar.  
  
## <a name="additional-best-practices"></a>Recomendaciones adicionales  
 Intentar anular el registro en el método <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> puede producir una referencia nula. Por lo tanto, se recomienda evitar esta práctica.  
  
 Aunque es posible adjuntar un observador a varios proveedores, el patrón recomendado consiste en adjuntar una instancia de <xref:System.IObserver%601> a una única instancia de <xref:System.IObservable%601>.  
  
## <a name="see-also"></a>Vea también

- [Modelo de diseño de observador](../../../docs/standard/events/observer-design-pattern.md)
- [Implementar un observador](../../../docs/standard/events/how-to-implement-an-observer.md)
- [Implementar un proveedor](../../../docs/standard/events/how-to-implement-a-provider.md)
