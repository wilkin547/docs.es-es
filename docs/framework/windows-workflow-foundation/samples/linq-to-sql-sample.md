---
title: LINQ to SQL ejemplo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5f39db9e-0e62-42c9-8c98-bb8b54cec98c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 03805d8917d16752cd84838fe210540a68c3f905
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="linq-to-sql-sample"></a><span data-ttu-id="23c98-102">LINQ to SQL ejemplo</span><span class="sxs-lookup"><span data-stu-id="23c98-102">LINQ to SQL Sample</span></span>
<span data-ttu-id="23c98-103">En este ejemplo se muestra cómo crear una actividad para utilizar las entidades de consulta de LINQ to SQL de las tablas en bases de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="23c98-103">This sample demonstrates how to create an activity to use LINQ to SQL query entities from tables in SQL Server databases.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="23c98-104">Puede que los ejemplos de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="23c98-104">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] samples may already be installed on your machine.</span></span> <span data-ttu-id="23c98-105">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="23c98-105">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\Samples\WCFWFCardspace`  
>   
>  <span data-ttu-id="23c98-106">Si este directorio no existe, haga clic en el vínculo de descarga de ejemplo en la parte superior de esta página.</span><span class="sxs-lookup"><span data-stu-id="23c98-106">If this directory does not exist, click the download sample link at the top of this page.</span></span> <span data-ttu-id="23c98-107">Tenga en cuenta que este vínculo descarga e instala todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)], [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] e [!INCLUDE[infocard](../../../../includes/infocard-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23c98-107">Note that this link downloads and installs all of the [!INCLUDE[wf1](../../../../includes/wf1-md.md)], [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], and [!INCLUDE[infocard](../../../../includes/infocard-md.md)] samples.</span></span> <span data-ttu-id="23c98-108">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="23c98-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\Samples\WCFWFCardSpace\WF\Scenario\ActivityLibrary\Linq\LinqToSql`  
  
## <a name="activity-details-for-findinsqltable"></a><span data-ttu-id="23c98-109">Detalles de la actividad FindInSqlTable</span><span class="sxs-lookup"><span data-stu-id="23c98-109">Activity details for FindInSqlTable</span></span>  
 <span data-ttu-id="23c98-110">Esta actividad permite a los usuarios consultar entidades de las tablas de una base de datos utilizando LINQ to SQL.</span><span class="sxs-lookup"><span data-stu-id="23c98-110">This activity allows users to query entities from tables in a database using LINQ to SQL.</span></span> <span data-ttu-id="23c98-111">Los usuarios de la actividad también pueden proporcionar un predicado de LINQ en forma de expresión lambda para filtrar los resultados.</span><span class="sxs-lookup"><span data-stu-id="23c98-111">Users of the activity can also provide a LINQ predicate in the form of a lambda expression to filter the results.</span></span> <span data-ttu-id="23c98-112">Si no se proporciona ningún predicado, se devuelve la tabla completa.</span><span class="sxs-lookup"><span data-stu-id="23c98-112">If no predicate is provided, the entire table is returned.</span></span> <span data-ttu-id="23c98-113">En la siguiente tabla se detallan las propiedades y los valores devueltos de la actividad.</span><span class="sxs-lookup"><span data-stu-id="23c98-113">The following table details the property and return values for the activity.</span></span>  
  
|<span data-ttu-id="23c98-114">Propiedad o valor devuelto</span><span class="sxs-lookup"><span data-stu-id="23c98-114">Property or Return Value</span></span>|<span data-ttu-id="23c98-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="23c98-115">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="23c98-116">Propiedad `Collection`</span><span class="sxs-lookup"><span data-stu-id="23c98-116">`Collection` property</span></span>|<span data-ttu-id="23c98-117">Propiedad necesaria que especifica la colección de origen.</span><span class="sxs-lookup"><span data-stu-id="23c98-117">A required property that specifies the source collection.</span></span>|  
|<span data-ttu-id="23c98-118">Propiedad `Predicate`</span><span class="sxs-lookup"><span data-stu-id="23c98-118">`Predicate` property</span></span>|<span data-ttu-id="23c98-119">Propiedad necesaria que especifica el filtro para la colección en forma de expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="23c98-119">A required property that specifies the filter for the collection in the form of a lambda expression.</span></span>|  
|<span data-ttu-id="23c98-120">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="23c98-120">Return Value</span></span>|<span data-ttu-id="23c98-121">La colección filtrada.</span><span class="sxs-lookup"><span data-stu-id="23c98-121">The filtered collection.</span></span>|  
  
## <a name="code-sample-that-uses-the-custom-activity"></a><span data-ttu-id="23c98-122">Ejemplo de código que utiliza la actividad personalizada</span><span class="sxs-lookup"><span data-stu-id="23c98-122">Code Sample that uses the Custom Activity</span></span>  
 <span data-ttu-id="23c98-123">El siguiente ejemplo de código utiliza la actividad personalizada `FindInSqlTable` para encontrar todas las filas de una tabla de SQL Server denominada `Employee` donde la columna `Role` es igual a `SDE`.</span><span class="sxs-lookup"><span data-stu-id="23c98-123">The following code example uses the `FindInSqlTable` custom activity to find all rows in a SQL Server table named `Employee` where the `Role` column is equal to `SDE`.</span></span>  
  
