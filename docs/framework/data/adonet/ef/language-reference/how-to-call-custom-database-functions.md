---
description: 'Más información acerca de cómo: llamar a funciones de base de datos personalizadas'
title: Procedimiento para llamar a funciones de base de datos personalizadas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4354e5eb-dd45-469d-97fb-1c495705ee59
ms.openlocfilehash: f33630f68740877ff2d0e7f0fec7202453d96bf7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696794"
---
# <a name="how-to-call-custom-database-functions"></a><span data-ttu-id="8a081-103">Procedimiento para llamar a funciones de base de datos personalizadas</span><span class="sxs-lookup"><span data-stu-id="8a081-103">How to: Call Custom Database Functions</span></span>

<span data-ttu-id="8a081-104">En este tema se describe cómo llamar a las funciones personalizadas definidas en la base de datos desde consultas LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="8a081-104">This topic describes how to call custom functions that are defined in the database from within LINQ to Entities queries.</span></span>

<span data-ttu-id="8a081-105">Las funciones de base de datos llamadas desde LINQ to Entities se ejecutan en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="8a081-105">Database functions that are called from LINQ to Entities queries are executed in the database.</span></span> <span data-ttu-id="8a081-106">La ejecución de funciones en la base de datos puede mejorar el rendimiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8a081-106">Executing functions in the database can improve application performance.</span></span>

<span data-ttu-id="8a081-107">El procedimiento siguiente proporciona un esquema general para llamar a una función de base de datos personalizada.</span><span class="sxs-lookup"><span data-stu-id="8a081-107">The procedure below provides a high-level outline for calling a custom database function.</span></span> <span data-ttu-id="8a081-108">El ejemplo que sigue proporciona más detalles sobre los pasos del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="8a081-108">The example that follows provides more detail about the steps in the procedure.</span></span>

## <a name="to-call-custom-functions-that-are-defined-in-the-database"></a><span data-ttu-id="8a081-109">Para llamar a funciones personalizadas definidas en la base de datos</span><span class="sxs-lookup"><span data-stu-id="8a081-109">To call custom functions that are defined in the database</span></span>

