---
title: Diseño de eventos
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- pre-events
- events [.NET Framework], design guidelines
- member design guidelines, events
- event handlers [.NET Framework], event design guidelines
- post-events
- signatures, event handling
ms.assetid: 67b3c6e2-6a8f-480d-a78f-ebeeaca1b95a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 48d1ad0f02ae34675c0a910d7651d718c060db60
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33575399"
---
# <a name="event-design"></a>Diseño de eventos
Los eventos son la forma más utilizada de las devoluciones de llamada (construcciones que permiten el marco de trabajo llamar a código de usuario). Otros mecanismos de devolución de llamada deben incluir a miembros teniendo delegados, los miembros virtuales y usar complementos basado en la interfaz. Datos de estudios de uso indican que la mayoría de los desarrolladores más cómodo mediante eventos que usen otros mecanismos de devolución de llamada. Eventos se integran perfectamente con Visual Studio y muchos idiomas.  
  
 Es importante tener en cuenta que hay dos grupos de eventos: eventos generados antes de un estado de los cambios del sistema, denominados eventos anteriores y eventos que se desencadena cuando se cambia un estado, denominan eventos posteriores a la. Un ejemplo de un evento previo sería `Form.Closing`, que se produce antes de que se cierra un formulario. Un ejemplo de un evento posterior a la sería `Form.Closed`, que se desencadena cuando se cierra un formulario.  
  
 **✓ DO** se usa el término "generar" para los eventos en lugar de "activar" o "activar".  
  
 **✓ DO** use <xref:System.EventHandler%601?displayProperty=nameWithType> en lugar de crear manualmente nuevos delegados que se usará como controladores de eventos.  
  
 **✓ CONSIDER** con una subclase de <xref:System.EventArgs> como el argumento de evento, a menos que esté totalmente seguro nunca tendrá que realizar ningún dato para el método de control de eventos el evento en cuyo caso puede utilizar la `EventArgs` escribir directamente.  
  
 Tanto si incluye una API mediante `EventArgs` directamente, nunca podrá agregar todos los datos se realiza con el evento sin interrumpir la compatibilidad. Si usa una subclase, incluso si inicialmente completamente vacías, podrá agregar propiedades a la subclase cuando sea necesario.  
  
 **✓ DO** utilizar un método virtual protegido para provocar cada evento. Esto solo es aplicable a los eventos no estáticos en clases no selladas, no a las estructuras, clases selladas o eventos estáticos.  
  
 El propósito del método es proporcionar una manera para que una clase derivada para controlar el evento mediante una invalidación. Reemplazar el método es una manera más flexible, más rápida y más natural para controlar los eventos de la clase base en clases derivadas. Por convención, el nombre del método debe comenzar con "On" y seguir con el nombre del evento.  
  
 La clase derivada puede elegir no llamar a la implementación base del método en su reemplazo. Prepárese para esto, no incluya ningún procesamiento en el método que se requiere para la clase base para que funcione correctamente.  
  
 **✓ DO** tomar un parámetro para el método protegido que genera un evento.  
  
 El parámetro se debe denominar `e` y debe escribirse como la clase de argumento de evento.  
  
 **X DO NOT** pasa null como el remitente cuando cuando se genera un evento no estático.  
  
 **✓ DO** pasa null como el remitente al generar un evento estático.  
  
 **X DO NOT** pasa null como parámetro de datos del evento al generar un evento.  
  
 Debería pasar `EventArgs.Empty` si no desea pasar ningún dato para el método de control de eventos. Los desarrolladores esperan este parámetro para que no sea null.  
  
 **✓ CONSIDER** generar eventos que se puede cancelar el usuario final. Esto solo se aplica a los eventos anteriores.  
  
 Use <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> o su subclase como el argumento de evento para permitir que el usuario final pueda cancelar eventos.  
  
### <a name="custom-event-handler-design"></a>Diseño de controlador de eventos personalizados  
 Hay casos en los que `EventHandler<T>` no se puede usar, por ejemplo, cuando el marco de trabajo necesita trabajar con versiones anteriores de CLR, el cual no era compatible con genéricos. En tales casos, deberá diseñar y desarrollar a un delegado de controlador de eventos personalizado.  
  
 **✓ DO** utilizar un tipo de valor devuelto de void para controladores de eventos.  
  
 Un controlador de eventos puede invocar varios métodos, posiblemente en varios objetos de control de eventos. Si se permiten métodos de control de eventos para devolver un valor, habrá varios valores devueltos para cada invocación del evento.  
  
 **✓ DO** usar `object` como el tipo del primer parámetro del controlador de eventos y llámelo `sender`.  
  
 **✓ DO** usar <xref:System.EventArgs?displayProperty=nameWithType> o su subclase como el tipo del segundo parámetro del controlador de eventos y llámelo `e`.  
  
 **X DO NOT** tiene más de dos parámetros en controladores de eventos.  
  
 *Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también  
 [Instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md)  
 [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
