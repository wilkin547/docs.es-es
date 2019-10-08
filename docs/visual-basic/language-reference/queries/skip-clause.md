---
title: Skip (Cláusula, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkip
helpviewer_keywords:
- queries [Visual Basic], Skip
- Skip statement [Visual Basic]
- Skip clause [Visual Basic]
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
ms.openlocfilehash: e52de186e1475bfabd02821a0cd2384d8350eed3
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004766"
---
# <a name="skip-clause-visual-basic"></a>Skip (Cláusula, Visual Basic)
Omite un número especificado de elementos de una colección y, a continuación, devuelve los elementos restantes.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Skip count  
```  
  
## <a name="parts"></a>Elementos  
 `count`  
 Obligatorio. Un valor o una expresión que se evalúa como el número de elementos de la secuencia que se va a omitir.  
  
## <a name="remarks"></a>Comentarios  
 La cláusula `Skip` hace que una consulta omita los elementos al principio de una lista de resultados y devuelva los elementos restantes. El número de elementos que se van a omitir se identifica mediante el parámetro `count`.  
  
 Puede usar la cláusula `Skip` con la cláusula `Take` para devolver un intervalo de datos de cualquier segmento de una consulta. Para ello, pase el índice del primer elemento del intervalo a la cláusula `Skip` y el tamaño del intervalo a la cláusula `Take`.  
  
 Cuando se usa la cláusula `Skip` en una consulta, también es necesario asegurarse de que los resultados se devuelven en un orden que permita que la cláusula `Skip` omita los resultados deseados. Para obtener más información sobre cómo ordenar los resultados de una consulta, vea [cláusula order by](../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
 Puede usar la cláusula `SkipWhile` para especificar que solo se omitan determinados elementos, en función de una condición proporcionada.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se usa la cláusula `Skip` junto con la cláusula `Take` para devolver datos de una consulta en páginas. La función `GetCustomers` usa la cláusula `Skip` para omitir los clientes de la lista hasta el valor del índice de inicio proporcionado y usa la cláusula `Take` para devolver una página de clientes a partir de ese valor de índice.  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Consultas](../../../visual-basic/language-reference/queries/index.md)
- [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)
- [From (cláusula)](../../../visual-basic/language-reference/queries/from-clause.md)
- [Order By (cláusula)](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [Skip While (cláusula)](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [Take (cláusula)](../../../visual-basic/language-reference/queries/take-clause.md)