```csharp  
new FindInSqlTable<Employee>   
{  
    ConnectionString = @"Data Source=.\SQLExpress;Initial Catalog=LinqToSqlSample;Integrated Security=True",                          
    Predicate = new LambdaValue<Func<Employee, bool>>(c => new Func<Employee, bool>(emp => emp.Role.Equals("SDE"))),  
    Result = new OutArgument<IList<Employee>>(employees)  
},  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="23c98-124">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="23c98-124">To use this sample</span></span>  
  
1.  <span data-ttu-id="23c98-125">Abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="23c98-125">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="23c98-126">Desplácese hasta la carpeta que contiene este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="23c98-126">Navigate to the folder that contains this sample.</span></span>  
  
3.  <span data-ttu-id="23c98-127">Ejecute el archivo de comandos Setup.cmd.</span><span class="sxs-lookup"><span data-stu-id="23c98-127">Run the Setup.cmd command file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="23c98-128">El script Setup.cmd intenta instalar la base de datos de ejemplo en la versión SQL Server Express del equipo local.</span><span class="sxs-lookup"><span data-stu-id="23c98-128">The Setup.cmd script attempts to install the sample database in your local machine SQL Server Express.</span></span> <span data-ttu-id="23c98-129">Si desea instalarla en otra instancia de SQL Server, edite Setup.cmd.</span><span class="sxs-lookup"><span data-stu-id="23c98-129">If you want to install it in other SQL server instance, edit Setup.cmd.</span></span>  
  
     <span data-ttu-id="23c98-130">El script Setup.cmd realiza las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="23c98-130">The Setup.cmd script does the following actions.:</span></span>  
  
    -   <span data-ttu-id="23c98-131">Crea una base de datos llamada LinqToSqlSample.</span><span class="sxs-lookup"><span data-stu-id="23c98-131">Creates a database called LinqToSqlSample.</span></span>  
  
    -   <span data-ttu-id="23c98-132">Crea una tabla Roles.</span><span class="sxs-lookup"><span data-stu-id="23c98-132">Creates a Roles table.</span></span>  
  
    -   <span data-ttu-id="23c98-133">Crea una tabla Employees.</span><span class="sxs-lookup"><span data-stu-id="23c98-133">Creates an Employees table.</span></span>  
  
    -   <span data-ttu-id="23c98-134">Inserta 3 registros en la tabla Roles.</span><span class="sxs-lookup"><span data-stu-id="23c98-134">Inserts 3 records into the Roles table.</span></span>  
  
    -   <span data-ttu-id="23c98-135">Inserta 12 registros en la tabla Employees.</span><span class="sxs-lookup"><span data-stu-id="23c98-135">Inserts 12 records into the Employees table.</span></span>  
  
4.  <span data-ttu-id="23c98-136">Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución LinqToSQL.sln.</span><span class="sxs-lookup"><span data-stu-id="23c98-136">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the LinqToSQL.sln solution file.</span></span>  
  
5.  <span data-ttu-id="23c98-137">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="23c98-137">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
6.  <span data-ttu-id="23c98-138">Presione F5 para ejecutar la solución.</span><span class="sxs-lookup"><span data-stu-id="23c98-138">To run the solution, press F5.</span></span>  
  
#### <a name="to-uninstall-the-linqtosql-sample-database"></a><span data-ttu-id="23c98-139">Para desinstalar la base de datos de ejemplo LinqToSql</span><span class="sxs-lookup"><span data-stu-id="23c98-139">To uninstall the LinqToSql sample database</span></span>  
  
1.  <span data-ttu-id="23c98-140">Abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="23c98-140">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="23c98-141">Desplácese hasta la carpeta que contiene este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="23c98-141">Navigate to the folder that contains this sample.</span></span>  
  
3.  <span data-ttu-id="23c98-142">Ejecute el archivo de comandos Cleanup.cmd.</span><span class="sxs-lookup"><span data-stu-id="23c98-142">Run the Cleanup.cmd command file.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="23c98-143">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="23c98-143">The samples may already be installed on your machine.</span></span> <span data-ttu-id="23c98-144">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="23c98-144">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="23c98-145">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="23c98-145">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="23c98-146">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="23c98-146">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Liiinq\LinqToSql`  
  
## <a name="see-also"></a><span data-ttu-id="23c98-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="23c98-147">See Also</span></span>  
 [<span data-ttu-id="23c98-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="23c98-148">LINQ to SQL</span></span>](http://go.microsoft.com/fwlink/?LinkId=150376)  
 [<span data-ttu-id="23c98-149">Introducción (LINQ to SQL)</span><span class="sxs-lookup"><span data-stu-id="23c98-149">Getting Started (LINQ to SQL)</span></span>](http://go.microsoft.com/fwlink/?LinkId=150377)
