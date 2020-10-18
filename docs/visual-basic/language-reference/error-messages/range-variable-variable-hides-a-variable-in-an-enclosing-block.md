---
title: La variable de rango <variable> oculta una variable en un bloque de inclusión, una variable de rango definida anteriormente o una variable declarada de forma implícita en una expresión de consulta
ms.date: 07/20/2015
f1_keywords:
- bc36633
- vbc36633
helpviewer_keywords:
- BC36633
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
ms.openlocfilehash: 90fed3dd27f18fe87c326cc36dfb774822fc4b21
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162354"
---
# <a name="bc36633-range-variable-variable-hides-a-variable-in-an-enclosing-block-a-previously-defined-range-variable-or-an-implicitly-declared-variable-in-a-query-expression"></a><span data-ttu-id="a899f-102">BC36633: la variable \<variable> de rango oculta una variable en un bloque de inclusión, una variable de rango definida previamente o una variable declarada implícitamente en una expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="a899f-102">BC36633: Range variable \<variable> hides a variable in an enclosing block, a previously defined range variable, or an implicitly declared variable in a query expression</span></span>

<span data-ttu-id="a899f-103">Un nombre de variable de rango especificado en una `Select` `From` cláusula,, `Aggregate` o `Let` duplica el nombre de una variable de rango ya especificada previamente en la consulta, o el nombre de una variable declarada implícitamente por la consulta, como un nombre de campo o el nombre de una función de agregado.</span><span class="sxs-lookup"><span data-stu-id="a899f-103">A range variable name specified in a `Select`, `From`, `Aggregate`, or `Let` clause duplicates the name of a range variable already specified previously in the query, or the name of a variable that is implicitly declared by the query, such as a field name or the name of an aggregate function.</span></span>

 <span data-ttu-id="a899f-104">**Identificador de error:** BC36633</span><span class="sxs-lookup"><span data-stu-id="a899f-104">**Error ID:** BC36633</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="a899f-105">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="a899f-105">To correct this error</span></span>

- <span data-ttu-id="a899f-106">Asegúrese de que todas las variables de rango de un ámbito de consulta determinado tienen nombres únicos.</span><span class="sxs-lookup"><span data-stu-id="a899f-106">Ensure that all range variables in a particular query scope have unique names.</span></span> <span data-ttu-id="a899f-107">Puede incluir una consulta entre paréntesis para asegurarse de que las consultas anidadas tienen un ámbito único.</span><span class="sxs-lookup"><span data-stu-id="a899f-107">You can enclose a query in parentheses to ensure that nested queries have a unique scope.</span></span>

## <a name="see-also"></a><span data-ttu-id="a899f-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="a899f-108">See also</span></span>

- [<span data-ttu-id="a899f-109">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a899f-109">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="a899f-110">Cláusula FROM</span><span class="sxs-lookup"><span data-stu-id="a899f-110">From Clause</span></span>](../queries/from-clause.md)
- [<span data-ttu-id="a899f-111">Let (cláusula)</span><span class="sxs-lookup"><span data-stu-id="a899f-111">Let Clause</span></span>](../queries/let-clause.md)
- [<span data-ttu-id="a899f-112">Aggregate Clause</span><span class="sxs-lookup"><span data-stu-id="a899f-112">Aggregate Clause</span></span>](../queries/aggregate-clause.md)
- [<span data-ttu-id="a899f-113">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="a899f-113">Select Clause</span></span>](../queries/select-clause.md)
