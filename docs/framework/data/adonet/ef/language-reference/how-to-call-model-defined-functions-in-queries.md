---
title: "Cómo: Llamar a funciones definidas por el modelo en consultas"
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
ms.assetid: 6c804e4d-f348-4afd-9f63-d3f0f24bc6a9
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 179c00def6b5a810806d536a8728cbbc544b1084
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-model-defined-functions-in-queries"></a><span data-ttu-id="10840-102">Cómo: Llamar a funciones definidas por el modelo en consultas</span><span class="sxs-lookup"><span data-stu-id="10840-102">How to: Call Model-Defined Functions in Queries</span></span>
<span data-ttu-id="10840-103">En este tema se describe cómo llamar a las funciones definidas en el modelo conceptual desde consultas [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].</span><span class="sxs-lookup"><span data-stu-id="10840-103">This topic describes how to call functions that are defined in the conceptual model from within [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries.</span></span>  
  
 <span data-ttu-id="10840-104">El siguiente procedimiento proporciona un esquema de alto nivel para llamar a una función definida por el modelo desde una consulta [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].</span><span class="sxs-lookup"><span data-stu-id="10840-104">The procedure below provides a high-level outline for calling a model-defined function from within a [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] query.</span></span> <span data-ttu-id="10840-105">El ejemplo que sigue proporciona más detalles sobre los pasos del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="10840-105">The example that follows provides more detail about the steps in the procedure.</span></span> <span data-ttu-id="10840-106">El procedimiento da por hecho que se ha definido una función en el modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="10840-106">The procedure assumes that you have defined a function in the conceptual model.</span></span> <span data-ttu-id="10840-107">Para obtener más información, consulte [Cómo: definir funciones personalizadas en el modelo Conceptual](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f).</span><span class="sxs-lookup"><span data-stu-id="10840-107">For more information, see [How to: Define Custom Functions in the Conceptual Model](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f).</span></span>  
  
### <a name="to-call-a-function-defined-in-the-conceptual-model"></a><span data-ttu-id="10840-108">Para llamar a una función definida en el modelo conceptual</span><span class="sxs-lookup"><span data-stu-id="10840-108">To call a function defined in the conceptual model</span></span>  
  
1.  <span data-ttu-id="10840-109">Agregue un método de Common Language Runtime (CLR) a su aplicación que se corresponda con la función definida en el modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="10840-109">Add a common language runtime (CLR) method to your application that maps to the function defined in the conceptual model.</span></span> <span data-ttu-id="10840-110">Para asignar el método, debe aplicarle un atributo <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="10840-110">To map the method, you must apply an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to the method.</span></span> <span data-ttu-id="10840-111">Tenga en cuenta que los parámetros <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> y <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> del atributo son el nombre del espacio de nombres del modelo conceptual y el nombre de la función en el modelo conceptual, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="10840-111">Note that the <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> and <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> parameters of the attribute are the namespace name of the conceptual model and the function name in the conceptual model respectively.</span></span> <span data-ttu-id="10840-112">La resolución del nombre de la función para LINQ distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="10840-112">Function name resolution for LINQ is case sensitive.</span></span>  
  
2.  <span data-ttu-id="10840-113">Llame a la función en una consulta [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].</span><span class="sxs-lookup"><span data-stu-id="10840-113">Call the function in a [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10840-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="10840-114">Example</span></span>  
 <span data-ttu-id="10840-115">En el siguiente ejemplo se muestra cómo llamar a una función que se define en el modelo conceptual desde una consulta [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].</span><span class="sxs-lookup"><span data-stu-id="10840-115">The following example demonstrates how to call a function that is defined in the conceptual model from within a [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] query.</span></span> <span data-ttu-id="10840-116">En el ejemplo se usa el modelo School.</span><span class="sxs-lookup"><span data-stu-id="10840-116">The example uses the School model.</span></span> <span data-ttu-id="10840-117">Para obtener información sobre el modelo School, vea [crear la base de datos de ejemplo School](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0) y [generar el archivo .edmx de School](http://msdn.microsoft.com/en-us/c48b3907-a8be-4fe6-884c-e95af1852758).</span><span class="sxs-lookup"><span data-stu-id="10840-117">For information about the School model, see [Creating the School Sample Database](http://msdn.microsoft.com/en-us/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0) and [Generating the School .edmx File](http://msdn.microsoft.com/en-us/c48b3907-a8be-4fe6-884c-e95af1852758).</span></span>  
  
 <span data-ttu-id="10840-118">La siguiente función del modelo conceptual devuelve el número de años transcurridos desde que se contrató a un instructor.</span><span class="sxs-lookup"><span data-stu-id="10840-118">The following conceptual model function returns the number of years since an instructor was hired.</span></span> <span data-ttu-id="10840-119">Para obtener información acerca de cómo agregar la función a un modelo conceptual, consulte [Cómo: definir funciones personalizadas en el modelo Conceptual](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f).)</span><span class="sxs-lookup"><span data-stu-id="10840-119">For information about adding the function to a conceptual model, see [How to: Define Custom Functions in the Conceptual Model](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f).)</span></span>  
  
 [!code-xml[DP ConceptualModelFunctions#1](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp conceptualmodelfunctions/xml/school.edmx#1)]
  
## <a name="example"></a><span data-ttu-id="10840-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="10840-120">Example</span></span>  
 <span data-ttu-id="10840-121">A continuación, agregue el siguiente método a su aplicación y utilice un atributo <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> para asignarlo a la función del modelo conceptual:</span><span class="sxs-lookup"><span data-stu-id="10840-121">Next, add the following method to your application and use an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to map it to the conceptual model function:</span></span>  
  
 [!code-csharp[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#2)]
 [!code-vb[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="10840-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="10840-122">Example</span></span>  
 <span data-ttu-id="10840-123">Ahora puede llamar a la función del modelo conceptual desde una consulta [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].</span><span class="sxs-lookup"><span data-stu-id="10840-123">Now you can call the conceptual model function from within a [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] query.</span></span> <span data-ttu-id="10840-124">El siguiente código llama al método para mostrar todos los instructores que se contrataron hace más de diez años:</span><span class="sxs-lookup"><span data-stu-id="10840-124">The following code calls the method to display all instructors that were hired more than ten years ago:</span></span>  
  
 [!code-csharp[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#3)]
 [!code-vb[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="10840-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="10840-125">See Also</span></span>  
 [<span data-ttu-id="10840-126">información general de archivo .edmx</span><span class="sxs-lookup"><span data-stu-id="10840-126">.edmx File Overview</span></span>](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [<span data-ttu-id="10840-127">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="10840-127">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)  
 [<span data-ttu-id="10840-128">Llamar a funciones en consultas LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="10840-128">Calling Functions in LINQ to Entities Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)  
 [<span data-ttu-id="10840-129">Cómo: llamar a funciones definidas por el modelo como métodos de objeto</span><span class="sxs-lookup"><span data-stu-id="10840-129">How to: Call Model-Defined Functions as Object Methods</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-as-object-methods.md)
