---
title: Oracle y ADO.NET
description: Obtenga información sobre las características y los comportamientos del proveedor de datos de .NET Framework para Oracle, que proporciona acceso a una base de datos de Oracle mediante la interfaz de llamada de Oracle.
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8ee8e389-53cf-45cf-80bd-1df63ef34f2e
ms.openlocfilehash: 736b8dc5179a15ec219c1dae06b9ee6b5d6c3ef3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166630"
---
# <a name="oracle-and-adonet"></a><span data-ttu-id="bcefe-103">Oracle y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="bcefe-103">Oracle and ADO.NET</span></span>

> [!NOTE]
> <span data-ttu-id="bcefe-104">Los tipos de <xref:System.Data.OracleClient> están en desuso.</span><span class="sxs-lookup"><span data-stu-id="bcefe-104">The types in <xref:System.Data.OracleClient> are deprecated.</span></span> <span data-ttu-id="bcefe-105">Los tipos seguirán estando admitidos en la versión actual de .NET Framework, pero se quitarán en una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="bcefe-105">The types remain supported in the current version of.NET Framework but will be removed in a future release.</span></span> <span data-ttu-id="bcefe-106">Microsoft recomienda usar un proveedor de Oracle de otro fabricante.</span><span class="sxs-lookup"><span data-stu-id="bcefe-106">Microsoft recommends that you use a third-party Oracle provider.</span></span>  
  
 <span data-ttu-id="bcefe-107">En esta sección se describen características y comportamientos específicos del proveedor de datos de .NET Framework para Oracle.</span><span class="sxs-lookup"><span data-stu-id="bcefe-107">This section describes features and behaviors that are specific to the .NET Framework Data Provider for Oracle.</span></span>  
  
 <span data-ttu-id="bcefe-108">El proveedor de datos de .NET Framework para Oracle proporciona acceso a una base de datos de Oracle mediante Oracle Call Interface (OCI), tal y como lo proporciona el software cliente de Oracle.</span><span class="sxs-lookup"><span data-stu-id="bcefe-108">The .NET Framework Data Provider for Oracle provides access to an Oracle database using the Oracle Call Interface (OCI) as provided by Oracle Client software.</span></span> <span data-ttu-id="bcefe-109">La funcionalidad del proveedor de datos está diseñada para ser similar a la de los .NET Framework proveedores de datos para SQL Server, OLE DB y ODBC.</span><span class="sxs-lookup"><span data-stu-id="bcefe-109">The functionality of the data provider is designed to be similar to that of the .NET Framework data providers for SQL Server, OLE DB, and ODBC.</span></span>  
  
 <span data-ttu-id="bcefe-110">Para utilizar el proveedor de datos de .NET Framework para Oracle, una aplicación debe hacer referencia al espacio de nombres de la <xref:System.Data.OracleClient> siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="bcefe-110">To use the .NET Framework Data Provider for Oracle, an application must reference the <xref:System.Data.OracleClient> namespace as follows:</span></span>  
  
```vb  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data.OracleClient;  
```  
  
 <span data-ttu-id="bcefe-111">También debe incluir una referencia a la DLL cuando compile el código.</span><span class="sxs-lookup"><span data-stu-id="bcefe-111">You also must include a reference to the DLL when you compile your code.</span></span> <span data-ttu-id="bcefe-112">Por ejemplo, si compila un programa C#, la línea de comandos debe incluir:</span><span class="sxs-lookup"><span data-stu-id="bcefe-112">For example, if you are compiling a C# program, your command line should include:</span></span>  
  
