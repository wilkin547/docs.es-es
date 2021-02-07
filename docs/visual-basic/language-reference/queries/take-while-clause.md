---
description: 'Más información sobre: Take while (cláusula, Visual Basic)'
title: Cláusula Take While
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
ms.openlocfilehash: a413223d4a85670c66f71e24addb92ae4d38a4a9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99719713"
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
  
## <a name="see-also"></a>Vea también

- [Introducción a LINQ en Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Consultas](index.md)
- [Select (cláusula)](select-clause.md)
- [Cláusula From](from-clause.md)
- [Cláusula Take](take-clause.md)
- [Cláusula Skip While](skip-while-clause.md)
- [Cláusula WHERE](where-clause.md)
