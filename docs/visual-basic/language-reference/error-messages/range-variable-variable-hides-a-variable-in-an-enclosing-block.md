---
title: La variable de rango <variable> oculta una variable en un bloque de inclusión, una variable de rango definida anteriormente o una variable declarada de forma implícita en una expresión de consulta
ms.date: 07/20/2015
f1_keywords:
- bc36633
- vbc36633
helpviewer_keywords:
- BC36633
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
ms.openlocfilehash: 8d898d2d3c5f36177a6363c1a24940fe46de83d3
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55259889"
---
# <a name="range-variable-variable-hides-a-variable-in-an-enclosing-block-a-previously-defined-range-variable-or-an-implicitly-declared-variable-in-a-query-expression"></a>Variable de rango \<variable > oculta una variable en un bloque de inclusión, una variable de rango definida anteriormente o una variable declarada de forma implícita en una expresión de consulta
Un nombre de variable de rango especificado en un `Select`, `From`, `Aggregate`, o `Let` cláusula duplica el nombre de una variable de rango definido anteriormente en la consulta o el nombre de una variable que se declara implícitamente por la consulta, Por ejemplo, un nombre de campo o el nombre de una función de agregado.  
  
 **Identificador de error:** BC36633  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Asegúrese de que todas las variables de rango en un ámbito determinado de consulta tienen nombres únicos. Puede incluir una consulta entre paréntesis para asegurarse de que las consultas anidadas tienen un ámbito único.  
  
## <a name="see-also"></a>Vea también
- [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [From (cláusula)](../../../visual-basic/language-reference/queries/from-clause.md)
- [Let (cláusula)](../../../visual-basic/language-reference/queries/let-clause.md)
- [Aggregate (cláusula)](../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)
