---
description: 'Más información sobre: expresiones de inicialización'
title: Expresiones de inicialización
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 98daef1f-15d4-483e-985c-d78ea3abe8c8
ms.openlocfilehash: 02f2ea6953291641516b1daffbb2b75931ffb3cf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99748562"
---
# <a name="initialization-expressions"></a><span data-ttu-id="e32c2-103">Expresiones de inicialización</span><span class="sxs-lookup"><span data-stu-id="e32c2-103">Initialization Expressions</span></span>

<span data-ttu-id="e32c2-104">Una expresión de inicialización inicializa un objeto nuevo.</span><span class="sxs-lookup"><span data-stu-id="e32c2-104">An initialization expression initializes a new object.</span></span> <span data-ttu-id="e32c2-105">Se admiten la mayoría de las expresiones de inicialización, incluso las de Visual Basic 9.0 y C# 3.0.</span><span class="sxs-lookup"><span data-stu-id="e32c2-105">Most initialization expressions are supported, including most new C# 3.0 and Visual Basic 9.0 initialization expressions.</span></span> <span data-ttu-id="e32c2-106">Los tipos siguientes pueden ser inicializados y devueltos por una consulta de LINQ to Entities:</span><span class="sxs-lookup"><span data-stu-id="e32c2-106">The following types can be initialized and returned by a LINQ to Entities query:</span></span>  
  
- <span data-ttu-id="e32c2-107">Una colección de cero o más objetos entidad con tipo o una proyección de tipos complejos definidos en el modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="e32c2-107">A collection of zero or more typed entity objects or a projection of complex types that are defined in the conceptual model.</span></span>  
  
- <span data-ttu-id="e32c2-108">Tipos CLR admitidos por el Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="e32c2-108">CLR types supported by the Entity Framework.</span></span>
  
- <span data-ttu-id="e32c2-109">Colecciones insertadas.</span><span class="sxs-lookup"><span data-stu-id="e32c2-109">Inline collections.</span></span>  
  
- <span data-ttu-id="e32c2-110">Tipos anónimos.</span><span class="sxs-lookup"><span data-stu-id="e32c2-110">Anonymous types.</span></span>  
  
 <span data-ttu-id="e32c2-111">En el ejemplo siguiente se muestra la inicialización de tipos anónimos en sintaxis de expresiones de consulta:</span><span class="sxs-lookup"><span data-stu-id="e32c2-111">Anonymous type initialization is shown in the following example in query expression syntax:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#AnonymousTypeInitialization](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#anonymoustypeinitialization)]
 [!code-vb[DP L2E Conceptual Examples#AnonymousTypeInitialization](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#anonymoustypeinitialization)]  
  
 <span data-ttu-id="e32c2-112">El ejemplo siguiente de sintaxis de la consulta basada en métodos muestra la inicialización de los tipos anónimos:</span><span class="sxs-lookup"><span data-stu-id="e32c2-112">The following example in method-based query syntax shows anonymous type initialization:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#AnonymousTypeInitialization_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#anonymoustypeinitialization_mq)]
 [!code-vb[DP L2E Conceptual Examples#AnonymousTypeInitialization_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#anonymoustypeinitialization_mq)]  
  
 <span data-ttu-id="e32c2-113">También se admite la inicialización de clases definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="e32c2-113">User-defined class initialization is also supported.</span></span> <span data-ttu-id="e32c2-114">Se admite el patrón de inicialización de C# 3.0 y Visual Basic 9.0, y se supone que el captador y el establecedor de la propiedad son simétricos.</span><span class="sxs-lookup"><span data-stu-id="e32c2-114">The C# 3.0 and Visual Basic 9.0 initialization pattern is supported and assumes that the property getter and setter are symmetric.</span></span> <span data-ttu-id="e32c2-115">El ejemplo siguiente de la sintaxis de las expresiones de consulta muestra una clase personalizada que se inicializa en la consulta:</span><span class="sxs-lookup"><span data-stu-id="e32c2-115">The following example in query expression syntax shows a custom class being initialized in the query:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#MyOrder](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#myorder)]
 [!code-vb[DP L2E Conceptual Examples#MyOrder](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#myorder)]  
  
 [!code-csharp[DP L2E Conceptual Examples#TypeInitialization](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#typeinitialization)]
 [!code-vb[DP L2E Conceptual Examples#TypeInitialization](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#typeinitialization)]  
  
 <span data-ttu-id="e32c2-116">El ejemplo siguiente de la sintaxis de las consultas basadas en métodos muestra una clase personalizada que se inicializa en la consulta:</span><span class="sxs-lookup"><span data-stu-id="e32c2-116">The following example in method-based query syntax shows a custom class being initialized in the query:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#TypeInitialization_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#typeinitialization_mq)]
 [!code-vb[DP L2E Conceptual Examples#TypeInitialization_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#typeinitialization_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="e32c2-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="e32c2-117">See also</span></span>

- [<span data-ttu-id="e32c2-118">Expresiones en consultas de LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="e32c2-118">Expressions in LINQ to Entities Queries</span></span>](expressions-in-linq-to-entities-queries.md)
