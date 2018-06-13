---
title: LINQ to SQL ejemplo
ms.date: 03/30/2017
ms.assetid: 5f39db9e-0e62-42c9-8c98-bb8b54cec98c
ms.openlocfilehash: 3cfcaf3de1a22b8bb5505083f127a9888b99dbd8
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
ms.locfileid: "33806723"
---
# <a name="linq-to-sql-sample"></a><span data-ttu-id="218ba-102">LINQ to SQL ejemplo</span><span class="sxs-lookup"><span data-stu-id="218ba-102">LINQ to SQL Sample</span></span>
<span data-ttu-id="218ba-103">En este ejemplo se muestra cómo crear una actividad para utilizar las entidades de consulta de LINQ to SQL de las tablas en bases de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="218ba-103">This sample demonstrates how to create an activity to use LINQ to SQL query entities from tables in SQL Server databases.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="218ba-104">Puede que los ejemplos WCF ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="218ba-104">The WCF samples may already be installed on your machine.</span></span> <span data-ttu-id="218ba-105">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="218ba-105">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\Samples\WCFWFCardspace`  
>   
>  <span data-ttu-id="218ba-106">Si este directorio no existe, haga clic en el vínculo de descarga de ejemplo en la parte superior de esta página.</span><span class="sxs-lookup"><span data-stu-id="218ba-106">If this directory does not exist, click the download sample link at the top of this page.</span></span> <span data-ttu-id="218ba-107">Tenga en cuenta que este vínculo descarga e instala todos los [!INCLUDE[wf1](../../../../includes/wf1-md.md)], WCF, y [!INCLUDE[infocard](../../../../includes/infocard-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="218ba-107">Note that this link downloads and installs all of the [!INCLUDE[wf1](../../../../includes/wf1-md.md)], WCF, and [!INCLUDE[infocard](../../../../includes/infocard-md.md)] samples.</span></span> <span data-ttu-id="218ba-108">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="218ba-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\Samples\WCFWFCardSpace\WF\Scenario\ActivityLibrary\Linq\LinqToSql`  
  
## <a name="activity-details-for-findinsqltable"></a><span data-ttu-id="218ba-109">Detalles de la actividad FindInSqlTable</span><span class="sxs-lookup"><span data-stu-id="218ba-109">Activity details for FindInSqlTable</span></span>  
 <span data-ttu-id="218ba-110">Esta actividad permite a los usuarios consultar entidades de las tablas de una base de datos utilizando LINQ to SQL.</span><span class="sxs-lookup"><span data-stu-id="218ba-110">This activity allows users to query entities from tables in a database using LINQ to SQL.</span></span> <span data-ttu-id="218ba-111">Los usuarios de la actividad también pueden proporcionar un predicado de LINQ en forma de expresión lambda para filtrar los resultados.</span><span class="sxs-lookup"><span data-stu-id="218ba-111">Users of the activity can also provide a LINQ predicate in the form of a lambda expression to filter the results.</span></span> <span data-ttu-id="218ba-112">Si no se proporciona ningún predicado, se devuelve la tabla completa.</span><span class="sxs-lookup"><span data-stu-id="218ba-112">If no predicate is provided, the entire table is returned.</span></span> <span data-ttu-id="218ba-113">En la siguiente tabla se detallan las propiedades y los valores devueltos de la actividad.</span><span class="sxs-lookup"><span data-stu-id="218ba-113">The following table details the property and return values for the activity.</span></span>  
  
|<span data-ttu-id="218ba-114">Propiedad o valor devuelto</span><span class="sxs-lookup"><span data-stu-id="218ba-114">Property or Return Value</span></span>|<span data-ttu-id="218ba-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="218ba-115">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="218ba-116">Propiedad `Collection`</span><span class="sxs-lookup"><span data-stu-id="218ba-116">`Collection` property</span></span>|<span data-ttu-id="218ba-117">Propiedad necesaria que especifica la colección de origen.</span><span class="sxs-lookup"><span data-stu-id="218ba-117">A required property that specifies the source collection.</span></span>|  
|<span data-ttu-id="218ba-118">Propiedad `Predicate`</span><span class="sxs-lookup"><span data-stu-id="218ba-118">`Predicate` property</span></span>|<span data-ttu-id="218ba-119">Propiedad necesaria que especifica el filtro para la colección en forma de expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="218ba-119">A required property that specifies the filter for the collection in the form of a lambda expression.</span></span>|  
|<span data-ttu-id="218ba-120">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="218ba-120">Return Value</span></span>|<span data-ttu-id="218ba-121">La colección filtrada.</span><span class="sxs-lookup"><span data-stu-id="218ba-121">The filtered collection.</span></span>|  
  
## <a name="code-sample-that-uses-the-custom-activity"></a><span data-ttu-id="218ba-122">Ejemplo de código que utiliza la actividad personalizada</span><span class="sxs-lookup"><span data-stu-id="218ba-122">Code Sample that uses the Custom Activity</span></span>  
 <span data-ttu-id="218ba-123">El siguiente ejemplo de código utiliza la actividad personalizada `FindInSqlTable` para encontrar todas las filas de una tabla de SQL Server denominada `Employee` donde la columna `Role` es igual a `SDE`.</span><span class="sxs-lookup"><span data-stu-id="218ba-123">The following code example uses the `FindInSqlTable` custom activity to find all rows in a SQL Server table named `Employee` where the `Role` column is equal to `SDE`.</span></span>  
  
