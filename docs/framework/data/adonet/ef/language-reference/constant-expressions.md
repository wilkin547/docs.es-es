---
description: 'Más información acerca de: expresiones constantes'
title: Expresiones constantes
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9d98a7be-b110-4edb-8eba-bed10f250b6d
ms.openlocfilehash: 3c040918df4af6a0302d2435e3564e395044108e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724835"
---
# <a name="constant-expressions"></a><span data-ttu-id="2d983-103">Expresiones constantes</span><span class="sxs-lookup"><span data-stu-id="2d983-103">Constant Expressions</span></span>

<span data-ttu-id="2d983-104">Una expresión constante consta de un valor constante.</span><span class="sxs-lookup"><span data-stu-id="2d983-104">A constant expression consists of a constant value.</span></span> <span data-ttu-id="2d983-105">Los valores constantes se convierten directamente en expresiones constantes de árbol de comandos, sin sufrir ninguna traducción en el cliente.</span><span class="sxs-lookup"><span data-stu-id="2d983-105">Constant values are directly converted to constant command tree expressions, without any translation on the client.</span></span> <span data-ttu-id="2d983-106">Esto incluye a las expresiones que producen un valor constante.</span><span class="sxs-lookup"><span data-stu-id="2d983-106">This includes expressions that result in a constant value.</span></span> <span data-ttu-id="2d983-107">Por consiguiente, debe esperarse el comportamiento del origen de datos para todas las expresiones que impliquen constantes.</span><span class="sxs-lookup"><span data-stu-id="2d983-107">Therefore, data source behavior should be expected for all expressions involving constants.</span></span> <span data-ttu-id="2d983-108">Esto puede producir un comportamiento que difiera del comportamiento de CLR.</span><span class="sxs-lookup"><span data-stu-id="2d983-108">This can result in behavior that differs from CLR behavior.</span></span>  
  
 <span data-ttu-id="2d983-109">En el ejemplo siguiente se muestra una expresión constante que se evalúa en el servidor.</span><span class="sxs-lookup"><span data-stu-id="2d983-109">The following example shows a constant expression that is evaluated on the server.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#constantexpression)]
 [!code-vb[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#constantexpression)]  
  
 <span data-ttu-id="2d983-110">LINQ to Entities no admite el uso de una clase de usuario como constante.</span><span class="sxs-lookup"><span data-stu-id="2d983-110">LINQ to Entities does not support using a user class as a constant.</span></span> <span data-ttu-id="2d983-111">Sin embargo, una referencia de propiedad en una clase de usuario se considera una constante, se convertirá en una expresión constante de árbol de comandos y se ejecutará en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="2d983-111">However, a property reference on a user class is considered a constant, and will be converted to a command tree constant expression and executed on the data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d983-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d983-112">See also</span></span>

- [<span data-ttu-id="2d983-113">Expresiones en consultas de LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="2d983-113">Expressions in LINQ to Entities Queries</span></span>](expressions-in-linq-to-entities-queries.md)
