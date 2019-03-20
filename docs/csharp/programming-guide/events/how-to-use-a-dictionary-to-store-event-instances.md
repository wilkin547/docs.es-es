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
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a><span data-ttu-id="f6a9a-102">Uso de un diccionario para almacenar instancias de eventos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="f6a9a-102">How to: use a dictionary to store event instances (C# Programming Guide)</span></span>

<span data-ttu-id="f6a9a-103">Un uso de los descriptores de acceso personalizados `add` y `remove` es exponer muchos eventos sin asignar un campo para cada evento, pero, en su lugar, a través de una instancia <xref:System.Collections.Generic.Dictionary%602> para almacenar las instancias de eventos, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f6a9a-103">One use for the `add` and `remove` custom event accessors is to expose many events without allocating a field for each event, but instead using a <xref:System.Collections.Generic.Dictionary%602> instance to store the event instances, as the example below demonstrates.</span></span> <span data-ttu-id="f6a9a-104">Esto solo es útil si un tipo tiene muchos eventos, pero se espera que la mayoría de los eventos no estén suscritos.</span><span class="sxs-lookup"><span data-stu-id="f6a9a-104">This is only useful if a type has many events, but you expect that most of the events will not be subscribed to.</span></span>

[!code-csharp[csProgGuideEvents#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#9)]

<span data-ttu-id="f6a9a-105">Esta implementación se ajusta al comportamiento de [agregar y quitar delegados](~/_csharplang/spec/delegates.md#delegate-invocation) en la especificación del lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="f6a9a-105">This implementation conforms to the behavior for [adding and removing delegates](~/_csharplang/spec/delegates.md#delegate-invocation) in the C# language specification.</span></span>

<span data-ttu-id="f6a9a-106">Tenga en cuenta que la instrucción [lock](../../language-reference/keywords/lock-statement.md) solo se usa para *acceder* al diccionario con controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="f6a9a-106">Note that the [lock](../../language-reference/keywords/lock-statement.md) statement is used only to *access* the dictionary with event handlers.</span></span> <span data-ttu-id="f6a9a-107">No invoque un controlador de eventos dentro del cuerpo de la instrucción `lock`, porque podría conducir a interbloqueos o a la contención de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="f6a9a-107">Don't invoke an event handler inside the body of the `lock` statement, as it could lead to deadlocks or lock contention.</span></span>

## <a name="see-also"></a><span data-ttu-id="f6a9a-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6a9a-108">See also</span></span>

- [<span data-ttu-id="f6a9a-109">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="f6a9a-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="f6a9a-110">Eventos</span><span class="sxs-lookup"><span data-stu-id="f6a9a-110">Events</span></span>](../../../csharp/programming-guide/events/index.md)
- [<span data-ttu-id="f6a9a-111">Delegados</span><span class="sxs-lookup"><span data-stu-id="f6a9a-111">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
