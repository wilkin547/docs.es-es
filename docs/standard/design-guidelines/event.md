---
title: Diseño de eventos
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- pre-events
- events [.NET Framework], design guidelines
- member design guidelines, events
- event handlers [.NET Framework], event design guidelines
- post-events
- signatures, event handling
ms.assetid: 67b3c6e2-6a8f-480d-a78f-ebeeaca1b95a
author: KrzysztofCwalina
ms.openlocfilehash: 530c68ea5342263acd07f8dc8a8c8ce889652503
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54632028"
---
# <a name="event-design"></a>Diseño de eventos
Los eventos son la forma más frecuente de las devoluciones de llamada (construcciones que permiten el marco de trabajo llamar a código de usuario). Otros mecanismos de devolución de llamada incluyen a miembros tomar basado en la interfaz de complementos, los miembros virtuales y los delegados. Datos de estudios de uso indican que la mayoría de los desarrolladores son más cómodos si usan los eventos que usan otros mecanismos de devolución de llamada. Los eventos se integran perfectamente con Visual Studio y muchos lenguajes.  
  
 Es importante tener en cuenta que hay dos grupos de eventos: eventos provocados antes de que un estado de los cambios del sistema, denominados eventos previos y los eventos generados después de un estado cambie, denominan eventos posteriores. Un ejemplo de un evento previo sería `Form.Closing`, que se genera antes de que se cierra un formulario. Un ejemplo de un evento posterior a la sería `Form.Closed`, que se desencadena cuando se cierra un formulario.  
  
 **✓ DO** se usa el término "generar" para los eventos en lugar de "activar" o "activar".  
  
 **✓ DO** use <xref:System.EventHandler%601?displayProperty=nameWithType> en lugar de crear manualmente nuevos delegados que se usará como controladores de eventos.  
  
 **✓ CONSIDER** con una subclase de <xref:System.EventArgs> como el argumento de evento, a menos que esté totalmente seguro nunca tendrá que realizar ningún dato para el método de control de eventos el evento en cuyo caso puede utilizar la `EventArgs` escribir directamente.  
  
 Si envía una API mediante `EventArgs` directamente, nunca podrá agregar los datos se realice con el evento sin interrumpir la compatibilidad. Si usa una subclase, incluso si inicialmente completamente vacía, podrá agregar propiedades a la subclase cuando sea necesario.  
  
 **✓ DO** utilizar un método virtual protegido para provocar cada evento. Esto solo es aplicable a los eventos no estáticos en clases no selladas, no a las estructuras, clases selladas o eventos estáticos.  
  
 El propósito del método es proporcionar una forma de una clase derivada para controlar el evento mediante una invalidación. Reemplazar es una manera más flexible, rápida y más natural para controlar los eventos de la clase base en clases derivadas. Por convención, el nombre del método debe empezar por "On" y seguir con el nombre del evento.  
  
 La clase derivada puede elegir no llamar a la implementación base del método en su reemplazo. Estar preparadas para ello, no incluya ningún procesamiento en el método que se requiere para la clase base para que funcione correctamente.  
  
 **✓ DO** tomar un parámetro para el método protegido que genera un evento.  
  
 El parámetro debe denominarse `e` y debe escribirse como la clase de argumento de evento.  
  
 **X DO NOT** pasa null como el remitente cuando cuando se genera un evento no estático.  
  
 **✓ DO** pasa null como el remitente al generar un evento estático.  
  
 **X DO NOT** pasa null como parámetro de datos del evento al generar un evento.  
  
 Debería pasar `EventArgs.Empty` si no desea pasar ningún dato para el método de control de eventos. Los desarrolladores esperan este parámetro no sea null.  
  
 **✓ CONSIDER** generar eventos que se puede cancelar el usuario final. Esto solo se aplica a los eventos anteriores.  
  
 Use <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> o su subclase como el argumento de evento para permitir que el usuario final cancelar los eventos.  
  
### <a name="custom-event-handler-design"></a>Diseño de controlador de eventos personalizados  
 Hay casos en los que `EventHandler<T>` no se puede usar, por ejemplo, cuando el marco de trabajo necesita para trabajar con versiones anteriores de CLR, que no eran compatibles con los genéricos. En tales casos, es posible que necesita diseñar y desarrollar a un delegado de controlador de eventos personalizado.  
  
 **✓ DO** utilizar un tipo de valor devuelto de void para controladores de eventos.  
  
 Un controlador de eventos puede invocar varios métodos, posiblemente en varios objetos de control de eventos. Si los métodos de control de eventos se pueden devolver un valor, habrá varios valores devueltos para cada invocación del evento.  
  
 **✓ DO** usar `object` como el tipo del primer parámetro del controlador de eventos y llámelo `sender`.  
  
 **✓ DO** usar <xref:System.EventArgs?displayProperty=nameWithType> o su subclase como el tipo del segundo parámetro del controlador de eventos y llámelo `e`.  
  
 **X DO NOT** tiene más de dos parámetros en controladores de eventos.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md)
- [Instrucciones de diseño de .NET Framework](../../../docs/standard/design-guidelines/index.md)
