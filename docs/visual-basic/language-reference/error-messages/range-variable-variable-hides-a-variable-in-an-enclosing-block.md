---
description: 'Más información sobre: BC36633: la variable <variable> de rango oculta una variable en un bloque de inclusión, una variable de rango definida previamente o una variable declarada implícitamente en una expresión de consulta'
title: La variable de rango <variable> oculta una variable en un bloque de inclusión, una variable de rango definida anteriormente o una variable declarada de forma implícita en una expresión de consulta
ms.date: 07/20/2015
f1_keywords:
- bc36633
- vbc36633
helpviewer_keywords:
- BC36633
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
ms.openlocfilehash: f8e5c109274af9c00963e8a9f18384a299d17a4a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792081"
---
# <a name="bc36633-range-variable-variable-hides-a-variable-in-an-enclosing-block-a-previously-defined-range-variable-or-an-implicitly-declared-variable-in-a-query-expression"></a><span data-ttu-id="a9bf2-103">BC36633: la variable \<variable> de rango oculta una variable en un bloque de inclusión, una variable de rango definida previamente o una variable declarada implícitamente en una expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="a9bf2-103">BC36633: Range variable \<variable> hides a variable in an enclosing block, a previously defined range variable, or an implicitly declared variable in a query expression</span></span>

<span data-ttu-id="a9bf2-104">Un nombre de variable de rango especificado en una `Select` `From` cláusula,, `Aggregate` o `Let` duplica el nombre de una variable de rango ya especificada previamente en la consulta, o el nombre de una variable declarada implícitamente por la consulta, como un nombre de campo o el nombre de una función de agregado.</span><span class="sxs-lookup"><span data-stu-id="a9bf2-104">A range variable name specified in a `Select`, `From`, `Aggregate`, or `Let` clause duplicates the name of a range variable already specified previously in the query, or the name of a variable that is implicitly declared by the query, such as a field name or the name of an aggregate function.</span></span>

 <span data-ttu-id="a9bf2-105">**Identificador de error:** BC36633</span><span class="sxs-lookup"><span data-stu-id="a9bf2-105">**Error ID:** BC36633</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="a9bf2-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="a9bf2-106">To correct this error</span></span>

- <span data-ttu-id="a9bf2-107">Asegúrese de que todas las variables de rango de un ámbito de consulta determinado tienen nombres únicos.</span><span class="sxs-lookup"><span data-stu-id="a9bf2-107">Ensure that all range variables in a particular query scope have unique names.</span></span> <span data-ttu-id="a9bf2-108">Puede incluir una consulta entre paréntesis para asegurarse de que las consultas anidadas tienen un ámbito único.</span><span class="sxs-lookup"><span data-stu-id="a9bf2-108">You can enclose a query in parentheses to ensure that nested queries have a unique scope.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9bf2-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9bf2-109">See also</span></span>

- [<span data-ttu-id="a9bf2-110">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a9bf2-110">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="a9bf2-111">Cláusula From</span><span class="sxs-lookup"><span data-stu-id="a9bf2-111">From Clause</span></span>](../queries/from-clause.md)
- [<span data-ttu-id="a9bf2-112">Cláusula Let</span><span class="sxs-lookup"><span data-stu-id="a9bf2-112">Let Clause</span></span>](../queries/let-clause.md)
- [<span data-ttu-id="a9bf2-113">Aggregate Clause</span><span class="sxs-lookup"><span data-stu-id="a9bf2-113">Aggregate Clause</span></span>](../queries/aggregate-clause.md)
- [<span data-ttu-id="a9bf2-114">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="a9bf2-114">Select Clause</span></span>](../queries/select-clause.md)
