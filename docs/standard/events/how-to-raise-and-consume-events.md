---
title: 'Cómo: Provocar y utilizar eventos'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- events [.NET Framework], raising
- raising events
- events [.NET Framework], samples
ms.assetid: 42afade7-3a02-4f2e-868b-95845f302f8f
ms.openlocfilehash: 256b5ae9ac2145e339136985872dfa5423aca730
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73131592"
---
# <a name="how-to-raise-and-consume-events"></a>Cómo: Provocar y utilizar eventos
En los ejemplos de este tema se muestra cómo trabajar con eventos. Se incluyen ejemplos del delegado <xref:System.EventHandler>, el delegado <xref:System.EventHandler%601> y un delegado personalizado, para ilustrar eventos con y sin datos.  
  
 En los ejemplos se usan los conceptos descritos en el artículo [Eventos](../../../docs/standard/events/index.md).  
  
## <a name="example"></a>Ejemplo  
 En el primer ejemplo se muestra cómo generar y consumir un evento que no tiene datos. Contiene una clase denominada `Counter` que tiene un evento denominado `ThresholdReached`. Este evento se genera cuando un valor de contador iguala o supera el valor de umbral. El delegado <xref:System.EventHandler> está asociado al evento, porque no se proporcionan datos de evento.  
  
 [!code-csharp[EventsOverview#5](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programnodata.cs#5)]
 [!code-vb[EventsOverview#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1nodata.vb#5)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo generar y consumir un evento que proporciona datos. El delegado <xref:System.EventHandler%601> está asociado al evento, y se proporciona una instancia de un objeto de datos de eventos personalizados.  
  
 [!code-cpp[EventsOverview#6](../../../samples/snippets/cpp/VS_Snippets_CLR/eventsoverview/cpp/programwithdata.cpp#6)]
 [!code-csharp[EventsOverview#6](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programwithdata.cs#6)]
 [!code-vb[EventsOverview#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1withdata.vb#6)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo declarar un delegado para un evento. El delegado se denomina `ThresholdReachedEventHandler`. Esto es simplemente una ilustración. Normalmente no es necesario declarar un delegado para un evento, porque se puede usar el delegado <xref:System.EventHandler> o <xref:System.EventHandler%601>. Solo debe declararse un delegado en escenarios poco habituales, como cuando se facilita el uso de una clase a código heredado que no puede usar elementos genéricos.  
  
 [!code-csharp[EventsOverview#7](../../../samples/snippets/csharp/VS_Snippets_CLR/eventsoverview/cs/programwithdelegate.cs#7)]
 [!code-vb[EventsOverview#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/eventsoverview/vb/module1withdelegate.vb#7)]  
  
## <a name="see-also"></a>Vea también

- [Eventos](../../../docs/standard/events/index.md)
