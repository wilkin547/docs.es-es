---
title: Cláusula Join
ms.date: 07/20/2015
f1_keywords:
- vb.QueryJoinIn
- vb.QueryJoin
- vb.QueryJoinOn
helpviewer_keywords:
- queries [Visual Basic], Join
- Join statement [Visual Basic]
- Join clause [Visual Basic]
ms.assetid: 6dd37936-b27c-4e00-98ad-154b23f4de64
ms.openlocfilehash: f73dc31bbbb9014a8a1a315de406c53fa58d1c65
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359779"
---
# <a name="join-clause-visual-basic"></a>Join (Cláusula, Visual Basic)

Combina dos colecciones en una sola colección. La operación de combinación se basa en las claves coincidentes y utiliza el `Equals` operador.

## <a name="syntax"></a>Sintaxis

```vb
Join element In collection _
  [ joinClause _ ]
  [ groupJoinClause ... _ ]
On key1 Equals key2 [ And key3 Equals key4 [... ]
```

## <a name="parts"></a>Partes

`element` Obligatorio. Variable de control de la colección que se va a combinar.

`collection`  
Necesario. Colección que se va a combinar con la colección identificada en el lado izquierdo del `Join` operador. Una `Join` cláusula se puede anidar en otra `Join` cláusula o en una `Group Join` cláusula.

`joinClause`  
Opcional. Una o más `Join` cláusulas adicionales para restringir aún más la consulta.

`groupJoinClause`  
Opcional. Una o más `Group Join` cláusulas adicionales para restringir aún más la consulta.

`key1` `Equals` `key2`  
Necesario. Identifica las claves para las colecciones que se están combinando. Debe utilizar el `Equals` operador para comparar las claves de las colecciones que se están combinando. Puede combinar condiciones de combinación mediante el `And` operador para identificar varias claves. `key1`debe ser de la colección en el lado izquierdo del `Join` operador. `key2`debe ser de la colección del lado derecho del `Join` operador.

Las claves utilizadas en la condición de combinación pueden ser expresiones que incluyen más de un elemento de la colección. Sin embargo, cada expresión clave solo puede contener elementos de su colección respectiva.

## <a name="remarks"></a>Observaciones

La `Join` cláusula combina dos colecciones basadas en los valores de clave coincidentes de las colecciones que se están combinando. La colección resultante puede contener cualquier combinación de valores de la colección identificada en el lado izquierdo del `Join` operador y la colección identificada en la `Join` cláusula. La consulta devolverá solo los resultados para los que se cumple la condición especificada por el `Equals` operador. Esto es equivalente a `INNER JOIN` en SQL.

Puede usar varias `Join` cláusulas en una consulta para combinar dos o más colecciones en una sola colección.

Puede realizar una combinación implícita para combinar colecciones sin la `Join` cláusula. Para ello, incluya varias `In` cláusulas en la `From` cláusula y especifique una `Where` cláusula que identifique las claves que desea usar para la combinación.

Puede usar la `Group Join` cláusula para combinar colecciones en una sola colección jerárquica. Es como un `LEFT OUTER JOIN` en SQL.

## <a name="example"></a>Ejemplo

En el ejemplo de código siguiente se realiza una combinación implícita para combinar una lista de clientes con sus pedidos.

[!code-vb[VbSimpleQuerySamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#13)]

## <a name="example"></a>Ejemplo

En el ejemplo de código siguiente se combinan dos colecciones mediante la `Join` cláusula.

[!code-vb[VbSimpleQuerySamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples2.vb#12)]

Este ejemplo generará una salida similar a la siguiente:

`winlogon (968), Windows Logon`

`explorer (2424), File Explorer`

`cmd (5136), Command Window`

## <a name="example"></a>Ejemplo

En el ejemplo de código siguiente se combinan dos colecciones mediante la `Join` cláusula con dos columnas de clave.

[!code-vb[VbSimpleQuerySamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples3.vb#17)]

En el ejemplo se producirá una salida similar a la siguiente:

`winlogon (968), Windows Logon, Priority = 13`

`cmd (700), Command Window, Priority = 8`

`explorer (2424), File Explorer, Priority = 8`

## <a name="see-also"></a>Consulte también

- [Introducción a LINQ en Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Consultas](index.md)
- [Select (cláusula)](select-clause.md)
- [Cláusula FROM](from-clause.md)
- [Cláusula Group Join](group-join-clause.md)
- [Cláusula WHERE](where-clause.md)
