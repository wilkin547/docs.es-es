---
title: "C&#243;mo: Implementar descriptores de acceso de eventos personalizados (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "descriptores de acceso [C#], descriptores de acceso de un evento"
  - "add (descriptor de acceso) [C#]"
  - "eventos [C#], add (descriptor de acceso)"
  - "eventos [C#], remove (descriptor de acceso)"
  - "remove (descriptor de acceso) [C#]"
ms.assetid: bf903abf-03a4-4f7b-ab6b-b7e59bc2ee1e
caps.latest.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 7
---
# C&#243;mo: Implementar descriptores de acceso de eventos personalizados (Gu&#237;a de programaci&#243;n de C#)
Un evento es un tipo especial de delegado de multidifusión que solo puede invocarse desde dentro de la clase en la que se declara.  El código cliente se suscribe al evento proporcionando una referencia a un método que debería invocarse cuando se desencadena el evento.  Estos métodos se agregan a la lista de invocación del delegado a través de descriptores de acceso de eventos, que son similares a los descriptores de acceso de propiedad, con la diferencia de que los descriptores de acceso de eventos se denominan `add` y `remove`.  En la mayoría de los casos, no tiene que proporcionar descriptores de acceso de eventos personalizados.  Cuando no proporciona ningún descriptor de acceso de eventos personalizado en el código, el compilador los agrega automáticamente.  Sin embargo, en algunos casos puede que tenga que proporcionar un comportamiento personalizado.  Uno de estos casos se muestra en el tema [Cómo: Implementar eventos de interfaz](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo implementar descriptores de acceso de eventos add y remove personalizados.  Aunque puede sustituir cualquier código dentro de los descriptores de acceso, recomendamos que bloquee el evento antes de agregar o quitar un nuevo método de control de eventos.  
  
```  
event EventHandler IDrawingObject.OnDraw  
        {  
            add  
            {  
                lock (PreDrawEvent)  
                {  
                    PreDrawEvent += value;  
                }  
            }  
            remove  
            {  
                lock (PreDrawEvent)  
                {  
                    PreDrawEvent -= value;  
                }  
            }  
        }  
  
```  
  
## Vea también  
 [Eventos](../../../csharp/programming-guide/events/index.md)   
 [event](../../../csharp/language-reference/keywords/event.md)