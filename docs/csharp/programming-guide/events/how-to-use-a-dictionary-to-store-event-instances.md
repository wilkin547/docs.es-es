---
title: 'Uso de un diccionario para almacenar instancias de eventos: Guía de programación de C#'
ms.custom: seodec18
ms.date: 03/11/2019
helpviewer_keywords:
- events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
ms.openlocfilehash: f8522e499887398402f63c7788bbc6c6c4f57782
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2019
ms.locfileid: "57845284"
---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a>Uso de un diccionario para almacenar instancias de eventos (Guía de programación de C#)

Un uso de los descriptores de acceso personalizados `add` y `remove` es exponer muchos eventos sin asignar un campo para cada evento, pero, en su lugar, a través de una instancia <xref:System.Collections.Generic.Dictionary%602> para almacenar las instancias de eventos, como se muestra en el ejemplo siguiente. Esto solo es útil si un tipo tiene muchos eventos, pero se espera que la mayoría de los eventos no estén suscritos.

[!code-csharp[csProgGuideEvents#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#9)]

Esta implementación se ajusta al comportamiento de [agregar y quitar delegados](~/_csharplang/spec/delegates.md#delegate-invocation) en la especificación del lenguaje C#.

Tenga en cuenta que la instrucción [lock](../../language-reference/keywords/lock-statement.md) solo se usa para *acceder* al diccionario con controladores de eventos. No invoque un controlador de eventos dentro del cuerpo de la instrucción `lock`, porque podría conducir a interbloqueos o a la contención de bloqueo.

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../../csharp/programming-guide/index.md)
- [Eventos](../../../csharp/programming-guide/events/index.md)
- [Delegados](../../../csharp/programming-guide/delegates/index.md)
