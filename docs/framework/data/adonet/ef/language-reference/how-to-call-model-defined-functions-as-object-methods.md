---
description: 'Más información acerca de cómo: llamar a funciones de Model-Defined como métodos de objeto'
title: Procedimiento para llamar a funciones definidas por el modelo como métodos de objeto
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 33bae8a8-4ed8-4a1f-85d1-c62ff288cc61
ms.openlocfilehash: 46f171d5785bf715382e87c3fb7dae932db0bb65
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99748679"
---
# <a name="how-to-call-model-defined-functions-as-object-methods"></a><span data-ttu-id="4c672-103">Procedimiento para llamar a funciones definidas por el modelo como métodos de objeto</span><span class="sxs-lookup"><span data-stu-id="4c672-103">How to: Call Model-Defined Functions as Object Methods</span></span>

<span data-ttu-id="4c672-104">En este tema se describe cómo llamar a una función definida por el modelo como un método en un objeto <xref:System.Data.Objects.ObjectContext> o como un método estático en una clase personalizada.</span><span class="sxs-lookup"><span data-stu-id="4c672-104">This topic describes how to call a model-defined function as a method on an <xref:System.Data.Objects.ObjectContext> object or as a static method on a custom class.</span></span> <span data-ttu-id="4c672-105">Una *función definida por el modelo* es una función que se define en el modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="4c672-105">A *model-defined function* is a function that is defined in the conceptual model.</span></span> <span data-ttu-id="4c672-106">Los procedimientos de este tema describen cómo llamar directamente a estas funciones en lugar de hacerlo desde consultas LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="4c672-106">The procedures in the topic describe how to call these functions directly instead of calling them from LINQ to Entities queries.</span></span> <span data-ttu-id="4c672-107">Para obtener información sobre cómo llamar a funciones definidas por el modelo en LINQ to Entities consultas, vea [Cómo: llamar a funciones de Model-Defined en las consultas](how-to-call-model-defined-functions-in-queries.md).</span><span class="sxs-lookup"><span data-stu-id="4c672-107">For information about calling model-defined functions in LINQ to Entities queries, see [How to: Call Model-Defined Functions in Queries](how-to-call-model-defined-functions-in-queries.md).</span></span>  
  
 <span data-ttu-id="4c672-108">Tanto si se llama a una función definida por el modelo como un método <xref:System.Data.Objects.ObjectContext> o como un método estático en una clase personalizada, primero se deberá asignar el método a dicha función con un atributo <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="4c672-108">Whether you call a model-defined function as an <xref:System.Data.Objects.ObjectContext> method or as a static method on a custom class, you must first map the method to the model-defined function with an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span> <span data-ttu-id="4c672-109">Sin embargo, si se define un método en la clase <xref:System.Data.Objects.ObjectContext>, se debe usar la propiedad <xref:System.Data.Objects.ObjectContext.QueryProvider%2A> para exponer el proveedor LINQ, mientras que si se define un método estático en una clase personalizada, se debe usar la propiedad <xref:System.Linq.IQueryable.Provider%2A> para exponer dicho proveedor.</span><span class="sxs-lookup"><span data-stu-id="4c672-109">However, when you define a method on the <xref:System.Data.Objects.ObjectContext> class, you must use the <xref:System.Data.Objects.ObjectContext.QueryProvider%2A> property to expose the LINQ provider, whereas when you define a static method on a custom class, you must use the <xref:System.Linq.IQueryable.Provider%2A> property to expose the LINQ provider.</span></span> <span data-ttu-id="4c672-110">Para obtener más información, vea los ejemplos que aparecen a continuación de los procedimientos siguientes.</span><span class="sxs-lookup"><span data-stu-id="4c672-110">For more information, see the examples that follow the procedures below.</span></span>  
  
 <span data-ttu-id="4c672-111">Los procedimientos siguientes proporcionan esquemas generales para llamar a una función definida por el modelo como un método en un objeto <xref:System.Data.Objects.ObjectContext> y como un método estático en una clase personalizada.</span><span class="sxs-lookup"><span data-stu-id="4c672-111">The procedures below provide high-level outlines for calling a model-defined function as a method on an <xref:System.Data.Objects.ObjectContext> object and as a static method on a custom class.</span></span> <span data-ttu-id="4c672-112">Los ejemplos que los siguen proporcionan más detalles sobre los pasos de los procedimientos.</span><span class="sxs-lookup"><span data-stu-id="4c672-112">The examples that follow provide more detail about the steps in the procedures.</span></span> <span data-ttu-id="4c672-113">Los procedimientos dan por hecho que se ha definido una función en el modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="4c672-113">The procedures assume that you have defined a function in the conceptual model.</span></span> <span data-ttu-id="4c672-114">Para obtener más información, vea [Cómo: definir funciones personalizadas en el modelo conceptual](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="4c672-114">For more information, see [How to: Define Custom Functions in the Conceptual Model](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).</span></span>  
  
### <a name="to-call-a-model-defined-function-as-a-method-on-an-objectcontext-object"></a><span data-ttu-id="4c672-115">Para llamar a una función definida por el modelo como un método en un objeto ObjectContext</span><span class="sxs-lookup"><span data-stu-id="4c672-115">To call a model-defined function as a method on an ObjectContext object</span></span>  
  
1. <span data-ttu-id="4c672-116">Agregue un archivo de código fuente para extender la clase parcial derivada de la clase <xref:System.Data.Objects.ObjectContext>, generada automáticamente por las herramientas de Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="4c672-116">Add a source file to extend the partial class derived from the <xref:System.Data.Objects.ObjectContext> class, auto-generated by the Entity Framework tools.</span></span> <span data-ttu-id="4c672-117">La definición del código auxiliar de CLR en un archivo de código fuente independiente evitará que se pierdan los cambios cuando se regenere el archivo.</span><span class="sxs-lookup"><span data-stu-id="4c672-117">Defining the CLR stub in a separate source file will prevent the changes from being lost when the file is regenerated.</span></span>  
  
2. <span data-ttu-id="4c672-118">Agregue un método de Common Language Runtime (CLR) a la clase <xref:System.Data.Objects.ObjectContext> que haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4c672-118">Add a common language runtime (CLR) method to your <xref:System.Data.Objects.ObjectContext> class that does the following:</span></span>  
  
    - <span data-ttu-id="4c672-119">Se asigne a la función definida en el modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="4c672-119">Maps to the function defined in the conceptual model.</span></span> <span data-ttu-id="4c672-120">Para asignar el método, debe aplicarle un atributo <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="4c672-120">To map the method, you must apply an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to the method.</span></span> <span data-ttu-id="4c672-121">Tenga en cuenta que los parámetros <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> y <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> del atributo son el nombre del espacio de nombres del modelo conceptual y el nombre de la función en el modelo conceptual, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="4c672-121">Note that the <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> and <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> parameters of the attribute are the namespace name of the conceptual model and the function name in the conceptual model, respectively.</span></span> <span data-ttu-id="4c672-122">La resolución del nombre de la función para LINQ distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="4c672-122">Function name resolution for LINQ is case sensitive.</span></span>  
  
    - <span data-ttu-id="4c672-123">Devuelva los resultados del método <xref:System.Linq.IQueryProvider.Execute%2A> devuelto por la propiedad <xref:System.Data.Objects.ObjectContext.QueryProvider%2A>.</span><span class="sxs-lookup"><span data-stu-id="4c672-123">Returns the results of the <xref:System.Linq.IQueryProvider.Execute%2A> method that is returned by the <xref:System.Data.Objects.ObjectContext.QueryProvider%2A> property.</span></span>  
  
3. <span data-ttu-id="4c672-124">Llame al método como un miembro de una instancia de la clase <xref:System.Data.Objects.ObjectContext>.</span><span class="sxs-lookup"><span data-stu-id="4c672-124">Call the method as a member on an instance of the <xref:System.Data.Objects.ObjectContext> class.</span></span>  
  
### <a name="to-call-a-model-defined-function-as-static-method-on-a-custom-class"></a><span data-ttu-id="4c672-125">Para llamar a una función definida por el modelo como un método estático en una clase personalizada</span><span class="sxs-lookup"><span data-stu-id="4c672-125">To call a model-defined function as static method on a custom class</span></span>  
  
1. <span data-ttu-id="4c672-126">Agregue una clase a la aplicación con un método estático que haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4c672-126">Add a class to your application with a static method that does the following:</span></span>  
  
    - <span data-ttu-id="4c672-127">Se asigne a la función definida en el modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="4c672-127">Maps to the function defined in the conceptual model.</span></span> <span data-ttu-id="4c672-128">Para asignar el método, debe aplicarle un atributo <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="4c672-128">To map the method, you must apply an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to the method.</span></span> <span data-ttu-id="4c672-129">Tenga en cuenta que los parámetros <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> y <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> del atributo son el nombre del espacio de nombres del modelo conceptual y el nombre de la función en el modelo conceptual, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="4c672-129">Note that the <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> and <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> parameters of the attribute are the namespace name of the conceptual model and the function name in the conceptual model, respectively.</span></span>  
  
    - <span data-ttu-id="4c672-130">Acepte un argumento <xref:System.Linq.IQueryable>.</span><span class="sxs-lookup"><span data-stu-id="4c672-130">Accepts an <xref:System.Linq.IQueryable> argument.</span></span>  
  
    - <span data-ttu-id="4c672-131">Devuelva los resultados del método <xref:System.Linq.IQueryProvider.Execute%2A> devuelto por la propiedad <xref:System.Linq.IQueryable.Provider%2A>.</span><span class="sxs-lookup"><span data-stu-id="4c672-131">Returns the results of the <xref:System.Linq.IQueryProvider.Execute%2A> method that is returned by the <xref:System.Linq.IQueryable.Provider%2A> property.</span></span>  
  
2. <span data-ttu-id="4c672-132">Llame al método como un miembro de un método estático en la clase personalizada</span><span class="sxs-lookup"><span data-stu-id="4c672-132">Call the method as a member a static method on the custom class</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c672-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4c672-133">Example</span></span>  

 <span data-ttu-id="4c672-134">**Llamar a una función definida por el modelo como un método en un objeto ObjectContext**</span><span class="sxs-lookup"><span data-stu-id="4c672-134">**Calling a Model-Defined Function as a Method on an ObjectContext Object**</span></span>  
  
 <span data-ttu-id="4c672-135">En el siguiente ejemplo se muestra cómo llamar a una función definida por el modelo como un método en un objeto <xref:System.Data.Objects.ObjectContext>.</span><span class="sxs-lookup"><span data-stu-id="4c672-135">The following example demonstrates how to call a model-defined function as a method on an <xref:System.Data.Objects.ObjectContext> object.</span></span> <span data-ttu-id="4c672-136">En el ejemplo se usa el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span><span class="sxs-lookup"><span data-stu-id="4c672-136">The example uses the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span>  
  
 <span data-ttu-id="4c672-137">Observe la función de modelo conceptual siguiente que devuelve los ingresos obtenidos para un producto determinado.</span><span class="sxs-lookup"><span data-stu-id="4c672-137">Consider the conceptual model function below that returns product revenue for a specified product.</span></span> <span data-ttu-id="4c672-138">(Para obtener información sobre cómo agregar la función al modelo conceptual, vea [Cómo: definir funciones personalizadas en el modelo conceptual](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))).</span><span class="sxs-lookup"><span data-stu-id="4c672-138">(For information about adding the function to your conceptual model, see [How to: Define Custom Functions in the Conceptual Model](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).)</span></span>  
  
 [!code-xml[DP L2E Methods on ObjectContext#4](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp l2e methods on objectcontext/xml/adventureworks.edmx#4)]  

## <a name="example"></a><span data-ttu-id="4c672-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4c672-139">Example</span></span>  

 <span data-ttu-id="4c672-140">El código siguiente agrega un método a la clase `AdventureWorksEntities` que se asigna a la función de modelo conceptual anterior.</span><span class="sxs-lookup"><span data-stu-id="4c672-140">The following code adds a method to the `AdventureWorksEntities` class that maps to the conceptual model function above.</span></span>  
  
 [!code-csharp[DP L2E Methods on ObjectContext#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#2)]
 [!code-vb[DP L2E Methods on ObjectContext#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/class1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="4c672-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4c672-141">Example</span></span>  

 <span data-ttu-id="4c672-142">El código siguiente llama al método anterior para mostrar los ingresos obtenidos para un producto determinado:</span><span class="sxs-lookup"><span data-stu-id="4c672-142">The following code calls the method above to display the product revenue for a specified product:</span></span>  
  
 [!code-csharp[DP L2E Methods on ObjectContext#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#3)]
 [!code-vb[DP L2E Methods on ObjectContext#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/module1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="4c672-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4c672-143">Example</span></span>  

 <span data-ttu-id="4c672-144">En el ejemplo siguiente se muestra cómo llamar a una función definida por el modelo que devuelve una colección (como un objeto <xref:System.Linq.IQueryable%601>).</span><span class="sxs-lookup"><span data-stu-id="4c672-144">The following example demonstrates how to call a model-defined function that returns a collection (as an <xref:System.Linq.IQueryable%601> object).</span></span> <span data-ttu-id="4c672-145">Observe la función de modelo conceptual siguiente que devuelve todos los `SalesOrderDetails` para un identificador de producto determinado.</span><span class="sxs-lookup"><span data-stu-id="4c672-145">Consider the conceptual model function below that returns all the `SalesOrderDetails` for a given product ID.</span></span>  
  
 [!code-xml[DP L2E Methods on ObjectContext#7](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp l2e methods on objectcontext/xml/adventureworks.edmx#7)]  
  
## <a name="example"></a><span data-ttu-id="4c672-146">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4c672-146">Example</span></span>  

 <span data-ttu-id="4c672-147">El código siguiente agrega un método a la clase `AdventureWorksEntities` que se asigna a la función de modelo conceptual anterior.</span><span class="sxs-lookup"><span data-stu-id="4c672-147">The following code adds a method to the `AdventureWorksEntities` class that maps to the conceptual model function above.</span></span>  
  
 [!code-csharp[DP L2E Methods on ObjectContext#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#8)]
 [!code-vb[DP L2E Methods on ObjectContext#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/class1.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="4c672-148">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4c672-148">Example</span></span>  

 <span data-ttu-id="4c672-149">El código siguiente llama al método.</span><span class="sxs-lookup"><span data-stu-id="4c672-149">The following code calls the method.</span></span> <span data-ttu-id="4c672-150">Observe que la consulta <xref:System.Linq.IQueryable%601> devuelta se redefine para devolver los totales de línea para cada `SalesOrderDetail`.</span><span class="sxs-lookup"><span data-stu-id="4c672-150">Note that the returned <xref:System.Linq.IQueryable%601> query is further refined to return line totals for each `SalesOrderDetail`.</span></span>  
  
 [!code-csharp[DP L2E Methods on ObjectContext#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#9)]
 [!code-vb[DP L2E Methods on ObjectContext#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/module1.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="4c672-151">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4c672-151">Example</span></span>  

 <span data-ttu-id="4c672-152">**Llamar a una función definida por el modelo como un método estático en una clase personalizada**</span><span class="sxs-lookup"><span data-stu-id="4c672-152">**Calling a Model-Defined Function as a Static Method on a Custom Class**</span></span>  
  
 <span data-ttu-id="4c672-153">En el ejemplo siguiente se muestra cómo llamar a una función definida por el modelo como un método estático en una clase personalizada.</span><span class="sxs-lookup"><span data-stu-id="4c672-153">The next example demonstrates how to call a model-defined function as a static method on a custom class.</span></span> <span data-ttu-id="4c672-154">En el ejemplo se usa el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span><span class="sxs-lookup"><span data-stu-id="4c672-154">The example uses the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4c672-155">Cuando se llama a una función definida por el modelo como un método estático en una clase personalizada, la función debe aceptar una colección y devolver una agregación de valores de la colección.</span><span class="sxs-lookup"><span data-stu-id="4c672-155">When you call a model-defined function as a static method on a custom class, the model-defined function must accept a collection and return an aggregation of values in the collection.</span></span>  
  
 <span data-ttu-id="4c672-156">Considere la función de modelo conceptual siguiente que devuelve los ingresos de los productos para una colección SalesOrderDetail.</span><span class="sxs-lookup"><span data-stu-id="4c672-156">Consider the conceptual model function below that returns product revenue for a SalesOrderDetail collection.</span></span> <span data-ttu-id="4c672-157">(Para obtener información sobre cómo agregar la función al modelo conceptual, vea [Cómo: definir funciones personalizadas en el modelo conceptual](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))).</span><span class="sxs-lookup"><span data-stu-id="4c672-157">(For information about adding the function to your conceptual model, see [How to: Define Custom Functions in the Conceptual Model](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).).</span></span>  
  
 [!code-xml[DP L2E Methods on ObjectContext#1](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp l2e methods on objectcontext/xml/adventureworks.edmx#1)]
  
## <a name="example"></a><span data-ttu-id="4c672-158">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4c672-158">Example</span></span>  

 <span data-ttu-id="4c672-159">El código siguiente agrega una clase a la aplicación que contiene un método estático que se asigna a la función de modelo conceptual anterior.</span><span class="sxs-lookup"><span data-stu-id="4c672-159">The following code adds a class to your application that contains a static method that maps to the conceptual model function above.</span></span>  
  
 [!code-csharp[DP L2E Methods on ObjectContext#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#5)]
 [!code-vb[DP L2E Methods on ObjectContext#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/class1.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="4c672-160">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4c672-160">Example</span></span>  

 <span data-ttu-id="4c672-161">El código siguiente llama al método anterior para mostrar los ingresos de los productos para una colección SalesOrderDetail:</span><span class="sxs-lookup"><span data-stu-id="4c672-161">The following code calls the method above to display the product revenue for a SalesOrderDetail collection:</span></span>  
  
 [!code-csharp[DP L2E Methods on ObjectContext#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#6)]
 [!code-vb[DP L2E Methods on ObjectContext#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/module1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="4c672-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c672-162">See also</span></span>

- <span data-ttu-id="4c672-163">[.edmx, Información general sobre el archivo](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="4c672-163">[.edmx File Overview](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span></span>
- [<span data-ttu-id="4c672-164">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="4c672-164">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
- [<span data-ttu-id="4c672-165">Llamar a funciones en consultas de LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="4c672-165">Calling Functions in LINQ to Entities Queries</span></span>](calling-functions-in-linq-to-entities-queries.md)
