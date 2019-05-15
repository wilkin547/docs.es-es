---
title: Oracle y ADO.NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8ee8e389-53cf-45cf-80bd-1df63ef34f2e
ms.openlocfilehash: a8668ee115a3babbdf1ef549a418187d2c5e26b8
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583408"
---
# <a name="oracle-and-adonet"></a><span data-ttu-id="a1440-102">Oracle y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a1440-102">Oracle and ADO.NET</span></span>
> [!NOTE]
>  <span data-ttu-id="a1440-103">Los tipos de <xref:System.Data.OracleClient> están en desuso.</span><span class="sxs-lookup"><span data-stu-id="a1440-103">The types in <xref:System.Data.OracleClient> are deprecated.</span></span> <span data-ttu-id="a1440-104">Los tipos seguirán estando admitidos en la versión actual de .NET Framework, pero se quitarán en una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="a1440-104">The types remain supported in the current version of.NET Framework but will be removed in a future release.</span></span> <span data-ttu-id="a1440-105">Microsoft recomienda usar un proveedor de Oracle de otro fabricante.</span><span class="sxs-lookup"><span data-stu-id="a1440-105">Microsoft recommends that you use a third-party Oracle provider.</span></span>  
  
 <span data-ttu-id="a1440-106">Esta sección describen las características y comportamientos que son específicos del proveedor de datos de .NET Framework para Oracle.</span><span class="sxs-lookup"><span data-stu-id="a1440-106">This section describes features and behaviors that are specific to the .NET Framework Data Provider for Oracle.</span></span>  
  
 <span data-ttu-id="a1440-107">El proveedor de datos de .NET Framework para Oracle proporciona acceso a una base de datos de Oracle mediante Oracle Call Interface (OCI) proporcionados por el software cliente de Oracle.</span><span class="sxs-lookup"><span data-stu-id="a1440-107">The .NET Framework Data Provider for Oracle provides access to an Oracle database using the Oracle Call Interface (OCI) as provided by Oracle Client software.</span></span> <span data-ttu-id="a1440-108">La funcionalidad del proveedor de datos está diseñada para ser similar de los proveedores de datos .NET Framework para SQL Server, OLE DB y ODBC.</span><span class="sxs-lookup"><span data-stu-id="a1440-108">The functionality of the data provider is designed to be similar to that of the .NET Framework data providers for SQL Server, OLE DB, and ODBC.</span></span>  
  
 <span data-ttu-id="a1440-109">Para usar el proveedor de datos de .NET Framework para Oracle, debe hacer referencia a una aplicación la <xref:System.Data.OracleClient> espacio de nombres como sigue:</span><span class="sxs-lookup"><span data-stu-id="a1440-109">To use the .NET Framework Data Provider for Oracle, an application must reference the <xref:System.Data.OracleClient> namespace as follows:</span></span>  
  
```vb  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data.OracleClient;  
```  
  
 <span data-ttu-id="a1440-110">También debe incluir una referencia a la DLL cuando compile el código.</span><span class="sxs-lookup"><span data-stu-id="a1440-110">You also must include a reference to the DLL when you compile your code.</span></span> <span data-ttu-id="a1440-111">Por ejemplo, si compila un programa C#, la línea de comandos debe incluir:</span><span class="sxs-lookup"><span data-stu-id="a1440-111">For example, if you are compiling a C# program, your command line should include:</span></span>  
  
