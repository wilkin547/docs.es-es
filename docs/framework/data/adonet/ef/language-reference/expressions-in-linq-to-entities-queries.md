---
title: Expresiones en consultas de LINQ to Entities
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d70b502f-6a15-4120-b4fe-500b173ad9cc
ms.openlocfilehash: f65759d37661271588d56965eadcccbe997623f4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166656"
---
# <a name="expressions-in-linq-to-entities-queries"></a><span data-ttu-id="59527-102">Expresiones en consultas de LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="59527-102">Expressions in LINQ to Entities Queries</span></span>

<span data-ttu-id="59527-103">Una expresión es un fragmento de código que se puede evaluar como un valor, objeto, método o espacio de nombres único.</span><span class="sxs-lookup"><span data-stu-id="59527-103">An expression is a fragment of code that can be evaluated to a single value, object, method, or namespace.</span></span> <span data-ttu-id="59527-104">Las expresiones pueden contener un valor literal, una llamada a un método, un operador y sus operandos, o un nombre simple.</span><span class="sxs-lookup"><span data-stu-id="59527-104">Expressions can contain a literal value, a method call, an operator and its operands, or a simple name.</span></span> <span data-ttu-id="59527-105">Los nombres simples pueden ser el nombre de una variable, el miembro de un tipo, el parámetro de un método, un espacio de nombres o un tipo.</span><span class="sxs-lookup"><span data-stu-id="59527-105">Simple names can be the name of a variable, type member, method parameter, namespace or type.</span></span> <span data-ttu-id="59527-106">Las expresiones pueden utilizar operadores que a su vez utilizan otras expresiones como parámetros, o llamadas a métodos cuyos parámetros son a su vez otras llamadas a métodos.</span><span class="sxs-lookup"><span data-stu-id="59527-106">Expressions can use operators that in turn use other expressions as parameters, or method calls whose parameters are in turn other method calls.</span></span> <span data-ttu-id="59527-107">Por consiguiente, las expresiones pueden ser de muy simples a muy complejas.</span><span class="sxs-lookup"><span data-stu-id="59527-107">Therefore, expressions can range from simple to very complex.</span></span>  
  
 <span data-ttu-id="59527-108">En LINQ to Entities consultas, las expresiones pueden contener cualquier elemento permitido por los tipos dentro del <xref:System.Linq.Expressions> espacio de nombres, incluidas las expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="59527-108">In LINQ to Entities queries, expressions can contain anything allowed by the types within the <xref:System.Linq.Expressions> namespace, including lambda expressions.</span></span> <span data-ttu-id="59527-109">Las expresiones que se pueden usar en las consultas de LINQ to Entities son un superconjunto de las expresiones que se pueden utilizar para consultar el Entity Framework. las expresiones que forman parte de las consultas en el Entity Framework se limitan a las operaciones admitidas por `ObjectQuery<T>` y el origen de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="59527-109">The expressions that can be used in LINQ to Entities queries are a superset of the expressions that can be used to query the Entity Framework.Expressions that are part of queries against the Entity Framework are limited to operations supported by `ObjectQuery<T>` and the underlying data source.</span></span>  
  
 <span data-ttu-id="59527-110">En el ejemplo siguiente, la comparación en la cláusula `Where` es una expresión:</span><span class="sxs-lookup"><span data-stu-id="59527-110">In the following example, the comparison in the `Where` clause is an expression:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#whereexpression)]
 [!code-vb[DP L2E Conceptual Examples#WhereExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#whereexpression)]  
  
> [!NOTE]
> <span data-ttu-id="59527-111">Las construcciones de lenguaje específicas, como C# `unchecked` , no tienen ningún significado en LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="59527-111">Specific language constructs, such as C# `unchecked`, have no meaning in LINQ to Entities.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="59527-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="59527-112">In This Section</span></span>  

 [<span data-ttu-id="59527-113">Expresiones constantes</span><span class="sxs-lookup"><span data-stu-id="59527-113">Constant Expressions</span></span>](constant-expressions.md)  
  
 [<span data-ttu-id="59527-114">Expresiones de comparación</span><span class="sxs-lookup"><span data-stu-id="59527-114">Comparison Expressions</span></span>](comparison-expressions.md)  
  
 [<span data-ttu-id="59527-115">Comparaciones NULL</span><span class="sxs-lookup"><span data-stu-id="59527-115">Null Comparisons</span></span>](null-comparisons.md)  
  
 [<span data-ttu-id="59527-116">Expresiones de inicialización</span><span class="sxs-lookup"><span data-stu-id="59527-116">Initialization Expressions</span></span>](initialization-expressions.md)  
  
 [<span data-ttu-id="59527-117">Relaciones, propiedades de navegación y claves externas</span><span class="sxs-lookup"><span data-stu-id="59527-117">Relationships, navigation properties and foreign keys</span></span>](/ef/ef6/fundamentals/relationships)  
  
## <a name="see-also"></a><span data-ttu-id="59527-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="59527-118">See also</span></span>

- [<span data-ttu-id="59527-119">ADO.NET Entity Framework</span><span class="sxs-lookup"><span data-stu-id="59527-119">ADO.NET Entity Framework</span></span>](../index.md)
