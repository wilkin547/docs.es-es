---
title: Procedimiento para llamar a funciones definidas por el modelo en consultas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6c804e4d-f348-4afd-9f63-d3f0f24bc6a9
ms.openlocfilehash: b142ef820e964eaf5f1afed53a6b12a9344c7dda
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189336"
---
# <a name="how-to-call-model-defined-functions-in-queries"></a><span data-ttu-id="fb8c7-102">Procedimiento para llamar a funciones definidas por el modelo en consultas</span><span class="sxs-lookup"><span data-stu-id="fb8c7-102">How to: Call Model-Defined Functions in Queries</span></span>

<span data-ttu-id="fb8c7-103">En este tema se describe cómo llamar a las funciones definidas en el modelo conceptual desde LINQ to Entities consultas.</span><span class="sxs-lookup"><span data-stu-id="fb8c7-103">This topic describes how to call functions that are defined in the conceptual model from within LINQ to Entities queries.</span></span>  
  
 <span data-ttu-id="fb8c7-104">En el procedimiento siguiente se proporciona un esquema de alto nivel para llamar a una función definida por el modelo desde una consulta LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="fb8c7-104">The procedure below provides a high-level outline for calling a model-defined function from within a LINQ to Entities query.</span></span> <span data-ttu-id="fb8c7-105">El ejemplo que sigue proporciona más detalles sobre los pasos del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="fb8c7-105">The example that follows provides more detail about the steps in the procedure.</span></span> <span data-ttu-id="fb8c7-106">El procedimiento da por hecho que se ha definido una función en el modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="fb8c7-106">The procedure assumes that you have defined a function in the conceptual model.</span></span> <span data-ttu-id="fb8c7-107">Para obtener más información, vea [Cómo: definir funciones personalizadas en el modelo conceptual](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="fb8c7-107">For more information, see [How to: Define Custom Functions in the Conceptual Model](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).</span></span>  
  
### <a name="to-call-a-function-defined-in-the-conceptual-model"></a><span data-ttu-id="fb8c7-108">Para llamar a una función definida en el modelo conceptual</span><span class="sxs-lookup"><span data-stu-id="fb8c7-108">To call a function defined in the conceptual model</span></span>  
  
1. <span data-ttu-id="fb8c7-109">Agregue un método de Common Language Runtime (CLR) a su aplicación que se corresponda con la función definida en el modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="fb8c7-109">Add a common language runtime (CLR) method to your application that maps to the function defined in the conceptual model.</span></span> <span data-ttu-id="fb8c7-110">Para asignar el método, debe aplicarle un atributo <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="fb8c7-110">To map the method, you must apply an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to the method.</span></span> <span data-ttu-id="fb8c7-111">Tenga en cuenta que los parámetros <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> y <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> del atributo son el nombre del espacio de nombres del modelo conceptual y el nombre de la función en el modelo conceptual, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="fb8c7-111">Note that the <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> and <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> parameters of the attribute are the namespace name of the conceptual model and the function name in the conceptual model respectively.</span></span> <span data-ttu-id="fb8c7-112">La resolución del nombre de la función para LINQ distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="fb8c7-112">Function name resolution for LINQ is case sensitive.</span></span>  
  
2. <span data-ttu-id="fb8c7-113">Llame a la función en una consulta LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="fb8c7-113">Call the function in a LINQ to Entities query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb8c7-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fb8c7-114">Example</span></span>  

 <span data-ttu-id="fb8c7-115">En el ejemplo siguiente se muestra cómo llamar a una función que se define en el modelo conceptual desde una consulta LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="fb8c7-115">The following example demonstrates how to call a function that is defined in the conceptual model from within a LINQ to Entities query.</span></span> <span data-ttu-id="fb8c7-116">En el ejemplo se usa el modelo School.</span><span class="sxs-lookup"><span data-stu-id="fb8c7-116">The example uses the School model.</span></span> <span data-ttu-id="fb8c7-117">Para obtener información sobre el modelo School, vea [crear la base de datos de ejemplo School](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)) y [generar el archivo School. edmx](/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="fb8c7-117">For information about the School model, see [Creating the School Sample Database](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)) and [Generating the School .edmx File](/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100)).</span></span>  
  
 <span data-ttu-id="fb8c7-118">La siguiente función del modelo conceptual devuelve el número de años transcurridos desde que se contrató a un instructor.</span><span class="sxs-lookup"><span data-stu-id="fb8c7-118">The following conceptual model function returns the number of years since an instructor was hired.</span></span> <span data-ttu-id="fb8c7-119">Para obtener información sobre cómo agregar la función a un modelo conceptual, vea [Cómo: definir funciones personalizadas en el modelo conceptual](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))).</span><span class="sxs-lookup"><span data-stu-id="fb8c7-119">For information about adding the function to a conceptual model, see [How to: Define Custom Functions in the Conceptual Model](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).)</span></span>  
  
 [!code-xml[DP ConceptualModelFunctions#1](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp conceptualmodelfunctions/xml/school.edmx#1)]
  
## <a name="example"></a><span data-ttu-id="fb8c7-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fb8c7-120">Example</span></span>  

 <span data-ttu-id="fb8c7-121">A continuación, agregue el siguiente método a su aplicación y utilice un atributo <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> para asignarlo a la función del modelo conceptual:</span><span class="sxs-lookup"><span data-stu-id="fb8c7-121">Next, add the following method to your application and use an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to map it to the conceptual model function:</span></span>  
  
 [!code-csharp[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#2)]
 [!code-vb[DP ConceptualModelFunctions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="fb8c7-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fb8c7-122">Example</span></span>  

 <span data-ttu-id="fb8c7-123">Ahora puede llamar a la función de modelo conceptual desde una consulta de LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="fb8c7-123">Now you can call the conceptual model function from within a LINQ to Entities query.</span></span> <span data-ttu-id="fb8c7-124">El siguiente código llama al método para mostrar todos los instructores que se contrataron hace más de diez años:</span><span class="sxs-lookup"><span data-stu-id="fb8c7-124">The following code calls the method to display all instructors that were hired more than ten years ago:</span></span>  
  
 [!code-csharp[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp conceptualmodelfunctions/cs/program.cs#3)]
 [!code-vb[DP ConceptualModelFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp conceptualmodelfunctions/vb/module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="fb8c7-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fb8c7-125">See also</span></span>

- <span data-ttu-id="fb8c7-126">[.edmx, Información general sobre el archivo](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="fb8c7-126">[.edmx File Overview](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span></span>
- [<span data-ttu-id="fb8c7-127">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="fb8c7-127">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
- [<span data-ttu-id="fb8c7-128">Llamar a funciones en consultas de LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="fb8c7-128">Calling Functions in LINQ to Entities Queries</span></span>](calling-functions-in-linq-to-entities-queries.md)
- [<span data-ttu-id="fb8c7-129">Procedimiento para llamar a funciones definidas por el modelo como métodos de objeto</span><span class="sxs-lookup"><span data-stu-id="fb8c7-129">How to: Call Model-Defined Functions as Object Methods</span></span>](how-to-call-model-defined-functions-as-object-methods.md)
