---
title: Funciones definidas por el usuario
ms.date: 03/30/2017
ms.assetid: 3304c9b2-5c7a-4a95-9d45-4f260dcb606e
ms.openlocfilehash: 54faca27e3f70283144f902e531e2a08e45bae3b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742715"
---
# <a name="user-defined-functions"></a><span data-ttu-id="2bc5b-102">Funciones definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="2bc5b-102">User-Defined Functions</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="2bc5b-103">utiliza los métodos de un modelo de objetos para representar las funciones definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="2bc5b-103">uses methods in your object model to represent user-defined functions.</span></span> <span data-ttu-id="2bc5b-104">Los métodos se designan como funciones aplicando el atributo <xref:System.Data.Linq.Mapping.FunctionAttribute> y, si es necesario, el atributo <xref:System.Data.Linq.Mapping.ParameterAttribute>.</span><span class="sxs-lookup"><span data-stu-id="2bc5b-104">You designate methods as functions by applying the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute and, where required, the <xref:System.Data.Linq.Mapping.ParameterAttribute> attribute.</span></span> <span data-ttu-id="2bc5b-105">Para obtener más información, consulte [el modelo LINQ to SQL objeto](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span><span class="sxs-lookup"><span data-stu-id="2bc5b-105">For more information, see [The LINQ to SQL Object Model](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span></span>  
  
 <span data-ttu-id="2bc5b-106">Para evitar que se inicie <xref:System.InvalidOperationException>, las funciones definidas por el usuario en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] deben presentarse de una de las formas siguientes:</span><span class="sxs-lookup"><span data-stu-id="2bc5b-106">To avoid an <xref:System.InvalidOperationException>, user-defined functions in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] must be in one of the following forms:</span></span>  
  
- <span data-ttu-id="2bc5b-107">Una función ajustada como llamada a método que tiene los atributos de asignación correctos.</span><span class="sxs-lookup"><span data-stu-id="2bc5b-107">A function wrapped as a method call having the correct mapping attributes.</span></span> <span data-ttu-id="2bc5b-108">Para obtener más información, consulte [asignación basada en atributos](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="2bc5b-108">For more information, see [Attribute-Based Mapping](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span></span>  
  
- <span data-ttu-id="2bc5b-109">Un método SQL estático específico de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2bc5b-109">A static SQL method specific to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
- <span data-ttu-id="2bc5b-110">Una función admitida por un método de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2bc5b-110">A function supported by a .NET Framework method.</span></span>  
  
 <span data-ttu-id="2bc5b-111">Los temas de esta sección muestran cómo formar estos métodos y cómo llamarlos en una aplicación si es usted quien escribe el código.</span><span class="sxs-lookup"><span data-stu-id="2bc5b-111">The topics in this section show how to form and call these methods in your application if you write the code yourself.</span></span> <span data-ttu-id="2bc5b-112">Los desarrolladores que usan Visual Studio normalmente usaría el Object Relational Designer para asignar funciones definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="2bc5b-112">Developers using Visual Studio would typically use the Object Relational Designer to map user-defined functions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2bc5b-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2bc5b-113">In This Section</span></span>  
 [<span data-ttu-id="2bc5b-114">Cómo: Utilice las funciones escalares de definido por el usuario</span><span class="sxs-lookup"><span data-stu-id="2bc5b-114">How to: Use Scalar-Valued User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-scalar-valued-user-defined-functions.md)  
 <span data-ttu-id="2bc5b-115">Describe cómo implementar una función que devuelve valores escalares.</span><span class="sxs-lookup"><span data-stu-id="2bc5b-115">Describes how to implement a function that returns scalar values.</span></span>  
  
 [<span data-ttu-id="2bc5b-116">Procedimientos: Usar las funciones con valores de tabla de definido por el usuario</span><span class="sxs-lookup"><span data-stu-id="2bc5b-116">How to: Use Table-Valued User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-table-valued-user-defined-functions.md)  
 <span data-ttu-id="2bc5b-117">Describe cómo implementar una función que devuelve valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="2bc5b-117">Describes how to implement a function that returns table values.</span></span>  
  
 [<span data-ttu-id="2bc5b-118">Cómo: Llamar a funciones alineadas definidas por usuario</span><span class="sxs-lookup"><span data-stu-id="2bc5b-118">How to: Call User-Defined Functions Inline</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md)  
 <span data-ttu-id="2bc5b-119">Describe cómo realizar llamadas en el código a funciones y cómo varía la ejecución en esos casos.</span><span class="sxs-lookup"><span data-stu-id="2bc5b-119">Describes how to make inline calls to functions and the differences in execution when the call is made inline.</span></span>
