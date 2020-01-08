---
title: 'Eventos: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- classes [C#], events
- C# language, events
- events [C#]
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
ms.openlocfilehash: 84a7eba7bf71f5ef5a0f46eb5863952e1af37c86
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635436"
---
# <a name="events-c-programming-guide"></a>Eventos (Guía de programación de C#)
Cuando ocurre algo interesante, los eventos habilitan una [clase](../../language-reference/keywords/class.md) u objeto para notificarlo a otras clases u objetos. La clase que envía (o *genera*) el evento recibe el nombre de *publicador* y las clases que reciben (o *controlan*) el evento se denominan *suscriptores*.  
  
En una aplicación web o una aplicación de Windows Forms en C# típica, se puede suscribir a eventos generados por controles, como botones y cuadros de lista. Puede usar el entorno de desarrollo integrado (IDE) de Visual C# para examinar los eventos que publica un control y seleccionar los que quiera administrar. El IDE proporciona una forma sencilla de agregar automáticamente un método de controlador de eventos vacío y el código para suscribirse al evento. Para obtener más información, vea [Procedimiento para suscribir y cancelar la suscripción a eventos](./how-to-subscribe-to-and-unsubscribe-from-events.md).
  
## <a name="events-overview"></a>Información general sobre eventos  
 Los eventos tienen las siguientes propiedades:  
  
- El publicador determina el momento en el que se genera un evento; los suscriptores determinan la acción que se lleva a cabo en respuesta al evento.  
  
- Un evento puede tener varios suscriptores. Un suscriptor puede controlar varios eventos de varios publicadores.  
  
- Nunca se generan eventos que no tienen suscriptores.  
  
- Los eventos se suelen usar para indicar acciones del usuario, como los clics de los botones o las selecciones de menú en las interfaces gráficas de usuario.  
  
- Cuando un evento tiene varios suscriptores, los controladores de eventos se invocan sincrónicamente cuando se genera un evento. Para invocar eventos de forma asincrónica, consulte [Calling Synchronous Methods Asynchronously](../../../standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).  
  
- En la biblioteca de clases de .NET Framework, los eventos se basan en el delegado <xref:System.EventHandler> y en la clase base <xref:System.EventArgs>.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 Para obtener más información, consulte:  
  
- [Procedimiento para suscribir y cancelar la suscripción a eventos](./how-to-subscribe-to-and-unsubscribe-from-events.md)

- [Procedimiento para publicar eventos que cumplan las instrucciones de .NET Framework](./how-to-publish-events-that-conform-to-net-framework-guidelines.md)

- [Procedimiento para generar eventos de una clase base en clases derivadas](./how-to-raise-base-class-events-in-derived-classes.md)

- [Procedimiento para implementar eventos de interfaz](./how-to-implement-interface-events.md)

- [Procedimiento para implementar descriptores de acceso de eventos personalizados](./how-to-implement-custom-event-accessors.md)

## <a name="c-language-specification"></a>Especificación del lenguaje C#  

Para obtener más información, consulte la sección [Eventos](~/_csharplang/spec/classes.md#events) de [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction). La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.
  
## <a name="featured-book-chapters"></a>Capítulos destacados del libro  
 [Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) (Delegados, eventos y expresiones lambda) en [C# 3.0 Cookbook, Tercera edición: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29) (Más de 250 soluciones para programadores de C# 3.0)  
  
 [Delegates and Events](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652490%28v=orm.10%29) (Delegados y eventos) en [Learning C# 3.0: Master the fundamentals of C# 3.0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652493%28v=orm.10%29)  
  
## <a name="see-also"></a>Vea también

- <xref:System.EventHandler>
- [Guía de programación de C#](../index.md)
- [Delegados](../delegates/index.md)
- [Crear controladores de eventos en Windows Forms](../../../framework/winforms/creating-event-handlers-in-windows-forms.md)