```  
csc /r:System.Data.OracleClient.dll  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="a1440-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a1440-112">In This Section</span></span>  
 [<span data-ttu-id="a1440-113">Requisitos del sistema</span><span class="sxs-lookup"><span data-stu-id="a1440-113">System Requirements</span></span>](../../../../docs/framework/data/adonet/system-requirements-for-the-dotnet-data-provider-for-oracle.md)  
 <span data-ttu-id="a1440-114">Describe los requisitos para usar el proveedor de datos de .NET Framework para Oracle y una serie de problemas a tener en cuenta cuando se usa.</span><span class="sxs-lookup"><span data-stu-id="a1440-114">Describes requirements for using the .NET Framework Data Provider for Oracle, and describes a number of issues to be aware when using it.</span></span>  
  
 [<span data-ttu-id="a1440-115">Objetos BFILE de Oracle</span><span class="sxs-lookup"><span data-stu-id="a1440-115">Oracle BFILEs</span></span>](../../../../docs/framework/data/adonet/oracle-bfiles.md)  
 <span data-ttu-id="a1440-116">Describe la clase <xref:System.Data.OracleClient.OracleBFile>, que se utiliza para trabajar con el tipo de datos BFILE de Oracle.</span><span class="sxs-lookup"><span data-stu-id="a1440-116">Describes the <xref:System.Data.OracleClient.OracleBFile> class, which is used to work with the Oracle BFILE data type.</span></span>  
  
 [<span data-ttu-id="a1440-117">Objetos LOB de Oracle</span><span class="sxs-lookup"><span data-stu-id="a1440-117">Oracle LOBs</span></span>](../../../../docs/framework/data/adonet/oracle-lobs.md)  
 <span data-ttu-id="a1440-118">Describe la clase <xref:System.Data.OracleClient.OracleLob>, que se utiliza para trabajar con tipos de datos LOB de Oracle.</span><span class="sxs-lookup"><span data-stu-id="a1440-118">Describes the <xref:System.Data.OracleClient.OracleLob> class, which is used to work with Oracle LOB data types.</span></span>  
  
 [<span data-ttu-id="a1440-119">Parámetros REF CURSOR de Oracle</span><span class="sxs-lookup"><span data-stu-id="a1440-119">Oracle REF CURSORs</span></span>](../../../../docs/framework/data/adonet/oracle-ref-cursors.md)  
 <span data-ttu-id="a1440-120">Describe la compatibilidad con el tipo de datos REF CURSOR de Oracle.</span><span class="sxs-lookup"><span data-stu-id="a1440-120">Describes support for the Oracle REF CURSOR data type.</span></span>  
  
 [<span data-ttu-id="a1440-121">Tipos de Oracle</span><span class="sxs-lookup"><span data-stu-id="a1440-121">OracleTypes</span></span>](../../../../docs/framework/data/adonet/oracletypes.md)  
 <span data-ttu-id="a1440-122">Describe las estructuras que puede utilizar para trabajar con tipos de datos de Oracle, como <xref:System.Data.OracleClient.OracleNumber> y <xref:System.Data.OracleClient.OracleString>.</span><span class="sxs-lookup"><span data-stu-id="a1440-122">Describes structures you can use to work with Oracle data types, including <xref:System.Data.OracleClient.OracleNumber> and <xref:System.Data.OracleClient.OracleString>.</span></span>  
  
 [<span data-ttu-id="a1440-123">Secuencias de Oracle</span><span class="sxs-lookup"><span data-stu-id="a1440-123">Oracle Sequences</span></span>](../../../../docs/framework/data/adonet/oracle-sequences.md)  
 <span data-ttu-id="a1440-124">Describe la compatibilidad para recuperar los valores de clave de secuencia de Oracle que genera el servidor.</span><span class="sxs-lookup"><span data-stu-id="a1440-124">Describes support for retrieving the server-generated key Oracle Sequence values.</span></span>  
  
 [<span data-ttu-id="a1440-125">Asignaciones de tipos de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="a1440-125">Oracle Data Type Mappings</span></span>](../../../../docs/framework/data/adonet/oracle-data-type-mappings.md)  
 <span data-ttu-id="a1440-126">Enumera los tipos de datos de Oracle y sus asignaciones al <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="a1440-126">Lists Oracle data types and their mappings to the <xref:System.Data.OracleClient.OracleDataReader>.</span></span>  
  
 [<span data-ttu-id="a1440-127">Transacciones distribuidas de Oracle</span><span class="sxs-lookup"><span data-stu-id="a1440-127">Oracle Distributed Transactions</span></span>](../../../../docs/framework/data/adonet/oracle-distributed-transactions.md)  
 <span data-ttu-id="a1440-128">Describe cómo se inscribe automáticamente el objeto <xref:System.Data.OracleClient.OracleConnection> en una transacción distribuida si se determina que hay una transacción activa.</span><span class="sxs-lookup"><span data-stu-id="a1440-128">Describes how the <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a1440-129">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="a1440-129">Related Sections</span></span>  
 [<span data-ttu-id="a1440-130">Proteger aplicaciones de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a1440-130">Securing ADO.NET Applications</span></span>](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 <span data-ttu-id="a1440-131">Describe algunas recomendaciones de codificación segura para utilizar [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1440-131">Describes secure coding practices when using [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].</span></span>  
  
 [<span data-ttu-id="a1440-132">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="a1440-132">DataSets, DataTables, and DataViews</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 <span data-ttu-id="a1440-133">Describe cómo crear y usar `DataSets`, `DataSets` con establecimiento de tipos, `DataTables` y `DataViews`.</span><span class="sxs-lookup"><span data-stu-id="a1440-133">Describes how to create and use `DataSets`, typed `DataSets`, `DataTables`, and `DataViews`.</span></span>  
  
 [<span data-ttu-id="a1440-134">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a1440-134">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 <span data-ttu-id="a1440-135">Describe cómo trabajar con datos XML en ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="a1440-135">Describes how to work with data in ADO.NET.</span></span>  
  
 [<span data-ttu-id="a1440-136">SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a1440-136">SQL Server and ADO.NET</span></span>](../../../../docs/framework/data/adonet/sql/index.md)  
 <span data-ttu-id="a1440-137">Describe cómo trabajar con las características y la funcionalidad específicas de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a1440-137">Describes how to work with features and functionality that are specific to SQL Server.</span></span>  
  
 [<span data-ttu-id="a1440-138">Objetos DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="a1440-138">DbProviderFactories</span></span>](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 <span data-ttu-id="a1440-139">Describe clases genéricas que permiten escribir código independiente del proveedor en [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1440-139">Describes generic classes that allow you to write provider-independent code in [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1440-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1440-140">See also</span></span>

- [<span data-ttu-id="a1440-141">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a1440-141">ADO.NET</span></span>](../../../../docs/framework/data/adonet/index.md)
- [<span data-ttu-id="a1440-142">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="a1440-142">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
