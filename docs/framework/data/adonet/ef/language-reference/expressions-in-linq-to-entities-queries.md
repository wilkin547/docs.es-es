---
title: Expresiones en consultas de LINQ to Entities
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d70b502f-6a15-4120-b4fe-500b173ad9cc
ms.openlocfilehash: f449e7d5626d4a8c9709ae2cb4c026869d1e2dc9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54661781"
---
# <a name="expressions-in-linq-to-entities-queries"></a><span data-ttu-id="c4315-102">Expresiones en consultas de LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="c4315-102">Expressions in LINQ to Entities Queries</span></span>
<span data-ttu-id="c4315-103">Una expresión es un fragmento de código que se puede evaluar como un valor, objeto, método o espacio de nombres único.</span><span class="sxs-lookup"><span data-stu-id="c4315-103">An expression is a fragment of code that can be evaluated to a single value, object, method, or namespace.</span></span> <span data-ttu-id="c4315-104">Las expresiones pueden contener un valor literal, una llamada a un método, un operador y sus operandos, o un nombre simple.</span><span class="sxs-lookup"><span data-stu-id="c4315-104">Expressions can contain a literal value, a method call, an operator and its operands, or a simple name.</span></span> <span data-ttu-id="c4315-105">Los nombres simples pueden ser el nombre de una variable, el miembro de un tipo, el parámetro de un método, un espacio de nombres o un tipo.</span><span class="sxs-lookup"><span data-stu-id="c4315-105">Simple names can be the name of a variable, type member, method parameter, namespace or type.</span></span> <span data-ttu-id="c4315-106">Las expresiones pueden utilizar operadores que a su vez utilizan otras expresiones como parámetros, o llamadas a métodos cuyos parámetros son a su vez otras llamadas a métodos.</span><span class="sxs-lookup"><span data-stu-id="c4315-106">Expressions can use operators that in turn use other expressions as parameters, or method calls whose parameters are in turn other method calls.</span></span> <span data-ttu-id="c4315-107">Por consiguiente, las expresiones pueden ser de muy simples a muy complejas.</span><span class="sxs-lookup"><span data-stu-id="c4315-107">Therefore, expressions can range from simple to very complex.</span></span>  
  
 <span data-ttu-id="c4315-108">En [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] consultas, las expresiones pueden contener cualquier elemento permitido por los tipos dentro de la <xref:System.Linq.Expressions> espacio de nombres, incluidas las expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="c4315-108">In [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries, expressions can contain anything allowed by the types within the <xref:System.Linq.Expressions> namespace, including lambda expressions.</span></span> <span data-ttu-id="c4315-109">Las expresiones que se pueden utilizar en las consultas de [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] son un supraconjunto de las expresiones que se pueden utilizar para consultar [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c4315-109">The expressions that can be used in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries are a superset of the expressions that can be used to query the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].</span></span>  <span data-ttu-id="c4315-110">Las expresiones que forman parte de las consultas en el [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] están limitadas por las operaciones admitidas por `ObjectQuery<T>` y el origen de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="c4315-110">Expressions that are part of queries against the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] are limited to operations supported by `ObjectQuery<T>` and the underlying data source.</span></span>  
  
 <span data-ttu-id="c4315-111">En el ejemplo siguiente, la comparación en la cláusula `Where` es una expresión:</span><span class="sxs-lookup"><span data-stu-id="c4315-111">In the following example, the comparison in the `Where` clause is an expression:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#whereexpression)]
 [!code-vb[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#whereexpression)]  
  
> [!NOTE]
>  <span data-ttu-id="c4315-112">Las estructuras de un lenguaje concreto, como `unchecked`de C#, no tienen ningún significado en [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c4315-112">Specific language constructs, such as C# `unchecked`, have no meaning in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c4315-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c4315-113">In This Section</span></span>  
 [<span data-ttu-id="c4315-114">Expresiones constantes</span><span class="sxs-lookup"><span data-stu-id="c4315-114">Constant Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constant-expressions.md)  
  
 [<span data-ttu-id="c4315-115">Expresiones de comparación</span><span class="sxs-lookup"><span data-stu-id="c4315-115">Comparison Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/comparison-expressions.md)  
  
 [<span data-ttu-id="c4315-116">Comparaciones NULL</span><span class="sxs-lookup"><span data-stu-id="c4315-116">Null Comparisons</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/null-comparisons.md)  
  
 [<span data-ttu-id="c4315-117">Expresiones de inicialización</span><span class="sxs-lookup"><span data-stu-id="c4315-117">Initialization Expressions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/initialization-expressions.md)  
  
 [<span data-ttu-id="c4315-118">Propiedades de navegación</span><span class="sxs-lookup"><span data-stu-id="c4315-118">Navigation Properties</span></span>](https://msdn.microsoft.com/library/41e1e6b9-8a57-467d-99d9-1857d2ca2ea5)  
  
## <a name="see-also"></a><span data-ttu-id="c4315-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4315-119">See also</span></span>
- [<span data-ttu-id="c4315-120">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="c4315-120">ADO.NET Entity Framework</span></span>](../../../../../../docs/framework/data/adonet/ef/index.md)
