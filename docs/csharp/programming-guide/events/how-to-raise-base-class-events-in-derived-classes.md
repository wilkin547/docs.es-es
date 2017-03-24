---
title: "C&#243;mo: Producir eventos de una clase base en clases derivadas (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "eventos [C#], en clases derivadas"
ms.assetid: 2d20556a-0aad-46fc-845e-f85d86ea617a
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# C&#243;mo: Producir eventos de una clase base en clases derivadas (Gu&#237;a de programaci&#243;n de C#)
El siguiente ejemplo simple muestra la forma estándar de declarar eventos en una clase base para que también se puedan generar desde clases derivadas.  Este modelo se utiliza ampliamente en clases de formularios Windows Forms de la biblioteca de clases de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)].  
  
 Cuando cree una clase que pueda utilizarse como clase base de otras clases, debe tener en cuenta que los eventos son un tipo especial de delegado que sólo se pueden invocar desde dentro la clase que los declaró.  Las clases derivadas no pueden invocar directamente a eventos declarados dentro de la clase base.  Aunque a veces puede ser conveniente que sólo la clase base pueda provocar un evento, normalmente deberá habilitar la clase derivada para invocar eventos de clase base.  Para ello, puede crear un método de invocación protegido en la clase base que contiene el evento.  Al llamar a este método de invocación o al reemplazarlo, las clases derivadas podrán invocar directamente el evento.  
  
> [!NOTE]
>  No declare eventos virtuales en una clase base y los invalide en una clase derivada.  El compilador de C\# no administra correctamente y es imprevisible si un suscriptor al evento derivado suscribirá realmente al evento de clase base.  
  
## Ejemplo  
 [!code-cs[csProgGuideEvents#1](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-raise-base-class-events-in-derived-classes_1.cs)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Eventos](../../../csharp/programming-guide/events/index.md)   
 [Delegados](../../../csharp/programming-guide/delegates/index.md)   
 [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [Creating Event Handlers in Windows Forms](../Topic/Creating%20Event%20Handlers%20in%20Windows%20Forms.md)