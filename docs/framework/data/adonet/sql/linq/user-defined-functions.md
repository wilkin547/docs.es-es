---
title: Funciones definidas por el usuario
ms.date: 03/30/2017
ms.assetid: 3304c9b2-5c7a-4a95-9d45-4f260dcb606e
ms.openlocfilehash: 061e07ba91a1742c90a594bf42f12e64172b2481
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164121"
---
# <a name="user-defined-functions"></a><span data-ttu-id="e89d6-102">Funciones definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="e89d6-102">User-Defined Functions</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="e89d6-103">utiliza los métodos de un modelo de objetos para representar las funciones definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="e89d6-103">uses methods in your object model to represent user-defined functions.</span></span> <span data-ttu-id="e89d6-104">Los métodos se designan como funciones aplicando el atributo <xref:System.Data.Linq.Mapping.FunctionAttribute> y, si es necesario, el atributo <xref:System.Data.Linq.Mapping.ParameterAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e89d6-104">You designate methods as functions by applying the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute and, where required, the <xref:System.Data.Linq.Mapping.ParameterAttribute> attribute.</span></span> <span data-ttu-id="e89d6-105">Para obtener más información, vea [el LINQ to SQL modelo de objetos](the-linq-to-sql-object-model.md).</span><span class="sxs-lookup"><span data-stu-id="e89d6-105">For more information, see [The LINQ to SQL Object Model](the-linq-to-sql-object-model.md).</span></span>  
  
 <span data-ttu-id="e89d6-106">Para evitar que se inicie <xref:System.InvalidOperationException>, las funciones definidas por el usuario en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] deben presentarse de una de las formas siguientes:</span><span class="sxs-lookup"><span data-stu-id="e89d6-106">To avoid an <xref:System.InvalidOperationException>, user-defined functions in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] must be in one of the following forms:</span></span>  
  
- <span data-ttu-id="e89d6-107">Una función ajustada como llamada a método que tiene los atributos de asignación correctos.</span><span class="sxs-lookup"><span data-stu-id="e89d6-107">A function wrapped as a method call having the correct mapping attributes.</span></span> <span data-ttu-id="e89d6-108">Para obtener más información, consulte [asignación basada en atributos](attribute-based-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="e89d6-108">For more information, see [Attribute-Based Mapping](attribute-based-mapping.md).</span></span>  
  
- <span data-ttu-id="e89d6-109">Un método SQL estático específico de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e89d6-109">A static SQL method specific to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
- <span data-ttu-id="e89d6-110">Función compatible con un método .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e89d6-110">A function supported by a .NET Framework method.</span></span>  
  
 <span data-ttu-id="e89d6-111">Los temas de esta sección muestran cómo formar estos métodos y cómo llamarlos en una aplicación si es usted quien escribe el código.</span><span class="sxs-lookup"><span data-stu-id="e89d6-111">The topics in this section show how to form and call these methods in your application if you write the code yourself.</span></span> <span data-ttu-id="e89d6-112">Los desarrolladores que usan Visual Studio normalmente usarían el Object Relational Designer para asignar funciones definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="e89d6-112">Developers using Visual Studio would typically use the Object Relational Designer to map user-defined functions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e89d6-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e89d6-113">In This Section</span></span>  

 [<span data-ttu-id="e89d6-114">Procedimiento para usar funciones definidas por el usuario con valores escalares</span><span class="sxs-lookup"><span data-stu-id="e89d6-114">How to: Use Scalar-Valued User-Defined Functions</span></span>](how-to-use-scalar-valued-user-defined-functions.md)  
 <span data-ttu-id="e89d6-115">Describe cómo implementar una función que devuelve valores escalares.</span><span class="sxs-lookup"><span data-stu-id="e89d6-115">Describes how to implement a function that returns scalar values.</span></span>  
  
 [<span data-ttu-id="e89d6-116">Procedimiento para usar funciones definidas por el usuario con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="e89d6-116">How to: Use Table-Valued User-Defined Functions</span></span>](how-to-use-table-valued-user-defined-functions.md)  
 <span data-ttu-id="e89d6-117">Describe cómo implementar una función que devuelve valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="e89d6-117">Describes how to implement a function that returns table values.</span></span>  
  
 [<span data-ttu-id="e89d6-118">Procedimiento para llamar a funciones alineadas definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="e89d6-118">How to: Call User-Defined Functions Inline</span></span>](how-to-call-user-defined-functions-inline.md)  
 <span data-ttu-id="e89d6-119">Describe cómo realizar llamadas en el código a funciones y cómo varía la ejecución en esos casos.</span><span class="sxs-lookup"><span data-stu-id="e89d6-119">Describes how to make inline calls to functions and the differences in execution when the call is made inline.</span></span>
