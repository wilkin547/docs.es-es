---
title: Funciones definidas por el usuario
ms.date: 03/30/2017
ms.assetid: 3304c9b2-5c7a-4a95-9d45-4f260dcb606e
ms.openlocfilehash: f1222d9332d365c9c3c6ca2aa28cbb48e92c04e0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61917675"
---
# <a name="user-defined-functions"></a><span data-ttu-id="38559-102">Funciones definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="38559-102">User-Defined Functions</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="38559-103">utiliza los métodos de un modelo de objetos para representar las funciones definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="38559-103">uses methods in your object model to represent user-defined functions.</span></span> <span data-ttu-id="38559-104">Los métodos se designan como funciones aplicando el atributo <xref:System.Data.Linq.Mapping.FunctionAttribute> y, si es necesario, el atributo <xref:System.Data.Linq.Mapping.ParameterAttribute>.</span><span class="sxs-lookup"><span data-stu-id="38559-104">You designate methods as functions by applying the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute and, where required, the <xref:System.Data.Linq.Mapping.ParameterAttribute> attribute.</span></span> <span data-ttu-id="38559-105">Para obtener más información, consulte [el modelo LINQ to SQL objeto](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span><span class="sxs-lookup"><span data-stu-id="38559-105">For more information, see [The LINQ to SQL Object Model](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span></span>  
  
 <span data-ttu-id="38559-106">Para evitar que se inicie <xref:System.InvalidOperationException>, las funciones definidas por el usuario en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] deben presentarse de una de las formas siguientes:</span><span class="sxs-lookup"><span data-stu-id="38559-106">To avoid an <xref:System.InvalidOperationException>, user-defined functions in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] must be in one of the following forms:</span></span>  
  
-   <span data-ttu-id="38559-107">Una función ajustada como llamada a método que tiene los atributos de asignación correctos.</span><span class="sxs-lookup"><span data-stu-id="38559-107">A function wrapped as a method call having the correct mapping attributes.</span></span> <span data-ttu-id="38559-108">Para obtener más información, consulte [asignación basada en atributos](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="38559-108">For more information, see [Attribute-Based Mapping](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span></span>  
  
-   <span data-ttu-id="38559-109">Un método SQL estático específico de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38559-109">A static SQL method specific to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
-   <span data-ttu-id="38559-110">Una función admitida por un método [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38559-110">A function supported by a [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] method.</span></span>  
  
 <span data-ttu-id="38559-111">Los temas de esta sección muestran cómo formar estos métodos y cómo llamarlos en una aplicación si es usted quien escribe el código.</span><span class="sxs-lookup"><span data-stu-id="38559-111">The topics in this section show how to form and call these methods in your application if you write the code yourself.</span></span> <span data-ttu-id="38559-112">Los desarrolladores que usan Visual Studio normalmente usaría el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para asignar funciones definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="38559-112">Developers using Visual Studio would typically use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to map user-defined functions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="38559-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="38559-113">In This Section</span></span>  
 [<span data-ttu-id="38559-114">Cómo: Utilice las funciones escalares de definido por el usuario</span><span class="sxs-lookup"><span data-stu-id="38559-114">How to: Use Scalar-Valued User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-scalar-valued-user-defined-functions.md)  
 <span data-ttu-id="38559-115">Describe cómo implementar una función que devuelve valores escalares.</span><span class="sxs-lookup"><span data-stu-id="38559-115">Describes how to implement a function that returns scalar values.</span></span>  
  
 [<span data-ttu-id="38559-116">Cómo: Usar las funciones con valores de tabla de definido por el usuario</span><span class="sxs-lookup"><span data-stu-id="38559-116">How to: Use Table-Valued User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-table-valued-user-defined-functions.md)  
 <span data-ttu-id="38559-117">Describe cómo implementar una función que devuelve valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="38559-117">Describes how to implement a function that returns table values.</span></span>  
  
 [<span data-ttu-id="38559-118">Cómo: Llamar a funciones alineadas definidas por usuario</span><span class="sxs-lookup"><span data-stu-id="38559-118">How to: Call User-Defined Functions Inline</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md)  
 <span data-ttu-id="38559-119">Describe cómo realizar llamadas en el código a funciones y cómo varía la ejecución en esos casos.</span><span class="sxs-lookup"><span data-stu-id="38559-119">Describes how to make inline calls to functions and the differences in execution when the call is made inline.</span></span>
