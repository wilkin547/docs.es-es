---
title: Crear un grupo anidado (LINQ en C#)
description: Obtenga información sobre cómo crear un grupo anidado en una expresión de consulta LINQ en C#.
ms.date: 12/01/2016
ms.assetid: e9f00708-362e-4d13-98c5-d77549347ba0
ms.openlocfilehash: 7d056c9e215ccc7ca24d621b64e2328bed79f22e
ms.sourcegitcommit: 5dcfeb59179e81071f54840d4902cbe00b184294
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2019
ms.locfileid: "54857676"
---
# <a name="create-a-nested-group"></a>Crear un grupo anidado

En el ejemplo siguiente se muestra cómo crear grupos anidados en una expresión de consulta LINQ. Cada grupo creado a partir del nivel académico o del año de los estudiantes se subdivide en grupos según sus nombres.

## <a name="example"></a>Ejemplo

> [!NOTE]
> Este ejemplo contiene referencias a objetos que se definen en el código de ejemplo del tema [Consultar una colección de objetos](query-a-collection-of-objects.md).

[!code-csharp[csProgGuideLINQ#24](~/samples/snippets/csharp/concepts/linq/how-to-create-a-nested-group_1.cs)]

Tenga en cuenta que se necesitan tres bucles `foreach` anidados para recorrer en iteración los elementos internos de un grupo anidado.

## <a name="see-also"></a>Vea también

- [Language-Integrated Query (LINQ)](index.md)
