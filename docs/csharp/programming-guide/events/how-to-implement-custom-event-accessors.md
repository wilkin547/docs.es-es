---
title: "Cómo: Implementar descriptores de acceso de eventos personalizados (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- accessors [C#], event accessors
- add accessor [C#]
- events [C#], add accessor
- events [C#], remove accessor
- remove accessor [C#]
ms.assetid: bf903abf-03a4-4f7b-ab6b-b7e59bc2ee1e
caps.latest.revision: 7
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 71e1c16c9c6426ffb95020e4d7211dc1000f6796
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-implement-custom-event-accessors-c-programming-guide"></a>Cómo: Implementar descriptores de acceso de eventos personalizados (Guía de programación de C#)
Un evento es un tipo especial de delegado de multidifusión que solo puede invocarse desde dentro de la clase en la que se declara. El código cliente se suscribe al evento proporcionando una referencia a un método que debería invocarse cuando se desencadena el evento. Estos métodos se agregan a la lista de invocación del delegado a través de descriptores de acceso de eventos, que son similares a los descriptores de acceso de propiedad, con la diferencia de que los descriptores de acceso de eventos se denominan `add` y `remove`. En la mayoría de los casos, no tiene que proporcionar descriptores de acceso de eventos personalizados. Cuando no proporciona ningún descriptor de acceso de eventos personalizado en el código, el compilador los agrega automáticamente. En cambio, en algunos casos puede que tenga que proporcionar un comportamiento personalizado. Uno de estos casos se muestra en el tema [Cómo: Implementar eventos de interfaz](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo implementar descriptores de acceso de eventos add y remove personalizados. Aunque puede sustituir cualquier código dentro de los descriptores de acceso, recomendamos que bloquee el evento antes de agregar o quitar un nuevo método de control de eventos.  
  
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
  
## <a name="see-also"></a>Vea también  
 [Eventos](../../../csharp/programming-guide/events/index.md)   
 [event](../../../csharp/language-reference/keywords/event.md)

