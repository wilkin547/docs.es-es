---
title: Expresiones de inicialización
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 98daef1f-15d4-483e-985c-d78ea3abe8c8
ms.openlocfilehash: 78bafcad0a0f34c74ea58f107621ad145c1b405b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64631526"
---
# <a name="initialization-expressions"></a><span data-ttu-id="8aad2-102">Expresiones de inicialización</span><span class="sxs-lookup"><span data-stu-id="8aad2-102">Initialization Expressions</span></span>
<span data-ttu-id="8aad2-103">Una expresión de inicialización inicializa un objeto nuevo.</span><span class="sxs-lookup"><span data-stu-id="8aad2-103">An initialization expression initializes a new object.</span></span> <span data-ttu-id="8aad2-104">Se admiten la mayoría de las expresiones de inicialización, incluso las de Visual Basic 9.0 y C# 3.0.</span><span class="sxs-lookup"><span data-stu-id="8aad2-104">Most initialization expressions are supported, including most new C# 3.0 and Visual Basic 9.0 initialization expressions.</span></span> <span data-ttu-id="8aad2-105">Los tipos siguientes pueden ser inicializados y devueltos por una consulta de LINQ to Entities:</span><span class="sxs-lookup"><span data-stu-id="8aad2-105">The following types can be initialized and returned by a LINQ to Entities query:</span></span>  
  
- <span data-ttu-id="8aad2-106">Una colección de cero o más objetos entidad con tipo o una proyección de tipos complejos definidos en el modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="8aad2-106">A collection of zero or more typed entity objects or a projection of complex types that are defined in the conceptual model.</span></span>  
  
- <span data-ttu-id="8aad2-107">Tipos CLR admitidos por [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8aad2-107">CLR types supported by the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span>  
  
- <span data-ttu-id="8aad2-108">Colecciones insertadas.</span><span class="sxs-lookup"><span data-stu-id="8aad2-108">Inline collections.</span></span>  
  
- <span data-ttu-id="8aad2-109">Tipos anónimos.</span><span class="sxs-lookup"><span data-stu-id="8aad2-109">Anonymous types.</span></span>  
  
 <span data-ttu-id="8aad2-110">En el ejemplo siguiente se muestra la inicialización de tipos anónimos en sintaxis de expresiones de consulta:</span><span class="sxs-lookup"><span data-stu-id="8aad2-110">Anonymous type initialization is shown in the following example in query expression syntax:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#AnonymousTypeInitialization](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#anonymoustypeinitialization)]
 [!code-vb[DP L2E Conceptual Examples#AnonymousTypeInitialization](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#anonymoustypeinitialization)]  
  
 <span data-ttu-id="8aad2-111">El ejemplo siguiente de sintaxis de la consulta basada en métodos muestra la inicialización de los tipos anónimos:</span><span class="sxs-lookup"><span data-stu-id="8aad2-111">The following example in method-based query syntax shows anonymous type initialization:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#AnonymousTypeInitialization_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#anonymoustypeinitialization_mq)]
 [!code-vb[DP L2E Conceptual Examples#AnonymousTypeInitialization_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#anonymoustypeinitialization_mq)]  
  
 <span data-ttu-id="8aad2-112">También se admite la inicialización de clases definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="8aad2-112">User-defined class initialization is also supported.</span></span> <span data-ttu-id="8aad2-113">Se admite el patrón de inicialización de C# 3.0 y Visual Basic 9.0, y se supone que el captador y el establecedor de la propiedad son simétricos.</span><span class="sxs-lookup"><span data-stu-id="8aad2-113">The C# 3.0 and Visual Basic 9.0 initialization pattern is supported and assumes that the property getter and setter are symmetric.</span></span> <span data-ttu-id="8aad2-114">El ejemplo siguiente de la sintaxis de las expresiones de consulta muestra una clase personalizada que se inicializa en la consulta:</span><span class="sxs-lookup"><span data-stu-id="8aad2-114">The following example in query expression syntax shows a custom class being initialized in the query:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#MyOrder](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#myorder)]
 [!code-vb[DP L2E Conceptual Examples#MyOrder](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#myorder)]  
  
 [!code-csharp[DP L2E Conceptual Examples#TypeInitialization](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#typeinitialization)]
 [!code-vb[DP L2E Conceptual Examples#TypeInitialization](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#typeinitialization)]  
  
 <span data-ttu-id="8aad2-115">El ejemplo siguiente de la sintaxis de las consultas basadas en métodos muestra una clase personalizada que se inicializa en la consulta:</span><span class="sxs-lookup"><span data-stu-id="8aad2-115">The following example in method-based query syntax shows a custom class being initialized in the query:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#TypeInitialization_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#typeinitialization_mq)]
 [!code-vb[DP L2E Conceptual Examples#TypeInitialization_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#typeinitialization_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="8aad2-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="8aad2-116">See also</span></span>

- [<span data-ttu-id="8aad2-117">Expresiones en consultas de LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="8aad2-117">Expressions in LINQ to Entities Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)
