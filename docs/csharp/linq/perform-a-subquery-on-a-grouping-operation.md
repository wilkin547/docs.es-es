---
title: Realizar una subconsulta en una operación de agrupación (LINQ en C#)
description: Obtenga información sobre cómo realizar una subconsulta en una operación de agrupación con LINQ en C#.
ms.date: 12/01/2016
ms.assetid: d75a588e-9b6f-4f37-b195-f99ec8503855
ms.openlocfilehash: fd26f87ad7d5b4892f086bf8c7a34cf19a7f9e02
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173372"
---
# <a name="perform-a-subquery-on-a-grouping-operation"></a>Realizar una subconsulta en una operación de agrupación

En este artículo se muestran dos maneras diferentes de crear una consulta que ordena los datos de origen en grupos y, luego, realiza una subconsulta en cada grupo de forma individual. La técnica básica de cada ejemplo consiste en agrupar los elementos de origen usando una *continuación* denominada `newGroup` y después generar una nueva subconsulta en `newGroup`. Esta subconsulta se ejecuta en cada uno de los nuevos grupos creados por la consulta externa. Tenga en cuenta que en este ejemplo concreto el resultado final no es un grupo, sino una secuencia plana de tipos anónimos.  
  
Para obtener más información sobre cómo agrupar, consulte [Cláusula group](../language-reference/keywords/group-clause.md).  
  
Para obtener más información sobre continuaciones, consulte [into](../language-reference/keywords/into.md). En el ejemplo siguiente se usa una estructura de datos en memoria como origen de datos, pero se aplican los mismos principios para cualquier tipo de origen de datos LINQ.  
  
## <a name="example"></a>Ejemplo

> [!NOTE]
> Este ejemplo contiene referencias a objetos que se definen en el código de ejemplo de [Query a collection of objects](query-a-collection-of-objects.md) (Consultar una colección de objetos).

[!code-csharp[csProgGuideLINQ#23](~/samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_1.cs)]

La consulta del fragmento de código anterior también se puede escribir con la sintaxis de método. El siguiente fragmento de código tiene una consulta semánticamente equivalente escrita con sintaxis de método.

[!code-csharp[csProgGuideLINQ#86](~/samples/snippets/csharp/concepts/linq/how-to-perform-a-subquery-on-a-grouping-operation_2.cs)]

## <a name="see-also"></a>Vea también

- [Language-Integrated Query (LINQ)](index.md)
