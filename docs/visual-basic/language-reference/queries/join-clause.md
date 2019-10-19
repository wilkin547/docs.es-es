---
title: Join (Cláusula, Visual Basic)
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
ms.openlocfilehash: b5211d0ed3f618013dc9fe764a6d7b2db8177c26
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582291"
---
# <a name="join-clause-visual-basic"></a>Join (Cláusula, Visual Basic)

Combina dos colecciones en una sola colección. La operación de combinación se basa en las claves coincidentes y utiliza el operador `Equals`.

## <a name="syntax"></a>Sintaxis

```vb
Join element In collection _
  [ joinClause _ ]
  [ groupJoinClause ... _ ]
On key1 Equals key2 [ And key3 Equals key4 [... ]
```

## <a name="parts"></a>Elementos

`element` Obligatorio. Variable de control de la colección que se va a combinar.

`collection`  
Requerido. Colección que se va a combinar con la colección identificada en el lado izquierdo del operador `Join`. Una cláusula `Join` se puede anidar en otra cláusula `Join` o en una cláusula `Group Join`.

`joinClause`  
Opcional. Una o varias cláusulas de `Join` adicionales para restringir aún más la consulta.

`groupJoinClause`  
Opcional. Una o varias cláusulas de `Group Join` adicionales para restringir aún más la consulta.

`key1` `Equals` `key2`  
Requerido. Identifica las claves para las colecciones que se están combinando. Debe utilizar el operador `Equals` para comparar las claves de las colecciones que se están combinando. Puede combinar condiciones de combinación mediante el operador `And` para identificar varias claves. `key1` debe ser de la colección en el lado izquierdo del operador de `Join`. `key2` debe ser de la colección del lado derecho del operador de `Join`.

Las claves utilizadas en la condición de combinación pueden ser expresiones que incluyen más de un elemento de la colección. Sin embargo, cada expresión clave solo puede contener elementos de su colección respectiva.

## <a name="remarks"></a>Comentarios

La cláusula `Join` combina dos colecciones basadas en los valores de clave coincidentes de las colecciones que se van a combinar. La colección resultante puede contener cualquier combinación de valores de la colección identificada en el lado izquierdo del operador `Join` y la colección identificada en la cláusula `Join`. La consulta devolverá solo los resultados para los que se cumple la condición especificada por el operador `Equals`. Esto es equivalente a un `INNER JOIN` en SQL.

Puede usar varias cláusulas `Join` en una consulta para combinar dos o más colecciones en una sola colección.

Puede realizar una combinación implícita para combinar colecciones sin la cláusula `Join`. Para ello, incluya varias cláusulas `In` en la cláusula `From` y especifique una cláusula `Where` que identifique las claves que desea usar para la combinación.

Puede usar la cláusula `Group Join` para combinar colecciones en una sola colección jerárquica. Esto es como un `LEFT OUTER JOIN` en SQL.

## <a name="example"></a>Ejemplo

En el ejemplo de código siguiente se realiza una combinación implícita para combinar una lista de clientes con sus pedidos.

[!code-vb[VbSimpleQuerySamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#13)]

## <a name="example"></a>Ejemplo

En el ejemplo de código siguiente se combinan dos colecciones mediante la cláusula `Join`.

[!code-vb[VbSimpleQuerySamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples2.vb#12)]

Este ejemplo generará una salida similar a la siguiente:

`winlogon (968), Windows Logon`

`explorer (2424), File Explorer`

`cmd (5136), Command Window`

## <a name="example"></a>Ejemplo

En el ejemplo de código siguiente se combinan dos colecciones mediante la cláusula `Join` con dos columnas de clave.

[!code-vb[VbSimpleQuerySamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples3.vb#17)]

En el ejemplo se producirá una salida similar a la siguiente:

`winlogon (968), Windows Logon, Priority = 13`

`cmd (700), Command Window, Priority = 8`

`explorer (2424), File Explorer, Priority = 8`

## <a name="see-also"></a>Vea también

- [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Consultas](../../../visual-basic/language-reference/queries/index.md)
- [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)
- [From (cláusula)](../../../visual-basic/language-reference/queries/from-clause.md)
- [Group Join (cláusula)](../../../visual-basic/language-reference/queries/group-join-clause.md)
- [Where (cláusula)](../../../visual-basic/language-reference/queries/where-clause.md)
