---
title: 'Cómo: Llamar a funciones de base de datos personalizadas'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4354e5eb-dd45-469d-97fb-1c495705ee59
ms.openlocfilehash: 4e7c94dce5b50fe93f00aaaa72206be3394faf62
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43542211"
---
# <a name="how-to-call-custom-database-functions"></a><span data-ttu-id="a51f2-102">Cómo: Llamar a funciones de base de datos personalizadas</span><span class="sxs-lookup"><span data-stu-id="a51f2-102">How to: Call Custom Database Functions</span></span>
<span data-ttu-id="a51f2-103">En este tema se describe cómo llamar a las funciones personalizadas definidas en la base de datos desde consultas LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="a51f2-103">This topic describes how to call custom functions that are defined in the database from within LINQ to Entities queries.</span></span>  
  
 <span data-ttu-id="a51f2-104">Las funciones de base de datos llamadas desde LINQ to Entities se ejecutan en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a51f2-104">Database functions that are called from LINQ to Entities queries are executed in the database.</span></span> <span data-ttu-id="a51f2-105">La ejecución de funciones en la base de datos puede mejorar el rendimiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a51f2-105">Executing functions in the database can improve application performance.</span></span>  
  
 <span data-ttu-id="a51f2-106">El procedimiento siguiente proporciona un esquema general para llamar a una función de base de datos personalizada.</span><span class="sxs-lookup"><span data-stu-id="a51f2-106">The procedure below provides a high-level outline for calling a custom database function.</span></span> <span data-ttu-id="a51f2-107">El ejemplo que sigue proporciona más detalles sobre los pasos del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="a51f2-107">The example that follows provides more detail about the steps in the procedure.</span></span>  
  
### <a name="to-call-custom-functions-that-are-defined-in-the-database"></a><span data-ttu-id="a51f2-108">Para llamar a funciones personalizadas definidas en la base de datos</span><span class="sxs-lookup"><span data-stu-id="a51f2-108">To call custom functions that are defined in the database</span></span>  
  
