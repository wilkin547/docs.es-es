---
description: 'Más información sobre: funciones User-Defined'
title: Funciones definidas por el usuario
ms.date: 03/30/2017
ms.assetid: 3304c9b2-5c7a-4a95-9d45-4f260dcb606e
ms.openlocfilehash: d27abd78e15ad6cb5ce4e9440ac425159a0b5bdc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99680946"
---
# <a name="user-defined-functions"></a><span data-ttu-id="56474-103">Funciones definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="56474-103">User-Defined Functions</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="56474-104">utiliza los métodos de un modelo de objetos para representar las funciones definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="56474-104">uses methods in your object model to represent user-defined functions.</span></span> <span data-ttu-id="56474-105">Los métodos se designan como funciones aplicando el atributo <xref:System.Data.Linq.Mapping.FunctionAttribute> y, si es necesario, el atributo <xref:System.Data.Linq.Mapping.ParameterAttribute>.</span><span class="sxs-lookup"><span data-stu-id="56474-105">You designate methods as functions by applying the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute and, where required, the <xref:System.Data.Linq.Mapping.ParameterAttribute> attribute.</span></span> <span data-ttu-id="56474-106">Para obtener más información, vea [el LINQ to SQL modelo de objetos](the-linq-to-sql-object-model.md).</span><span class="sxs-lookup"><span data-stu-id="56474-106">For more information, see [The LINQ to SQL Object Model](the-linq-to-sql-object-model.md).</span></span>  
  
 <span data-ttu-id="56474-107">Para evitar que se inicie <xref:System.InvalidOperationException>, las funciones definidas por el usuario en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] deben presentarse de una de las formas siguientes:</span><span class="sxs-lookup"><span data-stu-id="56474-107">To avoid an <xref:System.InvalidOperationException>, user-defined functions in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] must be in one of the following forms:</span></span>  
  
- <span data-ttu-id="56474-108">Una función ajustada como llamada a método que tiene los atributos de asignación correctos.</span><span class="sxs-lookup"><span data-stu-id="56474-108">A function wrapped as a method call having the correct mapping attributes.</span></span> <span data-ttu-id="56474-109">Para obtener más información, consulte [asignación basada en atributos](attribute-based-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="56474-109">For more information, see [Attribute-Based Mapping](attribute-based-mapping.md).</span></span>  
  
- <span data-ttu-id="56474-110">Un método SQL estático específico de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="56474-110">A static SQL method specific to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
- <span data-ttu-id="56474-111">Función compatible con un método .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="56474-111">A function supported by a .NET Framework method.</span></span>  
  
 <span data-ttu-id="56474-112">Los temas de esta sección muestran cómo formar estos métodos y cómo llamarlos en una aplicación si es usted quien escribe el código.</span><span class="sxs-lookup"><span data-stu-id="56474-112">The topics in this section show how to form and call these methods in your application if you write the code yourself.</span></span> <span data-ttu-id="56474-113">Los desarrolladores que usan Visual Studio normalmente usarían el Object Relational Designer para asignar funciones definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="56474-113">Developers using Visual Studio would typically use the Object Relational Designer to map user-defined functions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="56474-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="56474-114">In This Section</span></span>  

 [<span data-ttu-id="56474-115">Procedimiento para usar funciones definidas por el usuario con valores escalares</span><span class="sxs-lookup"><span data-stu-id="56474-115">How to: Use Scalar-Valued User-Defined Functions</span></span>](how-to-use-scalar-valued-user-defined-functions.md)  
 <span data-ttu-id="56474-116">Describe cómo implementar una función que devuelve valores escalares.</span><span class="sxs-lookup"><span data-stu-id="56474-116">Describes how to implement a function that returns scalar values.</span></span>  
  
 [<span data-ttu-id="56474-117">Procedimiento para usar funciones definidas por el usuario con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="56474-117">How to: Use Table-Valued User-Defined Functions</span></span>](how-to-use-table-valued-user-defined-functions.md)  
 <span data-ttu-id="56474-118">Describe cómo implementar una función que devuelve valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="56474-118">Describes how to implement a function that returns table values.</span></span>  
  
 [<span data-ttu-id="56474-119">Procedimiento para llamar a funciones alineadas definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="56474-119">How to: Call User-Defined Functions Inline</span></span>](how-to-call-user-defined-functions-inline.md)  
 <span data-ttu-id="56474-120">Describe cómo realizar llamadas en el código a funciones y cómo varía la ejecución en esos casos.</span><span class="sxs-lookup"><span data-stu-id="56474-120">Describes how to make inline calls to functions and the differences in execution when the call is made inline.</span></span>
