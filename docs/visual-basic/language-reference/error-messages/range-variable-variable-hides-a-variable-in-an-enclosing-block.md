---
title: La variable de rango <variable> oculta una variable en un bloque de inclusión, una variable de rango definida anteriormente o una variable declarada de forma implícita en una expresión de consulta
ms.date: 07/20/2015
f1_keywords:
- bc36633
- vbc36633
helpviewer_keywords:
- BC36633
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
ms.openlocfilehash: e31f728de228bea743f6c7b5cbfef3cd73367262
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822718"
---
# <a name="range-variable-variable-hides-a-variable-in-an-enclosing-block-a-previously-defined-range-variable-or-an-implicitly-declared-variable-in-a-query-expression"></a><span data-ttu-id="199b9-102">Variable de rango \<variable > oculta una variable en un bloque de inclusión, una variable de rango definida anteriormente o una variable declarada de forma implícita en una expresión de consulta</span><span class="sxs-lookup"><span data-stu-id="199b9-102">Range variable \<variable> hides a variable in an enclosing block, a previously defined range variable, or an implicitly declared variable in a query expression</span></span>
<span data-ttu-id="199b9-103">Un nombre de variable de rango especificado en un `Select`, `From`, `Aggregate`, o `Let` cláusula duplica el nombre de una variable de rango definido anteriormente en la consulta o el nombre de una variable que se declara implícitamente por la consulta, Por ejemplo, un nombre de campo o el nombre de una función de agregado.</span><span class="sxs-lookup"><span data-stu-id="199b9-103">A range variable name specified in a `Select`, `From`, `Aggregate`, or `Let` clause duplicates the name of a range variable already specified previously in the query, or the name of a variable that is implicitly declared by the query, such as a field name or the name of an aggregate function.</span></span>  
  
 <span data-ttu-id="199b9-104">**Identificador de error:** BC36633</span><span class="sxs-lookup"><span data-stu-id="199b9-104">**Error ID:** BC36633</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="199b9-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="199b9-105">To correct this error</span></span>  
  
-   <span data-ttu-id="199b9-106">Asegúrese de que todas las variables de rango en un ámbito determinado de consulta tienen nombres únicos.</span><span class="sxs-lookup"><span data-stu-id="199b9-106">Ensure that all range variables in a particular query scope have unique names.</span></span> <span data-ttu-id="199b9-107">Puede incluir una consulta entre paréntesis para asegurarse de que las consultas anidadas tienen un ámbito único.</span><span class="sxs-lookup"><span data-stu-id="199b9-107">You can enclose a query in parentheses to ensure that nested queries have a unique scope.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="199b9-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="199b9-108">See also</span></span>

- [<span data-ttu-id="199b9-109">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="199b9-109">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="199b9-110">From (cláusula)</span><span class="sxs-lookup"><span data-stu-id="199b9-110">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="199b9-111">Let (cláusula)</span><span class="sxs-lookup"><span data-stu-id="199b9-111">Let Clause</span></span>](../../../visual-basic/language-reference/queries/let-clause.md)
- [<span data-ttu-id="199b9-112">Aggregate (cláusula)</span><span class="sxs-lookup"><span data-stu-id="199b9-112">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="199b9-113">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="199b9-113">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
