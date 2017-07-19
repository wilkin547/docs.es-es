---
title: "Eventos (Guía de programación de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- classes [C#], events
- C# language, events
- events [C#]
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
caps.latest.revision: 43
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: b3f4673eccdbd568fa8ab042023a4b3bd8230bb3
ms.contentlocale: es-es
ms.lasthandoff: 06/12/2017

---
<a id="events-c-programming-guide" class="xliff"></a>

# Eventos (Guía de programación de C#)
Cuando ocurre algo interesante, los eventos habilitan una [clase](../../../csharp/language-reference/keywords/class.md) u objeto para notificarlo a otras clases u objetos. La clase que envía (o *genera*) el evento recibe el nombre de *publicador* y las clases que reciben (o *controlan*) el evento se denominan *suscriptores*.  
  
 En una aplicación web o una aplicación de Windows Forms en C# típica, se puede suscribir a eventos generados por controles, como botones y cuadros de lista. Puede usar el entorno de desarrollo integrado (IDE) de [!INCLUDE[csprcs](~/includes/csprcs-md.md)] para examinar los eventos que publica un control y seleccionar los que quiera administrar. El IDE agrega automáticamente un método de controlador de eventos vacío y el código para suscribirse al evento. Para obtener más información, vea [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md) (Cómo: Suscribir y cancelar la suscripción a eventos [Guía de programación de C#]).  
  
<a id="events-overview" class="xliff"></a>

## Información general sobre eventos  
 Los eventos tienen las siguientes propiedades:  
  
-   El publicador determina el momento en el que se genera un evento; los suscriptores determinan la acción que se lleva a cabo en respuesta al evento.  
  
-   Un evento puede tener varios suscriptores. Un suscriptor puede controlar varios eventos de varios publicadores.  
  
-   Nunca se generan eventos que no tienen suscriptores.  
  
-   Los eventos se suelen usar para indicar acciones del usuario, como los clics de los botones o las selecciones de menú en las interfaces gráficas de usuario.  
  
-   Cuando un evento tiene varios suscriptores, los controladores de eventos se invocan sincrónicamente cuando se genera un evento. Para invocar eventos de forma asincrónica, consulte [Calling Synchronous Methods Asynchronously](https://msdn.microsoft.com/library/2e08f6yc).  
  
-   En la biblioteca de clases [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], los eventos se basan en el delegado <xref:System.EventHandler> y en la clase base <xref:System.EventArgs>.  
  
<a id="related-sections" class="xliff"></a>

## Secciones relacionadas  
 Para obtener más información, consulte:  
  
-   [Cómo: Suscribir y cancelar la suscripción a eventos](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)  
  
-   [Cómo: Publicar eventos que cumplan las directrices de .NET Framework](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)  
  
-   [Cómo: Producir eventos de una clase base en clases derivadas](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)  
  
-   [Cómo: Implementar eventos de interfaz](../../../csharp/programming-guide/events/how-to-implement-interface-events.md)  
  
-   [Sincronización de subprocesos](../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)  
  
-   [Cómo: Utilizar un diccionario para almacenar instancias de eventos](../../../csharp/programming-guide/events/how-to-use-a-dictionary-to-store-event-instances.md)  
  
-   [Cómo: Implementar descriptores de acceso de eventos personalizados](../../../csharp/programming-guide/events/how-to-implement-custom-event-accessors.md)  
  
<a id="c-language-specification" class="xliff"></a>

## Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
<a id="featured-book-chapters" class="xliff"></a>

## Capítulos destacados del libro  
 [Delegates, Events, and Lambda Expressions](http://go.microsoft.com/fwlink/?LinkId=195395) (Delegados, eventos y expresiones lambda) en [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](http://go.microsoft.com/fwlink/?LinkId=195369)  
  
 [Delegates and Events](http://go.microsoft.com/fwlink/?LinkId=195418) in [Learning C# 3.0: Master the fundamentals of C# 3.0](http://go.microsoft.com/fwlink/?LinkId=195412)  
  
<a id="see-also" class="xliff"></a>

## Vea también  
 <xref:System.EventHandler>   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Delegados](../../../csharp/programming-guide/delegates/index.md)   
 [Crear controladores de eventos en Windows Forms](https://msdn.microsoft.com/library/dacysss4.aspx)   
 [Programación multiproceso con el modelo asincrónico basado en eventos](https://msdn.microsoft.com/library/hkasytyf)
