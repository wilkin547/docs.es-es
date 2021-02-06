---
description: 'Más información sobre: cláusula Let (Visual Basic)'
title: Cláusula Let
ms.date: 07/20/2015
f1_keywords:
- vb.QueryLet
helpviewer_keywords:
- queries [Visual Basic], Let
- Let clause [Visual Basic]
- Let statement [Visual Basic]
ms.assetid: 981aa516-16eb-4c53-b1f1-5aa3e82f316e
ms.openlocfilehash: 88a7d96bb790a1e6ec5adfa4337c51f807930168
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99653646"
---
# <a name="let-clause-visual-basic"></a><span data-ttu-id="8e1e3-103">Let (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8e1e3-103">Let Clause (Visual Basic)</span></span>

<span data-ttu-id="8e1e3-104">Calcula un valor y lo asigna a una nueva variable dentro de la consulta.</span><span class="sxs-lookup"><span data-stu-id="8e1e3-104">Computes a value and assigns it to a new variable within the query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e1e3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8e1e3-105">Syntax</span></span>  
  
```vb  
Let variable = expression [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="8e1e3-106">Partes</span><span class="sxs-lookup"><span data-stu-id="8e1e3-106">Parts</span></span>  
  
|<span data-ttu-id="8e1e3-107">Término</span><span class="sxs-lookup"><span data-stu-id="8e1e3-107">Term</span></span>|<span data-ttu-id="8e1e3-108">Definición</span><span class="sxs-lookup"><span data-stu-id="8e1e3-108">Definition</span></span>|  
|---|---|  
|`variable`|<span data-ttu-id="8e1e3-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="8e1e3-109">Required.</span></span> <span data-ttu-id="8e1e3-110">Un alias que se puede usar para hacer referencia a los resultados de la expresión proporcionada.</span><span class="sxs-lookup"><span data-stu-id="8e1e3-110">An alias that can be used to reference the results of the supplied expression.</span></span>|  
|`expression`|<span data-ttu-id="8e1e3-111">Necesario.</span><span class="sxs-lookup"><span data-stu-id="8e1e3-111">Required.</span></span> <span data-ttu-id="8e1e3-112">Expresión que se evaluará y asignará a la variable especificada.</span><span class="sxs-lookup"><span data-stu-id="8e1e3-112">An expression that will be evaluated and assigned to the specified variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e1e3-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8e1e3-113">Remarks</span></span>  

 <span data-ttu-id="8e1e3-114">La `Let` cláusula permite calcular valores para cada resultado de la consulta y hacer referencia a ellos mediante un alias.</span><span class="sxs-lookup"><span data-stu-id="8e1e3-114">The `Let` clause enables you to compute values for each query result and reference them by using an alias.</span></span> <span data-ttu-id="8e1e3-115">El alias se puede usar en otras cláusulas, como la `Where` cláusula.</span><span class="sxs-lookup"><span data-stu-id="8e1e3-115">The alias can be used in other clauses, such as the `Where` clause.</span></span> <span data-ttu-id="8e1e3-116">La `Let` cláusula le permite crear una instrucción de consulta que es más fácil de leer, ya que puede especificar un alias para una cláusula Expression incluida en la consulta y sustituir el alias cada vez que se use la cláusula Expression.</span><span class="sxs-lookup"><span data-stu-id="8e1e3-116">The `Let` clause enables you to create a query statement that is easier to read because you can specify an alias for an expression clause included in the query and substitute the alias each time the expression clause is used.</span></span>  
  
 <span data-ttu-id="8e1e3-117">Puede incluir cualquier número de `variable` asignaciones y `expression` en la `Let` cláusula.</span><span class="sxs-lookup"><span data-stu-id="8e1e3-117">You can include any number of `variable` and `expression` assignments in the `Let` clause.</span></span> <span data-ttu-id="8e1e3-118">Separe cada asignación con una coma (,).</span><span class="sxs-lookup"><span data-stu-id="8e1e3-118">Separate each assignment with a comma (,).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e1e3-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8e1e3-119">Example</span></span>  

 <span data-ttu-id="8e1e3-120">En el ejemplo de código siguiente `Let` se usa la cláusula para calcular un 10% de descuento en productos.</span><span class="sxs-lookup"><span data-stu-id="8e1e3-120">The following code example uses the `Let` clause to compute a 10 percent discount on products.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#16)]  
  
## <a name="see-also"></a><span data-ttu-id="8e1e3-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e1e3-121">See also</span></span>

- [<span data-ttu-id="8e1e3-122">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8e1e3-122">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="8e1e3-123">Consultas</span><span class="sxs-lookup"><span data-stu-id="8e1e3-123">Queries</span></span>](index.md)
- [<span data-ttu-id="8e1e3-124">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="8e1e3-124">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="8e1e3-125">Cláusula From</span><span class="sxs-lookup"><span data-stu-id="8e1e3-125">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="8e1e3-126">Cláusula WHERE</span><span class="sxs-lookup"><span data-stu-id="8e1e3-126">Where Clause</span></span>](where-clause.md)
