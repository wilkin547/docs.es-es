---
description: 'Más información acerca de: Diseño de eventos'
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
ms.openlocfilehash: d64bfb13792aa9d646560de844acddd9b7e188c0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642206"
---
# <a name="event-design"></a>Diseño de eventos

Los eventos son la forma de devoluciones de llamada (construcciones que permiten al marco llamar al código de usuario) más usada. Otros mecanismos de devolución de llamada son, por ejemplo, los miembros que toman delegados, los miembros virtuales y los complementos basados en interfaz. Los datos de los estudios de facilidad de uso indican que la mayoría de los desarrolladores se sienten más cómodos con los eventos que con los otros mecanismos de devolución de llamada. Los eventos se integran perfectamente con Visual Studio y muchos lenguajes.

 Es importante tener en cuenta que hay dos grupos de eventos: los eventos que se generan antes de que cambie una condición del sistema, denominados "eventos previos", y los eventos generados después de un cambio de condición, denominados "eventos posteriores". Un ejemplo de evento previo sería `Form.Closing`, que se genera antes de que se cierre un formulario. Un ejemplo de un evento posterior sería `Form.Closed`, que se produce después de cerrar un formulario.

 ✔️ Use el término "generar" para los eventos en lugar de "activar" o "desencadenar".

 ✔️ Use <xref:System.EventHandler%601?displayProperty=nameWithType> en lugar de crear manualmente nuevos delegados para usarse como controladores de eventos.

 ✔️ Recomendamos usar una subclase de <xref:System.EventArgs> como argumento de evento, a menos que esté absolutamente seguro de que el evento nunca tendrá que transportar datos al método de control de eventos, en cuyo caso puede utilizar el tipo `EventArgs` directamente.

 Si envía una API mediante `EventArgs` directamente, nunca podrá agregar datos para transportarse con el evento sin interrumpir la compatibilidad. Si utiliza una subclase, incluso si inicialmente está completamente vacía, podrá agregar propiedades a la subclase cuando sea necesario.

 ✔️ Use un método virtual protegido para generar cada evento. Esto solo se aplica a eventos no estáticos en clases no selladas, y no en estructuras, clases selladas o eventos estáticos.

 El propósito del método es proporcionar una manera para que una clase derivada controle el evento mediante una invalidación. La invalidación es una forma más flexible, rápida y natural de controlar eventos de clase base en clases derivadas. Por convención, el nombre del método debe empezar por "On" e ir seguido del nombre del evento.

 La clase derivada puede decidir no llamar a la implementación base del método en su invalidación. Para ello, no incluya ningún procesamiento en el método necesario para que la clase base funcione correctamente.

 ✔️ Tome un parámetro para el método protegido que genera un evento.

 El parámetro debe llamarse `e` y debe escribirse como la clase de argumento de evento.

 ❌ NO pase NULL como emisor al generar un evento no estático.

 ✔️ Pase NULL como emisor al generar un evento estático.

 ❌ NO pase NULL como parámetro de datos de evento al generar un evento.

 Debe pasar `EventArgs.Empty` si no desea pasar datos al método de control de eventos. Los desarrolladores esperan que este parámetro no sea NULL.

 ✔️ Recomendamos generar eventos que el usuario final pueda cancelar. Esto solo se aplica a los eventos previos.

 Use <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> o su subclase como argumento de evento para permitir que el usuario final cancele los eventos.

### <a name="custom-event-handler-design"></a>Diseño de controladores de eventos personalizados

 Hay casos en los que no se puede usar `EventHandler<T>`, como cuando el marco necesita trabajar con versiones anteriores de CLR, que no admitía genéricos. En tales casos, es posible que tenga que diseñar y desarrollar un delegado de controlador de eventos personalizado.

 ✔️ Use un tipo de valor devuelto de void para los controladores de eventos.

 Un controlador de eventos puede invocar varios métodos de control de eventos, posiblemente en varios objetos. Si se permitiera que los métodos de control de eventos devolvieran un valor, habría varios valores devueltos para cada invocación de evento.

 ✔️ Use `object` como el tipo del primer parámetro del controlador de eventos y asígnele el nombre `sender`.

 ✔️ Use <xref:System.EventArgs?displayProperty=nameWithType> o su subclase como el tipo del segundo parámetro del controlador de eventos y asígnele el nombre `e`.

 ❌ NO tenga más de dos parámetros en los controladores de eventos.

 *Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*

 *Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*

## <a name="see-also"></a>Vea también

- [Instrucciones de diseño de miembros](member.md)
- [Instrucciones de diseño de .NET Framework](index.md)
