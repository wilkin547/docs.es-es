---
title: Oracle y ADO.NET
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8ee8e389-53cf-45cf-80bd-1df63ef34f2e
ms.openlocfilehash: 5683f2b4ba57021ff6dda3a51baca016f886b605
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980085"
---
# <a name="oracle-and-adonet"></a><span data-ttu-id="014d9-102">Oracle y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="014d9-102">Oracle and ADO.NET</span></span>
> [!NOTE]
> <span data-ttu-id="014d9-103">Los tipos de <xref:System.Data.OracleClient> están en desuso.</span><span class="sxs-lookup"><span data-stu-id="014d9-103">The types in <xref:System.Data.OracleClient> are deprecated.</span></span> <span data-ttu-id="014d9-104">Los tipos seguirán estando admitidos en la versión actual de .NET Framework, pero se quitarán en una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="014d9-104">The types remain supported in the current version of.NET Framework but will be removed in a future release.</span></span> <span data-ttu-id="014d9-105">Microsoft recomienda usar un proveedor de Oracle de otro fabricante.</span><span class="sxs-lookup"><span data-stu-id="014d9-105">Microsoft recommends that you use a third-party Oracle provider.</span></span>  
  
 <span data-ttu-id="014d9-106">En esta sección se describen características y comportamientos específicos del proveedor de datos de .NET Framework para Oracle.</span><span class="sxs-lookup"><span data-stu-id="014d9-106">This section describes features and behaviors that are specific to the .NET Framework Data Provider for Oracle.</span></span>  
  
 <span data-ttu-id="014d9-107">El proveedor de datos de .NET Framework para Oracle proporciona acceso a una base de datos de Oracle mediante Oracle Call Interface (OCI), tal y como lo proporciona el software cliente de Oracle.</span><span class="sxs-lookup"><span data-stu-id="014d9-107">The .NET Framework Data Provider for Oracle provides access to an Oracle database using the Oracle Call Interface (OCI) as provided by Oracle Client software.</span></span> <span data-ttu-id="014d9-108">La funcionalidad del proveedor de datos está diseñada para ser similar a la de los .NET Framework proveedores de datos para SQL Server, OLE DB y ODBC.</span><span class="sxs-lookup"><span data-stu-id="014d9-108">The functionality of the data provider is designed to be similar to that of the .NET Framework data providers for SQL Server, OLE DB, and ODBC.</span></span>  
  
 <span data-ttu-id="014d9-109">Para utilizar el proveedor de datos de .NET Framework para Oracle, una aplicación debe hacer referencia al espacio de nombres <xref:System.Data.OracleClient> como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="014d9-109">To use the .NET Framework Data Provider for Oracle, an application must reference the <xref:System.Data.OracleClient> namespace as follows:</span></span>  
  
```vb  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data.OracleClient;  
```  
  
 <span data-ttu-id="014d9-110">También debe incluir una referencia a la DLL cuando compile el código.</span><span class="sxs-lookup"><span data-stu-id="014d9-110">You also must include a reference to the DLL when you compile your code.</span></span> <span data-ttu-id="014d9-111">Por ejemplo, si compila un programa C#, la línea de comandos debe incluir:</span><span class="sxs-lookup"><span data-stu-id="014d9-111">For example, if you are compiling a C# program, your command line should include:</span></span>  
  
