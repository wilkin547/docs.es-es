---
title: "event (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "event"
  - "remove"
  - "event_CSharpKeyword"
  - "add"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "event (palabra clave) [C#]"
ms.assetid: 7858fd85-153b-4259-85d0-6aa13c35f174
caps.latest.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 28
---
# event (Referencia de C#)
La palabra clave `event` se utiliza para declarar un evento en una clase de editor.  
  
## Ejemplo  
 El ejemplo siguiente muestra cómo declarar y generar un evento que utiliza <xref:System.EventHandler> como tipo de delegado subyacente.  Para obtener el ejemplo de código completo que muestra también cómo utilizar el tipo de delegado genérico <xref:System.EventHandler%601> y cómo suscribirse a un evento y crear un método de control de eventos, vea [Cómo: Publicar eventos que cumplan las directrices de .NET Framework](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md).  
  
 [!code-cs[csrefKeywordsModifiers#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/event_1.cs)]  
  
 Los eventos son un tipo especial de delegado multidifusión que sólo se puede invocar desde dentro de la clase o struct donde se declaran \(la clase de editor\).  Si otras clases o structs se suscriben al evento, se llamará a sus métodos de control de eventos cuando la clase de editor genere el evento.  Para obtener más información y ejemplos de código, vea [Eventos](../../../csharp/programming-guide/events/index.md) y [Delegados](../../../csharp/programming-guide/delegates/index.md).  
  
 Los eventos se pueden marcar como [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) o `protected``internal`.  Estos modificadores de acceso definen cómo los usuarios de la clase pueden tener acceso al evento.  Para obtener más información, vea [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
## Palabras clave y eventos  
 Las palabras clave siguientes se aplican a los eventos.  
  
|Palabra clave|Descripción|Para obtener más información|  
|-------------------|-----------------|----------------------------------|  
|[static](../../../csharp/language-reference/keywords/static.md)|Hace que el evento esté siempre disponible para los llamadores, aunque no exista ninguna instancia de la clase.|[Clases estáticas y sus miembros](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)|  
|[virtual](../../../csharp/language-reference/keywords/virtual.md)|Permite que las clases derivadas reemplacen el comportamiento del evento mediante la palabra clave [override](../../../csharp/language-reference/keywords/override.md).|[Herencia](../../../csharp/programming-guide/classes-and-structs/inheritance.md)|  
|[sealed](../../../csharp/language-reference/keywords/sealed.md)|Especifica que el evento ya no es virtual para las clases derivadas.||  
|[abstract](../../../csharp/language-reference/keywords/abstract.md)|El compilador no generará los bloques de descriptor de acceso a eventos `add` y `remove` y, por tanto, las clases derivadas deben proporcionar su propia implementación.||  
  
 Un evento puede declararse como evento estático mediante la palabra clave [static](../../../csharp/language-reference/keywords/static.md).  Esto hace que el evento esté siempre disponible para los llamadores, aunque no exista ninguna instancia de la clase.  Para obtener más información, vea [Clases estáticas y sus miembros](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
 Un evento puede marcarse como virtual mediante la palabra clave [virtual](../../../csharp/language-reference/keywords/virtual.md).  Esto permite que las clases derivadas invaliden el comportamiento del evento mediante la palabra clave [override](../../../csharp/language-reference/keywords/override.md).  Para obtener más información, vea [Herencia](../../../csharp/programming-guide/classes-and-structs/inheritance.md).  Un evento que invalida un evento virtual también puede ser de tipo [sealed](../../../csharp/language-reference/keywords/sealed.md), que especifica que ya no es virtual para las clases derivadas.  Por último, un evento puede declararse como [abstract](../../../csharp/language-reference/keywords/abstract.md), lo cual significa que el compilador no generará los bloques de descriptores de acceso de eventos `add` y `remove`.  Por consiguiente, las clases derivadas deben proporcionar su propia implementación.  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [agregar](../../../csharp/language-reference/keywords/add.md)   
 [quitar](../../../csharp/language-reference/keywords/remove.md)   
 [Modificadores](../../../csharp/language-reference/keywords/modifiers.md)   
 [Cómo: Combinar delegados \(delegados de multidifusión\)](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)