1.  <span data-ttu-id="a51f2-109">Cree una función personalizada en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a51f2-109">Create a custom function in your database.</span></span>  
  
     <span data-ttu-id="a51f2-110">Para obtener más información sobre cómo crear funciones personalizadas en SQL Server, vea [CREATE FUNCTION (Transact-SQL)](https://go.microsoft.com/fwlink/?LinkID=139871).</span><span class="sxs-lookup"><span data-stu-id="a51f2-110">For more information about creating custom functions in SQL Server, see [CREATE FUNCTION (Transact-SQL)](https://go.microsoft.com/fwlink/?LinkID=139871).</span></span>  
  
2.  <span data-ttu-id="a51f2-111">Declare una función en el lenguaje de definición de esquemas de almacenamiento (SSDL) del archivo .edmx.</span><span class="sxs-lookup"><span data-stu-id="a51f2-111">Declare a function in the store schema definition language (SSDL) of your .edmx file.</span></span> <span data-ttu-id="a51f2-112">El nombre de la función debe coincidir con el nombre de la función declarada en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a51f2-112">The name of the function must be the same as the name of the function declared in the database.</span></span>  
  
     <span data-ttu-id="a51f2-113">Para obtener más información, consulte [Function Element (SSDL)](https://msdn.microsoft.com/library/b60cfc3d-8b93-423e-8c99-b867256640a4).</span><span class="sxs-lookup"><span data-stu-id="a51f2-113">For more information, see [Function Element (SSDL)](https://msdn.microsoft.com/library/b60cfc3d-8b93-423e-8c99-b867256640a4).</span></span>  
  
3.  <span data-ttu-id="a51f2-114">Agregue un método correspondiente a una clase del código de la aplicación y aplique un atributo <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> al método. Tenga en cuenta que los parámetros <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> y <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> de dicho atributo son el nombre del espacio de nombres del modelo conceptual y el nombre de la función en el modelo conceptual, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="a51f2-114">Add a corresponding method to a class in your application code and apply a <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to the method Note that the <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> and <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> parameters of the attribute are the namespace name of the conceptual model and the function name in the conceptual model respectively.</span></span> <span data-ttu-id="a51f2-115">La resolución del nombre de la función para LINQ distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a51f2-115">Function name resolution for LINQ is case sensitive.</span></span>  
  
4.  <span data-ttu-id="a51f2-116">Llame al método en una consulta LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="a51f2-116">Call the method in a LINQ to Entities query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a51f2-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a51f2-117">Example</span></span>  
 <span data-ttu-id="a51f2-118">En el ejemplo siguiente se muestra cómo llamar a una función de base de datos personalizada desde una consulta LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="a51f2-118">The following example demonstrates how to call a custom database function from within a LINQ to Entities query.</span></span> <span data-ttu-id="a51f2-119">En el ejemplo se usa el modelo School.</span><span class="sxs-lookup"><span data-stu-id="a51f2-119">The example uses the School model.</span></span> <span data-ttu-id="a51f2-120">Para obtener información sobre el modelo School, vea [crear la base de datos de ejemplo School](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0) y [generar el archivo .edmx de School](https://msdn.microsoft.com/library/c48b3907-a8be-4fe6-884c-e95af1852758).</span><span class="sxs-lookup"><span data-stu-id="a51f2-120">For information about the School model, see [Creating the School Sample Database](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0) and [Generating the School .edmx File](https://msdn.microsoft.com/library/c48b3907-a8be-4fe6-884c-e95af1852758).</span></span>  
  
 <span data-ttu-id="a51f2-121">El código siguiente agrega la función `AvgStudentGrade` a la base de datos de ejemplo School.</span><span class="sxs-lookup"><span data-stu-id="a51f2-121">The following code adds the `AvgStudentGrade` function to the School sample database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a51f2-122">Los pasos para llamar a una función de base de datos personalizada son los mismos, independientemente del servidor de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="a51f2-122">The steps for calling a custom database function are the same regardless of the database server.</span></span> <span data-ttu-id="a51f2-123">Sin embargo, el código siguiente es específico para crear una función en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a51f2-123">However, the code below is specific to creating a function in a SQL Server database.</span></span> <span data-ttu-id="a51f2-124">El código para crear una función personalizada en otros servidores de bases de datos puede variar.</span><span class="sxs-lookup"><span data-stu-id="a51f2-124">The code for creating a custom function in other database servers might differ.</span></span>  
  
 [!code-sql[DP L2E MapToDBFunction#1](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp l2e maptodbfunction/tsql/create_avgstudentgrade.sql#1)]  
  
## <a name="example"></a><span data-ttu-id="a51f2-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a51f2-125">Example</span></span>  
 <span data-ttu-id="a51f2-126">A continuación, declare una función en el lenguaje de definición de esquemas de almacenamiento (SSDL) del archivo .edmx.</span><span class="sxs-lookup"><span data-stu-id="a51f2-126">Next, declare a function in the store schema definition language (SSDL) of your .edmx file.</span></span> <span data-ttu-id="a51f2-127">El código siguiente declara la función `AvgStudentGrade` en SSDL:</span><span class="sxs-lookup"><span data-stu-id="a51f2-127">the following code declares the `AvgStudentGrade` function in SSDL:</span></span>  
  
 [!code-xml[DP L2E MapToDBFunction#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/school.edmx#2)]  
  
## <a name="example"></a><span data-ttu-id="a51f2-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a51f2-128">Example</span></span>  
 <span data-ttu-id="a51f2-129">Ahora cree un método y asígneselo a la función declarada en SSDL.</span><span class="sxs-lookup"><span data-stu-id="a51f2-129">Now create a method and map it to the function declared in the SSDL.</span></span> <span data-ttu-id="a51f2-130">El método de la clase siguiente se asigna a dicha función usando un atributo <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="a51f2-130">The method in the following class is mapped to the function defined in the SSDL (above) by using an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span> <span data-ttu-id="a51f2-131">Cuando se llama a este método, se ejecuta la función correspondiente en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a51f2-131">When this method is called, the corresponding function in the database is executed.</span></span>  
  
 [!code-csharp[DP L2E MapToDBFunction#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#3)]
 [!code-vb[DP L2E MapToDBFunction#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="a51f2-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a51f2-132">Example</span></span>  
 <span data-ttu-id="a51f2-133">Por último, llame al método en una consulta LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="a51f2-133">Finally, call the method in a LINQ to Entities query.</span></span> <span data-ttu-id="a51f2-134">El código siguiente muestra en la consola los apellidos de los alumnos y sus notas medias:</span><span class="sxs-lookup"><span data-stu-id="a51f2-134">The following code displays students' last names and average grades to the console:</span></span>  
  
 [!code-csharp[DP L2E MapToDBFunction#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#4)]
 [!code-vb[DP L2E MapToDBFunction#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="a51f2-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="a51f2-135">See Also</span></span>  
 [<span data-ttu-id="a51f2-136">Introducción al archivo .edmx</span><span class="sxs-lookup"><span data-stu-id="a51f2-136">.edmx File Overview</span></span>](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [<span data-ttu-id="a51f2-137">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="a51f2-137">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