```console
csc /r:System.Data.OracleClient.dll  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="014d9-112">Esta sección</span><span class="sxs-lookup"><span data-stu-id="014d9-112">In This Section</span></span>  
 [<span data-ttu-id="014d9-113">Requisitos del sistema</span><span class="sxs-lookup"><span data-stu-id="014d9-113">System Requirements</span></span>](system-requirements-for-the-dotnet-data-provider-for-oracle.md)  
 <span data-ttu-id="014d9-114">Describe los requisitos para usar el proveedor de datos de .NET Framework para Oracle y describe una serie de problemas que se deben tener en cuenta al utilizarlos.</span><span class="sxs-lookup"><span data-stu-id="014d9-114">Describes requirements for using the .NET Framework Data Provider for Oracle, and describes a number of issues to be aware when using it.</span></span>  
  
 [<span data-ttu-id="014d9-115">Objetos BFILE de Oracle</span><span class="sxs-lookup"><span data-stu-id="014d9-115">Oracle BFILEs</span></span>](oracle-bfiles.md)  
 <span data-ttu-id="014d9-116">Describe la clase <xref:System.Data.OracleClient.OracleBFile>, que se utiliza para trabajar con el tipo de datos BFILE de Oracle.</span><span class="sxs-lookup"><span data-stu-id="014d9-116">Describes the <xref:System.Data.OracleClient.OracleBFile> class, which is used to work with the Oracle BFILE data type.</span></span>  
  
 [<span data-ttu-id="014d9-117">Objetos LOB de Oracle</span><span class="sxs-lookup"><span data-stu-id="014d9-117">Oracle LOBs</span></span>](oracle-lobs.md)  
 <span data-ttu-id="014d9-118">Describe la clase <xref:System.Data.OracleClient.OracleLob>, que se utiliza para trabajar con tipos de datos LOB de Oracle.</span><span class="sxs-lookup"><span data-stu-id="014d9-118">Describes the <xref:System.Data.OracleClient.OracleLob> class, which is used to work with Oracle LOB data types.</span></span>  
  
 [<span data-ttu-id="014d9-119">Parámetros REF CURSOR de Oracle</span><span class="sxs-lookup"><span data-stu-id="014d9-119">Oracle REF CURSORs</span></span>](oracle-ref-cursors.md)  
 <span data-ttu-id="014d9-120">Describe la compatibilidad con el tipo de datos REF CURSOR de Oracle.</span><span class="sxs-lookup"><span data-stu-id="014d9-120">Describes support for the Oracle REF CURSOR data type.</span></span>  
  
 [<span data-ttu-id="014d9-121">Tipos de Oracle</span><span class="sxs-lookup"><span data-stu-id="014d9-121">OracleTypes</span></span>](oracletypes.md)  
 <span data-ttu-id="014d9-122">Describe las estructuras que puede utilizar para trabajar con tipos de datos de Oracle, como <xref:System.Data.OracleClient.OracleNumber> y <xref:System.Data.OracleClient.OracleString>.</span><span class="sxs-lookup"><span data-stu-id="014d9-122">Describes structures you can use to work with Oracle data types, including <xref:System.Data.OracleClient.OracleNumber> and <xref:System.Data.OracleClient.OracleString>.</span></span>  
  
 [<span data-ttu-id="014d9-123">Secuencias de Oracle</span><span class="sxs-lookup"><span data-stu-id="014d9-123">Oracle Sequences</span></span>](oracle-sequences.md)  
 <span data-ttu-id="014d9-124">Describe la compatibilidad para recuperar los valores de clave de secuencia de Oracle que genera el servidor.</span><span class="sxs-lookup"><span data-stu-id="014d9-124">Describes support for retrieving the server-generated key Oracle Sequence values.</span></span>  
  
 [<span data-ttu-id="014d9-125">Asignaciones de tipos de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="014d9-125">Oracle Data Type Mappings</span></span>](oracle-data-type-mappings.md)  
 <span data-ttu-id="014d9-126">Enumera los tipos de datos de Oracle y sus asignaciones al <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="014d9-126">Lists Oracle data types and their mappings to the <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 [<span data-ttu-id="014d9-127">Transacciones distribuidas de Oracle</span><span class="sxs-lookup"><span data-stu-id="014d9-127">Oracle Distributed Transactions</span></span>](oracle-distributed-transactions.md)  
 <span data-ttu-id="014d9-128">Describe cómo se inscribe automáticamente el objeto <xref:System.Data.OracleClient.OracleConnection> en una transacción distribuida si se determina que hay una transacción activa.</span><span class="sxs-lookup"><span data-stu-id="014d9-128">Describes how the <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="014d9-129">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="014d9-129">Related Sections</span></span>  
 [<span data-ttu-id="014d9-130">Proteger aplicaciones de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="014d9-130">Securing ADO.NET Applications</span></span>](securing-ado-net-applications.md)  
 <span data-ttu-id="014d9-131">Describe algunas recomendaciones de codificación segura para utilizar ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="014d9-131">Describes secure coding practices when using ADO.NET.</span></span>  
  
 [<span data-ttu-id="014d9-132">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="014d9-132">DataSets, DataTables, and DataViews</span></span>](./dataset-datatable-dataview/index.md)  
 <span data-ttu-id="014d9-133">Describe cómo crear y usar `DataSets`, `DataSets` con establecimiento de tipos, `DataTables` y `DataViews`.</span><span class="sxs-lookup"><span data-stu-id="014d9-133">Describes how to create and use `DataSets`, typed `DataSets`, `DataTables`, and `DataViews`.</span></span>  
  
 [<span data-ttu-id="014d9-134">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="014d9-134">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)  
 <span data-ttu-id="014d9-135">Describe cómo trabajar con datos XML en ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="014d9-135">Describes how to work with data in ADO.NET.</span></span>  
  
 [<span data-ttu-id="014d9-136">SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="014d9-136">SQL Server and ADO.NET</span></span>](./sql/index.md)  
 <span data-ttu-id="014d9-137">Describe cómo trabajar con las características y la funcionalidad específicas de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="014d9-137">Describes how to work with features and functionality that are specific to SQL Server.</span></span>  
  
 [<span data-ttu-id="014d9-138">Objetos DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="014d9-138">DbProviderFactories</span></span>](dbproviderfactories.md)  
 <span data-ttu-id="014d9-139">Describe clases genéricas que permiten escribir código independiente del proveedor en ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="014d9-139">Describes generic classes that allow you to write provider-independent code in ADO.NET.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="014d9-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="014d9-140">See also</span></span>

- [<span data-ttu-id="014d9-141">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="014d9-141">ADO.NET</span></span>](index.md)
- [<span data-ttu-id="014d9-142">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="014d9-142">ADO.NET Overview</span></span>](ado-net-overview.md)
