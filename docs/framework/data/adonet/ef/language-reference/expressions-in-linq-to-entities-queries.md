---
title: Expresiones en consultas de LINQ to Entities
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
ms.assetid: d70b502f-6a15-4120-b4fe-500b173ad9cc
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 6c1460aa78e112d29a4c500c54661b63de03e953
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="expressions-in-linq-to-entities-queries"></a><span data-ttu-id="28ca1-102">Expresiones en consultas de LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="28ca1-102">Expressions in LINQ to Entities Queries</span></span>
<span data-ttu-id="28ca1-103">Una expresión es un fragmento de código que se puede evaluar como un valor, objeto, método o espacio de nombres único.</span><span class="sxs-lookup"><span data-stu-id="28ca1-103">An expression is a fragment of code that can be evaluated to a single value, object, method, or namespace.</span></span> <span data-ttu-id="28ca1-104">Las expresiones pueden contener un valor literal, una llamada a un método, un operador y sus operandos, o un nombre simple.</span><span class="sxs-lookup"><span data-stu-id="28ca1-104">Expressions can contain a literal value, a method call, an operator and its operands, or a simple name.</span></span> <span data-ttu-id="28ca1-105">Los nombres simples pueden ser el nombre de una variable, el miembro de un tipo, el parámetro de un método, un espacio de nombres o un tipo.</span><span class="sxs-lookup"><span data-stu-id="28ca1-105">Simple names can be the name of a variable, type member, method parameter, namespace or type.</span></span> <span data-ttu-id="28ca1-106">Las expresiones pueden utilizar operadores que a su vez utilizan otras expresiones como parámetros, o llamadas a métodos cuyos parámetros son a su vez otras llamadas a métodos.</span><span class="sxs-lookup"><span data-stu-id="28ca1-106">Expressions can use operators that in turn use other expressions as parameters, or method calls whose parameters are in turn other method calls.</span></span> <span data-ttu-id="28ca1-107">Por consiguiente, las expresiones pueden ser de muy simples a muy complejas.</span><span class="sxs-lookup"><span data-stu-id="28ca1-107">Therefore, expressions can range from simple to very complex.</span></span>  
  
 <span data-ttu-id="28ca1-108">En [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] de las consultas, las expresiones pueden contener cualquier elemento permitido por los tipos dentro del <xref:System.Linq.Expressions> espacio de nombres, incluyendo expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="28ca1-108">In [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries, expressions can contain anything allowed by the types within the <xref:System.Linq.Expressions> namespace, including lambda expressions.</span></span> <span data-ttu-id="28ca1-109">Las expresiones que se pueden utilizar en las consultas de [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] son un supraconjunto de las expresiones que se pueden utilizar para consultar [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28ca1-109">The expressions that can be used in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries are a superset of the expressions that can be used to query the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span>  <span data-ttu-id="28ca1-110">Las expresiones que forman parte de las consultas realizadas en el [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] están limitadas por las operaciones admitidas por `ObjectQuery<T>` y el origen de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="28ca1-110">Expressions that are part of queries against the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] are limited to operations supported by `ObjectQuery<T>` and the underlying data source.</span></span>  
  
 <span data-ttu-id="28ca1-111">En el ejemplo siguiente, la comparación en la cláusula `Where` es una expresión:</span><span class="sxs-lookup"><span data-stu-id="28ca1-111">In the following example, the comparison in the `Where` clause is an expression:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#whereexpression)]
 [!code-vb[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#whereexpression)]  
  
> [!NOTE]
>  <span data-ttu-id="28ca1-112">Las estructuras de un lenguaje concreto, como `unchecked`de C#, no tienen ningún significado en [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28ca1-112">Specific language constructs, such as C# `unchecked`, have no meaning in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="28ca1-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="28ca1-113">In This Section</span></span>  
 [<span data-ttu-id="28ca1-114">Expresiones constantes</span><span class="sxs-lookup"><span data-stu-id="28ca1-114">Constant Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constant-expressions.md)  
  
 [<span data-ttu-id="28ca1-115">Expresiones de comparación</span><span class="sxs-lookup"><span data-stu-id="28ca1-115">Comparison Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/comparison-expressions.md)  
  
 [<span data-ttu-id="28ca1-116">Comparaciones NULL</span><span class="sxs-lookup"><span data-stu-id="28ca1-116">Null Comparisons</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/null-comparisons.md)  
  
 [<span data-ttu-id="28ca1-117">Expresiones de inicialización</span><span class="sxs-lookup"><span data-stu-id="28ca1-117">Initialization Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/initialization-expressions.md)  
  
 [<span data-ttu-id="28ca1-118">Propiedades de navegación</span><span class="sxs-lookup"><span data-stu-id="28ca1-118">Navigation Properties</span></span>](http://msdn.microsoft.com/en-us/41e1e6b9-8a57-467d-99d9-1857d2ca2ea5)  
  
## <a name="see-also"></a><span data-ttu-id="28ca1-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="28ca1-119">See Also</span></span>  
 [<span data-ttu-id="28ca1-120">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="28ca1-120">ADO.NET Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/index.md)
