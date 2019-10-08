---
title: Let (Cláusula, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryLet
helpviewer_keywords:
- queries [Visual Basic], Let
- Let clause [Visual Basic]
- Let statement [Visual Basic]
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
ms.openlocfilehash: 88166a040823cfefe623f672e556c364d652a7fc
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004728"
---
# <a name="let-clause-visual-basic"></a><span data-ttu-id="75ae1-102">Let (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75ae1-102">Let Clause (Visual Basic)</span></span>
<span data-ttu-id="75ae1-103">Calcula un valor y lo asigna a una nueva variable dentro de la consulta.</span><span class="sxs-lookup"><span data-stu-id="75ae1-103">Computes a value and assigns it to a new variable within the query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75ae1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="75ae1-104">Syntax</span></span>  
  
```vb  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="75ae1-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="75ae1-105">Parts</span></span>  
  
|<span data-ttu-id="75ae1-106">Término</span><span class="sxs-lookup"><span data-stu-id="75ae1-106">Term</span></span>|<span data-ttu-id="75ae1-107">Definición</span><span class="sxs-lookup"><span data-stu-id="75ae1-107">Definition</span></span>|  
|---|---|  
|`variable`|<span data-ttu-id="75ae1-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="75ae1-108">Required.</span></span> <span data-ttu-id="75ae1-109">Un alias que se puede usar para hacer referencia a los resultados de la expresión proporcionada.</span><span class="sxs-lookup"><span data-stu-id="75ae1-109">An alias that can be used to reference the results of the supplied expression.</span></span>|  
|`expression`|<span data-ttu-id="75ae1-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="75ae1-110">Required.</span></span> <span data-ttu-id="75ae1-111">Expresión que se evaluará y asignará a la variable especificada.</span><span class="sxs-lookup"><span data-stu-id="75ae1-111">An expression that will be evaluated and assigned to the specified variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75ae1-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="75ae1-112">Remarks</span></span>  
 <span data-ttu-id="75ae1-113">La cláusula `Let` permite calcular valores para cada resultado de la consulta y hacer referencia a ellos mediante un alias.</span><span class="sxs-lookup"><span data-stu-id="75ae1-113">The `Let` clause enables you to compute values for each query result and reference them by using an alias.</span></span> <span data-ttu-id="75ae1-114">El alias se puede usar en otras cláusulas, como la cláusula `Where`.</span><span class="sxs-lookup"><span data-stu-id="75ae1-114">The alias can be used in other clauses, such as the `Where` clause.</span></span> <span data-ttu-id="75ae1-115">La cláusula `Let` le permite crear una instrucción de consulta que es más fácil de leer, ya que puede especificar un alias para una cláusula Expression incluida en la consulta y sustituir el alias cada vez que se use la cláusula Expression.</span><span class="sxs-lookup"><span data-stu-id="75ae1-115">The `Let` clause enables you to create a query statement that is easier to read because you can specify an alias for an expression clause included in the query and substitute the alias each time the expression clause is used.</span></span>  
  
 <span data-ttu-id="75ae1-116">Puede incluir cualquier número de asignaciones `variable` y `expression` en la cláusula `Let`.</span><span class="sxs-lookup"><span data-stu-id="75ae1-116">You can include any number of `variable` and `expression` assignments in the `Let` clause.</span></span> <span data-ttu-id="75ae1-117">Separe cada asignación con una coma (,).</span><span class="sxs-lookup"><span data-stu-id="75ae1-117">Separate each assignment with a comma (,).</span></span>  
  
## <a name="example"></a><span data-ttu-id="75ae1-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="75ae1-118">Example</span></span>  
 <span data-ttu-id="75ae1-119">En el ejemplo de código siguiente se usa la cláusula `Let` para calcular un 10% de descuento en productos.</span><span class="sxs-lookup"><span data-stu-id="75ae1-119">The following code example uses the `Let` clause to compute a 10 percent discount on products.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#16)]  
  
## <a name="see-also"></a><span data-ttu-id="75ae1-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="75ae1-120">See also</span></span>

- [<span data-ttu-id="75ae1-121">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="75ae1-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="75ae1-122">Consultas</span><span class="sxs-lookup"><span data-stu-id="75ae1-122">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="75ae1-123">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="75ae1-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="75ae1-124">From (cláusula)</span><span class="sxs-lookup"><span data-stu-id="75ae1-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="75ae1-125">Where (cláusula)</span><span class="sxs-lookup"><span data-stu-id="75ae1-125">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
