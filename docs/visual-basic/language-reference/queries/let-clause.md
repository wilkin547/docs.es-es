---
title: "Let (Cláusula, Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.QueryLet
helpviewer_keywords:
- queries [Visual Basic], Let
- Let clause [Visual Basic]
- Let statement [Visual Basic]
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 70e47517a62f58dcababd31c26277417b62eab66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="let-clause-visual-basic"></a><span data-ttu-id="20819-102">Let (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="20819-102">Let Clause (Visual Basic)</span></span>
<span data-ttu-id="20819-103">Calcula un valor y lo asigna a una nueva variable en la consulta.</span><span class="sxs-lookup"><span data-stu-id="20819-103">Computes a value and assigns it to a new variable within the query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20819-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="20819-104">Syntax</span></span>  
  
```  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="20819-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="20819-105">Parts</span></span>  
  
|<span data-ttu-id="20819-106">Término</span><span class="sxs-lookup"><span data-stu-id="20819-106">Term</span></span>|<span data-ttu-id="20819-107">Definición</span><span class="sxs-lookup"><span data-stu-id="20819-107">Definition</span></span>|  
|---|---|  
|`variable`|<span data-ttu-id="20819-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="20819-108">Required.</span></span> <span data-ttu-id="20819-109">Un alias que puede utilizarse para hacer referencia a los resultados de la expresión proporcionada.</span><span class="sxs-lookup"><span data-stu-id="20819-109">An alias that can be used to reference the results of the supplied expression.</span></span>|  
|`expression`|<span data-ttu-id="20819-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="20819-110">Required.</span></span> <span data-ttu-id="20819-111">Una expresión que se evalúa y se asigna a la variable especificada.</span><span class="sxs-lookup"><span data-stu-id="20819-111">An expression that will be evaluated and assigned to the specified variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20819-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="20819-112">Remarks</span></span>  
 <span data-ttu-id="20819-113">El `Let` cláusula permite calcular valores para cada resultado de la consulta y hacer referencia a ellos mediante un alias.</span><span class="sxs-lookup"><span data-stu-id="20819-113">The `Let` clause enables you to compute values for each query result and reference them by using an alias.</span></span> <span data-ttu-id="20819-114">El alias se puede usar en otras cláusulas, como la `Where` cláusula.</span><span class="sxs-lookup"><span data-stu-id="20819-114">The alias can be used in other clauses, such as the `Where` clause.</span></span> <span data-ttu-id="20819-115">El `Let` cláusula le permite crear una instrucción de consulta que es más fácil de leer porque puede especificar un alias para una cláusula de expresión incluida en la consulta y sustituya el alias cada vez que se utiliza la cláusula de expresión.</span><span class="sxs-lookup"><span data-stu-id="20819-115">The `Let` clause enables you to create a query statement that is easier to read because you can specify an alias for an expression clause included in the query and substitute the alias each time the expression clause is used.</span></span>  
  
 <span data-ttu-id="20819-116">Puede incluir cualquier número de `variable` y `expression` asignaciones en la `Let` cláusula.</span><span class="sxs-lookup"><span data-stu-id="20819-116">You can include any number of `variable` and `expression` assignments in the `Let` clause.</span></span> <span data-ttu-id="20819-117">Separe cada asignación con una coma (,).</span><span class="sxs-lookup"><span data-stu-id="20819-117">Separate each assignment with a comma (,).</span></span>  
  
## <a name="example"></a><span data-ttu-id="20819-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="20819-118">Example</span></span>  
 <span data-ttu-id="20819-119">El siguiente ejemplo de código utiliza el `Let` cláusula para calcular un 10 por ciento de descuento sobre los productos.</span><span class="sxs-lookup"><span data-stu-id="20819-119">The following code example uses the `Let` clause to compute a 10 percent discount on products.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#16](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/let-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="20819-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="20819-120">See Also</span></span>  
 [<span data-ttu-id="20819-121">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="20819-121">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="20819-122">Consultas</span><span class="sxs-lookup"><span data-stu-id="20819-122">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="20819-123">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="20819-123">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="20819-124">From (cláusula)</span><span class="sxs-lookup"><span data-stu-id="20819-124">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="20819-125">Where (cláusula)</span><span class="sxs-lookup"><span data-stu-id="20819-125">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
