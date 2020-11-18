---
title: Diseño de eventos
ms.date: 10/22/2008
helpviewer_keywords:
- pre-events
- events [.NET Framework], design guidelines
- member design guidelines, events
- event handlers [.NET Framework], event design guidelines
- post-events
- signatures, event handling
ms.assetid: 67b3c6e2-6a8f-480d-a78f-ebeeaca1b95a
ms.openlocfilehash: eee4b1a9e72c167b9b1e48a73dbb3f0528744bdc
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821338"
---
# <a name="event-design"></a>Diseño de eventos
Los eventos son la forma de devoluciones de llamada que se usa con más frecuencia (construcciones que permiten al marco de trabajo llamar a código de usuario). Otros mecanismos de devolución de llamada incluyen miembros que toman delegados, miembros virtuales y complementos basados en interfaz. Los datos de los estudios de facilidad de uso indican que la mayoría de los desarrolladores se sienten más cómodos con los eventos que usan los otros mecanismos de devolución de llamada. Los eventos se integran perfectamente con Visual Studio y muchos lenguajes.

 Es importante tener en cuenta que hay dos grupos de eventos: los eventos que se generan antes de que cambie un estado del sistema, denominados eventos previos, y eventos generados después de un cambio de estado, denominados eventos posteriores. Un ejemplo de evento anterior sería `Form.Closing` , que se desencadena antes de que se cierre un formulario. Un ejemplo de evento posterior sería `Form.Closed` , que se genera después de cerrar un formulario.

 ✔️ usar el término "raise" para los eventos en lugar de "Fire" o "Trigger".

 ✔️ usar en <xref:System.EventHandler%601?displayProperty=nameWithType> lugar de crear manualmente nuevos delegados que se usarán como controladores de eventos.

 ✔️ considere la posibilidad de usar una subclase de <xref:System.EventArgs> como argumento de evento, a menos que esté absolutamente seguro de que el evento nunca tendrá que llevar ningún dato al método de control de eventos, en cuyo caso puede utilizar el `EventArgs` tipo directamente.

 Si envía una API `EventArgs` directamente, nunca podrá agregar ningún dato que se lleve a cabo con el evento sin interrumpir la compatibilidad. Si utiliza una subclase, incluso si inicialmente está completamente vacía, podrá agregar propiedades a la subclase cuando sea necesario.

 ✔️ usar un método virtual protegido para generar cada evento. Esto solo se aplica a eventos no estáticos en clases no selladas, no en Structs, clases selladas ni eventos estáticos.

 El propósito del método es proporcionar una manera para que una clase derivada controle el evento mediante una invalidación. Reemplazar es una forma más flexible, más rápida y más natural de controlar eventos de clase base en clases derivadas. Por Convención, el nombre del método debe empezar por "ON" y debe ir seguido del nombre del evento.

 La clase derivada puede elegir no llamar a la implementación base del método en su invalidación. Para ello, no incluya ningún procesamiento en el método necesario para que la clase base funcione correctamente.

 ✔️ realizar un parámetro al método protegido que genera un evento.

 El parámetro debe tener el nombre `e` y debe escribirse como la clase de argumento de evento.

 ❌ NO pase NULL como remitente al generar un evento no estático.

 ✔️ pasar null como remitente al generar un evento estático.

 ❌ NO pase NULL como parámetro de datos de evento al generar un evento.

 Debe pasar `EventArgs.Empty` si no desea pasar datos al método de control de eventos. Los desarrolladores esperan que este parámetro no sea NULL.

 ✔️ considere la posibilidad de generar eventos que el usuario final pueda cancelar. Esto solo se aplica a eventos previos.

 Use <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> o su subclase como argumento de evento para permitir que el usuario final cancele los eventos.

### <a name="custom-event-handler-design"></a>Diseño de controladores de eventos personalizados
 Hay casos en los que `EventHandler<T>` no se puede usar, como cuando el marco de trabajo necesita trabajar con versiones anteriores de CLR, que no admiten genéricos. En tales casos, es posible que tenga que diseñar y desarrollar un delegado de controlador de eventos personalizado.

 ✔️ usar un tipo de valor devuelto de void para los controladores de eventos.

 Un controlador de eventos puede invocar varios métodos de control de eventos, posiblemente en varios objetos. Si los métodos de control de eventos podían devolver un valor, hubiera varios valores devueltos por cada invocación de evento.

 ✔️ usar `object` como el tipo del primer parámetro del controlador de eventos y llamarlo `sender` .

 ✔️ usar <xref:System.EventArgs?displayProperty=nameWithType> o su subclase como el tipo del segundo parámetro del controlador de eventos y llamarlo `e` .

 ❌ NO tener más de dos parámetros en los controladores de eventos.

 *Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Consulte también

- [Instrucciones para el diseño de miembros](member.md)
- [Directrices de diseño de marco](index.md)