1. <span data-ttu-id="8a081-110">Cree una función personalizada en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="8a081-110">Create a custom function in your database.</span></span>

     <span data-ttu-id="8a081-111">Para obtener más información sobre cómo crear funciones personalizadas en SQL Server, vea [CREATE FUNCTION (Transact-SQL)](/sql/t-sql/statements/create-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8a081-111">For more information about creating custom functions in SQL Server, see [CREATE FUNCTION (Transact-SQL)](/sql/t-sql/statements/create-function-transact-sql).</span></span>

2. <span data-ttu-id="8a081-112">Declare una función en el lenguaje de definición de esquemas de almacenamiento (SSDL) del archivo .edmx.</span><span class="sxs-lookup"><span data-stu-id="8a081-112">Declare a function in the store schema definition language (SSDL) of your .edmx file.</span></span> <span data-ttu-id="8a081-113">El nombre de la función debe coincidir con el nombre de la función declarada en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="8a081-113">The name of the function must be the same as the name of the function declared in the database.</span></span>

     <span data-ttu-id="8a081-114">Para obtener más información, vea [elemento function (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#function-element-ssdl).</span><span class="sxs-lookup"><span data-stu-id="8a081-114">For more information, see [Function Element (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#function-element-ssdl).</span></span>

3. <span data-ttu-id="8a081-115">Agregue un método correspondiente a una clase del código de la aplicación y aplique un atributo <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> al método. Tenga en cuenta que los parámetros <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> y <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> de dicho atributo son el nombre del espacio de nombres del modelo conceptual y el nombre de la función en el modelo conceptual, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="8a081-115">Add a corresponding method to a class in your application code and apply a <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to the method Note that the <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> and <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> parameters of the attribute are the namespace name of the conceptual model and the function name in the conceptual model respectively.</span></span> <span data-ttu-id="8a081-116">La resolución del nombre de la función para LINQ distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="8a081-116">Function name resolution for LINQ is case sensitive.</span></span>

4. <span data-ttu-id="8a081-117">Llame al método en una consulta LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="8a081-117">Call the method in a LINQ to Entities query.</span></span>  

## <a name="example"></a><span data-ttu-id="8a081-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8a081-118">Example</span></span>

<span data-ttu-id="8a081-119">En el ejemplo siguiente se muestra cómo llamar a una función de base de datos personalizada desde una consulta LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="8a081-119">The following example demonstrates how to call a custom database function from within a LINQ to Entities query.</span></span> <span data-ttu-id="8a081-120">En el ejemplo se usa el modelo School.</span><span class="sxs-lookup"><span data-stu-id="8a081-120">The example uses the School model.</span></span> <span data-ttu-id="8a081-121">Para obtener información sobre el modelo School, vea [crear la base de datos de ejemplo School](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)) y [generar el archivo School. edmx](/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="8a081-121">For information about the School model, see [Creating the School Sample Database](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)) and [Generating the School .edmx File](/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100)).</span></span>

<span data-ttu-id="8a081-122">El código siguiente agrega la función `AvgStudentGrade` a la base de datos de ejemplo School.</span><span class="sxs-lookup"><span data-stu-id="8a081-122">The following code adds the `AvgStudentGrade` function to the School sample database.</span></span>

> [!NOTE]
> <span data-ttu-id="8a081-123">Los pasos para llamar a una función de base de datos personalizada son los mismos, independientemente del servidor de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="8a081-123">The steps for calling a custom database function are the same regardless of the database server.</span></span> <span data-ttu-id="8a081-124">Sin embargo, el código siguiente es específico para crear una función en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8a081-124">However, the code below is specific to creating a function in a SQL Server database.</span></span> <span data-ttu-id="8a081-125">El código para crear una función personalizada en otros servidores de bases de datos puede variar.</span><span class="sxs-lookup"><span data-stu-id="8a081-125">The code for creating a custom function in other database servers might differ.</span></span>

[!code-sql[DP L2E MapToDBFunction#1](~/samples/snippets/tsql/VS_Snippets_Data/dp l2e maptodbfunction/tsql/create_avgstudentgrade.sql#1)]

## <a name="example"></a><span data-ttu-id="8a081-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8a081-126">Example</span></span>

<span data-ttu-id="8a081-127">A continuación, declare una función en el lenguaje de definición de esquemas de almacenamiento (SSDL) del archivo *. edmx* .</span><span class="sxs-lookup"><span data-stu-id="8a081-127">Next, declare a function in the store schema definition language (SSDL) of your *.edmx* file.</span></span> <span data-ttu-id="8a081-128">El código siguiente declara la `AvgStudentGrade` función en SSDL:</span><span class="sxs-lookup"><span data-stu-id="8a081-128">The following code declares the `AvgStudentGrade` function in SSDL:</span></span>

[!code-xml[DP L2E MapToDBFunction#2](~/samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/school.edmx#2)]

## <a name="example"></a><span data-ttu-id="8a081-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8a081-129">Example</span></span>

<span data-ttu-id="8a081-130">Ahora, cree un método y asígnelo a la función declarada en el SSDL.</span><span class="sxs-lookup"><span data-stu-id="8a081-130">Now, create a method and map it to the function declared in the SSDL.</span></span> <span data-ttu-id="8a081-131">El método de la clase siguiente se asigna a dicha función usando un atributo <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="8a081-131">The method in the following class is mapped to the function defined in the SSDL (above) by using an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span> <span data-ttu-id="8a081-132">Cuando se llama a este método, se ejecuta la función correspondiente en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="8a081-132">When this method is called, the corresponding function in the database is executed.</span></span>

[!code-csharp[DP L2E MapToDBFunction#3](~/samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#3)]
[!code-vb[DP L2E MapToDBFunction#3](~/samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#3)]

## <a name="example"></a><span data-ttu-id="8a081-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8a081-133">Example</span></span>

<span data-ttu-id="8a081-134">Por último, llame al método en una consulta LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="8a081-134">Finally, call the method in a LINQ to Entities query.</span></span> <span data-ttu-id="8a081-135">El código siguiente muestra en la consola los apellidos de los alumnos y sus notas medias:</span><span class="sxs-lookup"><span data-stu-id="8a081-135">The following code displays students' last names and average grades to the console:</span></span>

[!code-csharp[DP L2E MapToDBFunction#4](~/samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#4)]
[!code-vb[DP L2E MapToDBFunction#4](~/samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#4)]

## <a name="see-also"></a><span data-ttu-id="8a081-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a081-136">See also</span></span>

- <span data-ttu-id="8a081-137">[.edmx, Información general sobre el archivo](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8a081-137">[.edmx File Overview](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span></span>
- [<span data-ttu-id="8a081-138">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="8a081-138">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
