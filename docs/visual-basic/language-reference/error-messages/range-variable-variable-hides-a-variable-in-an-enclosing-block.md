---
title: Variable de rango &lt;variable&gt; oculta una variable en un bloque de inclusión, una variable de rango definida previamente o una variable declarada de forma implícita en una expresión de consulta
ms.date: 07/20/2015
f1_keywords:
- bc36633
- vbc36633
helpviewer_keywords:
- BC36633
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
ms.openlocfilehash: f02533cf7cb79c34e5bb5a6d445aaef7ab0e86da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593131"
---
# <a name="range-variable-ltvariablegt-hides-a-variable-in-an-enclosing-block-a-previously-defined-range-variable-or-an-implicitly-declared-variable-in-a-query-expression"></a>Variable de rango &lt;variable&gt; oculta una variable en un bloque de inclusión, una variable de rango definida previamente o una variable declarada de forma implícita en una expresión de consulta
Un nombre de variable de rango especificado en un `Select`, `From`, `Aggregate`, o `Let` cláusula duplica el nombre de una variable de rango definido anteriormente en la consulta o el nombre de una variable que se declara implícitamente por la consulta, Por ejemplo, un nombre de campo o el nombre de una función de agregado.  
  
 **Id. de error:** BC36633  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Asegúrese de que todas las variables de rango de un ámbito de consulta determinada tienen nombres únicos. Puede agregar una consulta paréntesis para asegurarse de que las consultas anidadas tienen un único ámbito.  
  
## <a name="see-also"></a>Vea también  
 [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [From (cláusula)](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Let (cláusula)](../../../visual-basic/language-reference/queries/let-clause.md)  
 [Aggregate (cláusula)](../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)
