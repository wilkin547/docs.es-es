---
title: Cláusula Take While
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
ms.openlocfilehash: 4b6133efdbd9c46ab85201ad454671e5538b6a81
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359585"
---
# <a name="take-while-clause-visual-basic"></a>Take While (Cláusula, Visual Basic)
Incluye los elementos de una colección siempre que el valor de una condición especificada sea `true` y, a continuación, omite los elementos restantes.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Take While expression  
```  
  
## <a name="parts"></a>Partes  
  
|Término|Definición|  
|---|---|  
|`expression`|Obligatorio. Expresión que representa una condición de la que se van a probar los elementos. La expresión debe devolver un `Boolean` valor o un equivalente funcional, como un `Integer` que se va a evaluar como `Boolean` .|  
  
## <a name="remarks"></a>Observaciones  
 La `Take While` cláusula incluye elementos desde el principio del resultado de una consulta hasta que el proporcionado `expression` devuelve `false` . Una vez que `expression` devuelve `false` , la consulta omitirá todos los elementos restantes. `expression`Se omite para los resultados restantes.  
  
 La `Take While` cláusula difiere de la `Where` cláusula en que la `Where` cláusula se puede utilizar para incluir todos los elementos de una consulta que cumplan una condición determinada. La `Take While` cláusula solo incluye elementos hasta la primera vez que la condición no se cumple. La `Take While` cláusula es muy útil cuando se trabaja con un resultado de consulta ordenado.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente `Take While` se usa la cláusula para recuperar los resultados hasta que se encuentre el primer cliente sin ningún pedido.  
  
 [!code-vb[VbSimpleQuerySamples#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#2)]  
  
## <a name="see-also"></a>Consulte también

- [Introducción a LINQ en Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Consultas](index.md)
- [Select (cláusula)](select-clause.md)
- [Cláusula FROM](from-clause.md)
- [Cláusula Take](take-clause.md)
- [Cláusula Skip While](skip-while-clause.md)
- [Cláusula WHERE](where-clause.md)
