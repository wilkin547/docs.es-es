---
title: Expresiones constantes
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 9d98a7be-b110-4edb-8eba-bed10f250b6d
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 328284ce07a0361dbfd25b0d765000b497156ff7
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="constant-expressions"></a><span data-ttu-id="93d98-102">Expresiones constantes</span><span class="sxs-lookup"><span data-stu-id="93d98-102">Constant Expressions</span></span>
<span data-ttu-id="93d98-103">Una expresión constante consta de un valor constante.</span><span class="sxs-lookup"><span data-stu-id="93d98-103">A constant expression consists of a constant value.</span></span> <span data-ttu-id="93d98-104">Los valores constantes se convierten directamente en expresiones constantes de árbol de comandos, sin sufrir ninguna traducción en el cliente.</span><span class="sxs-lookup"><span data-stu-id="93d98-104">Constant values are directly converted to constant command tree expressions, without any translation on the client.</span></span> <span data-ttu-id="93d98-105">Esto incluye a las expresiones que producen un valor constante.</span><span class="sxs-lookup"><span data-stu-id="93d98-105">This includes expressions that result in a constant value.</span></span> <span data-ttu-id="93d98-106">Por consiguiente, debe esperarse el comportamiento del origen de datos para todas las expresiones que impliquen constantes.</span><span class="sxs-lookup"><span data-stu-id="93d98-106">Therefore, data source behavior should be expected for all expressions involving constants.</span></span> <span data-ttu-id="93d98-107">Esto puede producir un comportamiento que difiera del comportamiento de CLR.</span><span class="sxs-lookup"><span data-stu-id="93d98-107">This can result in behavior that differs from CLR behavior.</span></span>  
  
 <span data-ttu-id="93d98-108">En el ejemplo siguiente se muestra una expresión constante que se evalúa en el servidor.</span><span class="sxs-lookup"><span data-stu-id="93d98-108">The following example shows a constant expression that is evaluated on the server.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#constantexpression)]
 [!code-vb[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#constantexpression)]  
  
 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]<span data-ttu-id="93d98-109"> no permite utilizar una clase de usuario como constante.</span><span class="sxs-lookup"><span data-stu-id="93d98-109"> does not support using a user class as a constant.</span></span> <span data-ttu-id="93d98-110">Sin embargo, una referencia de propiedad en una clase de usuario se considera una constante, se convertirá en una expresión constante de árbol de comandos y se ejecutará en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="93d98-110">However, a property reference on a user class is considered a constant, and will be converted to a command tree constant expression and executed on the data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93d98-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="93d98-111">See Also</span></span>  
 [<span data-ttu-id="93d98-112">Expresiones en consultas de LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="93d98-112">Expressions in LINQ to Entities Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)