```console
csc /r:System.Data.OracleClient.dll  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="bcefe-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="bcefe-113">In This Section</span></span>  

 [<span data-ttu-id="bcefe-114">Requisitos del sistema</span><span class="sxs-lookup"><span data-stu-id="bcefe-114">System Requirements</span></span>](system-requirements-for-the-dotnet-data-provider-for-oracle.md)  
 <span data-ttu-id="bcefe-115">Describe los requisitos para usar el proveedor de datos de .NET Framework para Oracle y describe una serie de problemas que se deben tener en cuenta al utilizarlos.</span><span class="sxs-lookup"><span data-stu-id="bcefe-115">Describes requirements for using the .NET Framework Data Provider for Oracle, and describes a number of issues to be aware when using it.</span></span>  
  
 [<span data-ttu-id="bcefe-116">Objetos BFILE de Oracle</span><span class="sxs-lookup"><span data-stu-id="bcefe-116">Oracle BFILEs</span></span>](oracle-bfiles.md)  
 <span data-ttu-id="bcefe-117">Describe la clase <xref:System.Data.OracleClient.OracleBFile>, que se utiliza para trabajar con el tipo de datos BFILE de Oracle.</span><span class="sxs-lookup"><span data-stu-id="bcefe-117">Describes the <xref:System.Data.OracleClient.OracleBFile> class, which is used to work with the Oracle BFILE data type.</span></span>  
  
 [<span data-ttu-id="bcefe-118">Objetos LOB de Oracle</span><span class="sxs-lookup"><span data-stu-id="bcefe-118">Oracle LOBs</span></span>](oracle-lobs.md)  
 <span data-ttu-id="bcefe-119">Describe la clase <xref:System.Data.OracleClient.OracleLob>, que se utiliza para trabajar con tipos de datos LOB de Oracle.</span><span class="sxs-lookup"><span data-stu-id="bcefe-119">Describes the <xref:System.Data.OracleClient.OracleLob> class, which is used to work with Oracle LOB data types.</span></span>  
  
 [<span data-ttu-id="bcefe-120">Parámetros REF CURSOR de Oracle</span><span class="sxs-lookup"><span data-stu-id="bcefe-120">Oracle REF CURSORs</span></span>](oracle-ref-cursors.md)  
 <span data-ttu-id="bcefe-121">Describe la compatibilidad con el tipo de datos REF CURSOR de Oracle.</span><span class="sxs-lookup"><span data-stu-id="bcefe-121">Describes support for the Oracle REF CURSOR data type.</span></span>  
  
 [<span data-ttu-id="bcefe-122">Tipos de Oracle</span><span class="sxs-lookup"><span data-stu-id="bcefe-122">OracleTypes</span></span>](oracletypes.md)  
 <span data-ttu-id="bcefe-123">Describe las estructuras que puede utilizar para trabajar con tipos de datos de Oracle, como <xref:System.Data.OracleClient.OracleNumber> y <xref:System.Data.OracleClient.OracleString>.</span><span class="sxs-lookup"><span data-stu-id="bcefe-123">Describes structures you can use to work with Oracle data types, including <xref:System.Data.OracleClient.OracleNumber> and <xref:System.Data.OracleClient.OracleString>.</span></span>  
  
 [<span data-ttu-id="bcefe-124">Secuencias de Oracle</span><span class="sxs-lookup"><span data-stu-id="bcefe-124">Oracle Sequences</span></span>](oracle-sequences.md)  
 <span data-ttu-id="bcefe-125">Describe la compatibilidad para recuperar los valores de clave de secuencia de Oracle que genera el servidor.</span><span class="sxs-lookup"><span data-stu-id="bcefe-125">Describes support for retrieving the server-generated key Oracle Sequence values.</span></span>  
  
 [<span data-ttu-id="bcefe-126">Asignaciones de tipos de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="bcefe-126">Oracle Data Type Mappings</span></span>](oracle-data-type-mappings.md)  
 <span data-ttu-id="bcefe-127">Enumera los tipos de datos de Oracle y sus asignaciones al <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="bcefe-127">Lists Oracle data types and their mappings to the <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 [<span data-ttu-id="bcefe-128">Transacciones distribuidas de Oracle</span><span class="sxs-lookup"><span data-stu-id="bcefe-128">Oracle Distributed Transactions</span></span>](oracle-distributed-transactions.md)  
 <span data-ttu-id="bcefe-129">Describe cómo se inscribe automáticamente el objeto <xref:System.Data.OracleClient.OracleConnection> en una transacción distribuida si se determina que hay una transacción activa.</span><span class="sxs-lookup"><span data-stu-id="bcefe-129">Describes how the <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="bcefe-130">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="bcefe-130">Related Sections</span></span>  

 [<span data-ttu-id="bcefe-131">Proteger aplicaciones de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="bcefe-131">Securing ADO.NET Applications</span></span>](securing-ado-net-applications.md)  
 <span data-ttu-id="bcefe-132">Describe algunas recomendaciones de codificación segura para utilizar ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="bcefe-132">Describes secure coding practices when using ADO.NET.</span></span>  
  
 [<span data-ttu-id="bcefe-133">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="bcefe-133">DataSets, DataTables, and DataViews</span></span>](./dataset-datatable-dataview/index.md)  
 <span data-ttu-id="bcefe-134">Describe cómo crear y usar `DataSets`, `DataSets` con establecimiento de tipos, `DataTables` y `DataViews`.</span><span class="sxs-lookup"><span data-stu-id="bcefe-134">Describes how to create and use `DataSets`, typed `DataSets`, `DataTables`, and `DataViews`.</span></span>  
  
 [<span data-ttu-id="bcefe-135">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="bcefe-135">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)  
 <span data-ttu-id="bcefe-136">Describe cómo trabajar con datos XML en ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="bcefe-136">Describes how to work with data in ADO.NET.</span></span>  
  
 [<span data-ttu-id="bcefe-137">SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="bcefe-137">SQL Server and ADO.NET</span></span>](./sql/index.md)  
 <span data-ttu-id="bcefe-138">Describe cómo trabajar con las características y la funcionalidad específicas de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bcefe-138">Describes how to work with features and functionality that are specific to SQL Server.</span></span>  
  
 [<span data-ttu-id="bcefe-139">Objetos DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="bcefe-139">DbProviderFactories</span></span>](dbproviderfactories.md)  
 <span data-ttu-id="bcefe-140">Describe clases genéricas que permiten escribir código independiente del proveedor en ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="bcefe-140">Describes generic classes that allow you to write provider-independent code in ADO.NET.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcefe-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bcefe-141">See also</span></span>

- [<span data-ttu-id="bcefe-142">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="bcefe-142">ADO.NET</span></span>](index.md)
- [<span data-ttu-id="bcefe-143">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="bcefe-143">ADO.NET Overview</span></span>](ado-net-overview.md)
