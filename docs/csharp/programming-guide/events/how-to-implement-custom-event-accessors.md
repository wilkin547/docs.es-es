---
title: 'Procedimiento Implementar descriptores de acceso de eventos personalizados: Guía de programación de C#'
description: Aprenda a implementar descriptores de acceso de eventos personalizados. Vea un ejemplo de código y examine los recursos adicionales disponibles.
ms.date: 07/20/2015
helpviewer_keywords:
- accessors [C#], event accessors
- add accessor [C#]
- events [C#], add accessor
- events [C#], remove accessor
- remove accessor [C#]
ms.assetid: bf903abf-03a4-4f7b-ab6b-b7e59bc2ee1e
ms.openlocfilehash: 41c9bd255bf66cd914982b6044c4acaef66b8fcf
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167566"
---
# <a name="how-to-implement-custom-event-accessors-c-programming-guide"></a>Procedimiento Implementar descriptores de acceso de eventos personalizados (Guía de programación de C#)

Un evento es un tipo especial de delegado de multidifusión que solo puede invocarse desde dentro de la clase en la que se declara. El código cliente se suscribe al evento proporcionando una referencia a un método que debería invocarse cuando se desencadena el evento. Estos métodos se agregan a la lista de invocación del delegado a través de descriptores de acceso de eventos, que son similares a los descriptores de acceso de propiedad, con la diferencia de que los descriptores de acceso de eventos se denominan `add` y `remove`. En la mayoría de los casos, no tiene que proporcionar descriptores de acceso de eventos personalizados. Cuando no proporciona ningún descriptor de acceso de eventos personalizado en el código, el compilador los agrega automáticamente. En cambio, en algunos casos puede que tenga que proporcionar un comportamiento personalizado. Uno de estos casos se muestra en el tema [Procedimiento Implementar eventos de interfaz](./how-to-implement-interface-events.md).
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra cómo implementar descriptores de acceso de eventos add y remove personalizados. Aunque puede sustituir cualquier código dentro de los descriptores de acceso, recomendamos que bloquee el evento antes de agregar o quitar un nuevo método de control de eventos.  
  
[!code-csharp[IDrawingObject.OnDraw](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#IDrawingObjectOnDraw)]  
  
## <a name="see-also"></a>Vea también

- [Eventos](./index.md)
- [event](../../language-reference/keywords/event.md)
