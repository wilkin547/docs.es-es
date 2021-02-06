---
description: 'Más información acerca de: cláusula SKIP (Visual Basic)'
title: Cláusula Skip
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkip
helpviewer_keywords:
- queries [Visual Basic], Skip
- Skip statement [Visual Basic]
- Skip clause [Visual Basic]
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
ms.openlocfilehash: 6af702f65a724ea8c3d5a6122fb5f7a0ed5f6755
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99653555"
---
# <a name="skip-clause-visual-basic"></a>Skip (Cláusula, Visual Basic)

Omite un número especificado de elementos de una colección y, a continuación, devuelve los elementos restantes.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Skip count  
```  
  
## <a name="parts"></a>Partes  

 `count`  
 Necesario. Un valor o una expresión que se evalúa como el número de elementos de la secuencia que se va a omitir.  
  
## <a name="remarks"></a>Observaciones  

 La `Skip` cláusula hace que una consulta omita los elementos al principio de una lista de resultados y devuelva los elementos restantes. El número de elementos que se van a omitir se identifica mediante el `count` parámetro.  
  
 Puede usar la `Skip` cláusula con la `Take` cláusula para devolver un intervalo de datos de cualquier segmento de una consulta. Para ello, pase el índice del primer elemento del intervalo a la `Skip` cláusula y el tamaño del intervalo a la `Take` cláusula.  
  
 Al utilizar la `Skip` cláusula en una consulta, puede que también tenga que asegurarse de que los resultados se devuelven en un orden que permita que la `Skip` cláusula omita los resultados deseados. Para obtener más información sobre cómo ordenar los resultados de una consulta, vea [cláusula order by](order-by-clause.md).  
  
 Puede usar la `SkipWhile` cláusula para especificar que solo se omitan determinados elementos, en función de una condición proporcionada.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo de código siguiente `Skip` se usa la cláusula junto con la `Take` cláusula para devolver datos de una consulta en páginas. La `GetCustomers` función usa la `Skip` cláusula para omitir los clientes de la lista hasta el valor del índice de inicio proporcionado y usa la `Take` cláusula para devolver una página de clientes a partir de ese valor de índice.  
  
 [!code-vb[VbSimpleQuerySamples#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Introducción a LINQ en Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Consultas](index.md)
- [Select (cláusula)](select-clause.md)
- [Cláusula From](from-clause.md)
- [Cláusula order by](order-by-clause.md)
- [Cláusula Skip While](skip-while-clause.md)
- [Cláusula Take](take-clause.md)
