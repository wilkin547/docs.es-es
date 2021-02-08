---
description: 'Más información acerca de: cláusula SKIP while (Visual Basic)'
title: Cláusula Skip While
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
ms.openlocfilehash: 6f2785fde1a62c10c914904ccba51510dbb1a041
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99773854"
---
# <a name="skip-while-clause-visual-basic"></a>Skip While (Cláusula, Visual Basic)

Omite los elementos de una colección siempre que el valor de una condición especificada sea `true` y, a continuación, devuelve los elementos restantes.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Skip While expression  
```  
  
## <a name="parts"></a>Partes  
  
|Término|Definición|  
|---|---|  
|`expression`|Obligatorio. Expresión que representa una condición de la que se van a probar los elementos. La expresión debe devolver un `Boolean` valor o un equivalente funcional, como un `Integer` que se va a evaluar como `Boolean` .|  
  
## <a name="remarks"></a>Observaciones  

 La `Skip While` cláusula omite los elementos desde el principio del resultado de una consulta hasta que el proporcionado `expression` devuelve `false` . Después `expression` `false` de que devuelva, la consulta devuelve todos los elementos restantes. `expression`Se omite para los resultados restantes.  
  
 La `Skip While` cláusula difiere de la `Where` cláusula en que la `Where` cláusula se puede utilizar para excluir todos los elementos de una consulta que no cumplan una condición determinada. La `Skip While` cláusula excluye los elementos solo hasta la primera vez que la condición no se cumple. La `Skip While` cláusula es muy útil cuando se trabaja con un resultado de consulta ordenado.  
  
 Puede omitir un número específico de resultados desde el principio del resultado de una consulta mediante la `Skip` cláusula.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo de código siguiente `Skip While` se usa la cláusula para omitir los resultados hasta que se encuentre el primer cliente del Estados Unidos.  
  
 [!code-vb[VbSimpleQuerySamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#3)]  
  
## <a name="see-also"></a>Vea también

- [Introducción a LINQ en Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Consultas](index.md)
- [Select (cláusula)](select-clause.md)
- [Cláusula From](from-clause.md)
- [Cláusula Skip](skip-clause.md)
- [Cláusula Take While](take-while-clause.md)
- [Cláusula WHERE](where-clause.md)