```csharp  
new FindInSqlTable<Employee>   
{  
    ConnectionString = @"Data Source=.\SQLExpress;Initial Catalog=LinqToSqlSample;Integrated Security=True",                          
    Predicate = new LambdaValue<Func<Employee, bool>>(c => new Func<Employee, bool>(emp => emp.Role.Equals("SDE"))),  
    Result = new OutArgument<IList<Employee>>(employees)  
},  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="218ba-124">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="218ba-124">To use this sample</span></span>  
  
1.  <span data-ttu-id="218ba-125">Abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="218ba-125">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="218ba-126">Desplácese hasta la carpeta que contiene este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="218ba-126">Navigate to the folder that contains this sample.</span></span>  
  
3.  <span data-ttu-id="218ba-127">Ejecute el archivo de comandos Setup.cmd.</span><span class="sxs-lookup"><span data-stu-id="218ba-127">Run the Setup.cmd command file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="218ba-128">El script Setup.cmd intenta instalar la base de datos de ejemplo en la versión SQL Server Express del equipo local.</span><span class="sxs-lookup"><span data-stu-id="218ba-128">The Setup.cmd script attempts to install the sample database in your local machine SQL Server Express.</span></span> <span data-ttu-id="218ba-129">Si desea instalarla en otra instancia de SQL Server, edite Setup.cmd.</span><span class="sxs-lookup"><span data-stu-id="218ba-129">If you want to install it in other SQL server instance, edit Setup.cmd.</span></span>  
  
     <span data-ttu-id="218ba-130">El script Setup.cmd realiza las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="218ba-130">The Setup.cmd script does the following actions.:</span></span>  
  
    -   <span data-ttu-id="218ba-131">Crea una base de datos llamada LinqToSqlSample.</span><span class="sxs-lookup"><span data-stu-id="218ba-131">Creates a database called LinqToSqlSample.</span></span>  
  
    -   <span data-ttu-id="218ba-132">Crea una tabla Roles.</span><span class="sxs-lookup"><span data-stu-id="218ba-132">Creates a Roles table.</span></span>  
  
    -   <span data-ttu-id="218ba-133">Crea una tabla Employees.</span><span class="sxs-lookup"><span data-stu-id="218ba-133">Creates an Employees table.</span></span>  
  
    -   <span data-ttu-id="218ba-134">Inserta 3 registros en la tabla Roles.</span><span class="sxs-lookup"><span data-stu-id="218ba-134">Inserts 3 records into the Roles table.</span></span>  
  
    -   <span data-ttu-id="218ba-135">Inserta 12 registros en la tabla Employees.</span><span class="sxs-lookup"><span data-stu-id="218ba-135">Inserts 12 records into the Employees table.</span></span>  
  
4.  <span data-ttu-id="218ba-136">Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución LinqToSQL.sln.</span><span class="sxs-lookup"><span data-stu-id="218ba-136">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the LinqToSQL.sln solution file.</span></span>  
  
5.  <span data-ttu-id="218ba-137">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="218ba-137">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
6.  <span data-ttu-id="218ba-138">Presione F5 para ejecutar la solución.</span><span class="sxs-lookup"><span data-stu-id="218ba-138">To run the solution, press F5.</span></span>  
  
#### <a name="to-uninstall-the-linqtosql-sample-database"></a><span data-ttu-id="218ba-139">Para desinstalar la base de datos de ejemplo LinqToSql</span><span class="sxs-lookup"><span data-stu-id="218ba-139">To uninstall the LinqToSql sample database</span></span>  
  
1.  <span data-ttu-id="218ba-140">Abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="218ba-140">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="218ba-141">Desplácese hasta la carpeta que contiene este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="218ba-141">Navigate to the folder that contains this sample.</span></span>  
  
3.  <span data-ttu-id="218ba-142">Ejecute el archivo de comandos Cleanup.cmd.</span><span class="sxs-lookup"><span data-stu-id="218ba-142">Run the Cleanup.cmd command file.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="218ba-143">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="218ba-143">The samples may already be installed on your machine.</span></span> <span data-ttu-id="218ba-144">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="218ba-144">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="218ba-145">Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="218ba-145">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="218ba-146">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="218ba-146">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Liiinq\LinqToSql`  
  
## <a name="see-also"></a><span data-ttu-id="218ba-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="218ba-147">See Also</span></span>  
 [<span data-ttu-id="218ba-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="218ba-148">LINQ to SQL</span></span>](http://go.microsoft.com/fwlink/?LinkId=150376)  
 [<span data-ttu-id="218ba-149">Introducción (LINQ to SQL)</span><span class="sxs-lookup"><span data-stu-id="218ba-149">Getting Started (LINQ to SQL)</span></span>](http://go.microsoft.com/fwlink/?LinkId=150377)
