---
title: 'Cómo: Controlar varios eventos mediante propiedades de eventos'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- event properties [.NET Framework]
- multiple events [.NET Framework]
- event handling [.NET Framework], with multiple events
- events [.NET Framework], multiple
ms.assetid: 30047cba-e2fd-41c6-b9ca-2ad7a49003db
ms.openlocfilehash: c5be541c1a40c5d16a0502e76adef24f6a41cc89
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288477"
---
# <a name="how-to-handle-multiple-events-using-event-properties"></a>Cómo: Controlar varios eventos mediante propiedades de eventos
Para poder utilizar propiedades de evento, hay que definirlas en la clase que provoca los eventos y, a continuación, establecer los delegados de las propiedades de evento en las clases que controlan los eventos. Para implementar varias propiedades de evento en una clase, esta clase deberá almacenar internamente y mantener el delegado definido para cada evento. Para hacerlo, uno de los enfoques típicos consiste en implementar una colección de delegados que se indice por medio de una clave de evento.  
  
 Para almacenar los delegados de cada evento, puede utilizar la clase <xref:System.ComponentModel.EventHandlerList> o implementar su propia colección. La clase de colección debe proporcionar métodos para establecer, obtener acceso y recuperar el delegado del controlador de eventos basándose en la clave del evento. Por ejemplo, se puede utilizar una clase <xref:System.Collections.Hashtable> o derivar una clase personalizada a partir de la clase <xref:System.Collections.DictionaryBase>. No es necesario exponer los detalles de implementación de la colección de delegados fuera de la clase.  
  
 Cada una de las propiedades de evento de la clase define un método de descriptor de acceso add y un método de descriptor de acceso remove. El descriptor de acceso add de una propiedad de evento agrega la instancia de delegado de entrada a la colección de delegados. El descriptor de acceso remove de una propiedad de evento quita la instancia de delegado de entrada de la colección de delegados. Los descriptores de acceso de las propiedades de eventos utilizan la clave predefinida de la propiedad de evento para agregar y quitar instancias en la colección de delegados.  
  
### <a name="to-handle-multiple-events-using-event-properties"></a>Para controlar varios eventos mediante las propiedades de evento  
  
1. Defina una colección de delegados dentro de la clase que provoca los eventos.  
  
2. Defina una clave para cada evento.  
  
3. Defina las propiedades de evento de la clase que provoca los eventos.  
  
4. Utilice la colección de delegados para implementar los métodos de descriptor de acceso add y remove de las propiedades de evento.  
  
5. Utilice las propiedades de evento públicas para agregar y quitar delegados de controlador de eventos en las clases que controlan los eventos.  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo de C#, se implementan las propiedades de evento `MouseDown` y `MouseUp` mediante el uso de <xref:System.ComponentModel.EventHandlerList> para almacenar el delegado de cada evento. Las palabras clave de las construcciones de propiedades de evento están en negrita.  
  
 [!code-cpp[Conceptual.Events.Other#31](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.events.other/cpp/example3.cpp#31)]
 [!code-csharp[Conceptual.Events.Other#31](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.events.other/cs/example3.cs#31)]
 [!code-vb[Conceptual.Events.Other#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.events.other/vb/example3.vb#31)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.ComponentModel.EventHandlerList?displayProperty=nameWithType>
- [Eventos](index.md)
- <xref:System.Web.UI.Control.Events%2A?displayProperty=nameWithType>
- [Declarar eventos personalizados para conservar memoria](../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
