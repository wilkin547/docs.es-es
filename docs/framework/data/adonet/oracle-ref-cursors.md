---
description: 'Más información acerca de: CURSOres REF CURSOR de Oracle'
title: Parámetros REF CURSOR de Oracle
ms.date: 03/30/2017
ms.assetid: c6b25b8b-0bdd-41b2-9c7c-661f070c2247
ms.openlocfilehash: 0a9c5e95a9f0d2da74fd6a3db19f15699a3e2787
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99672457"
---
# <a name="oracle-ref-cursors"></a><span data-ttu-id="7a7e5-103">Parámetros REF CURSOR de Oracle</span><span class="sxs-lookup"><span data-stu-id="7a7e5-103">Oracle REF CURSORs</span></span>

<span data-ttu-id="7a7e5-104">El proveedor de datos de .NET Framework para Oracle admite el tipo de datos **ref cursor** de Oracle.</span><span class="sxs-lookup"><span data-stu-id="7a7e5-104">The .NET Framework Data Provider for Oracle supports the Oracle **REF CURSOR** data type.</span></span> <span data-ttu-id="7a7e5-105">Cuando utilice el proveedor de datos para trabajar con cursores REF CURSOR de Oracle, debe tener en cuenta los siguientes comportamientos.</span><span class="sxs-lookup"><span data-stu-id="7a7e5-105">When using the data provider to work with Oracle REF CURSORs, you should consider the following behaviors.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7a7e5-106">Algunos de ellos difieren de los del proveedor Microsoft OLE DB para Oracle (MSDAORA).</span><span class="sxs-lookup"><span data-stu-id="7a7e5-106">Some behaviors differ from those of the Microsoft OLE DB Provider for Oracle (MSDAORA).</span></span>  
  
- <span data-ttu-id="7a7e5-107">Por motivos de rendimiento, el proveedor de datos para Oracle no enlaza automáticamente los tipos de datos **ref cursor** , como hace MSDAORA, a menos que se especifiquen explícitamente.</span><span class="sxs-lookup"><span data-stu-id="7a7e5-107">For performance reasons, the Data Provider for Oracle does not automatically bind **REF CURSOR** data types, as MSDAORA does, unless you explicitly specify them.</span></span>  
  
- <span data-ttu-id="7a7e5-108">El proveedor de datos no admite ninguna secuencia de escape ODBC, lo que incluye el escape {resultset} usado para especificar parámetros REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="7a7e5-108">The data provider does not support any ODBC escape sequences, including the {resultset} escape used to specify REF CURSOR parameters.</span></span>  
  
- <span data-ttu-id="7a7e5-109">Para ejecutar un procedimiento almacenado que devuelve los CURSOres REF CURSOR, debe definir los parámetros de <xref:System.Data.OracleClient.OracleParameterCollection> con un <xref:System.Data.OracleClient.OracleType> de **cursor** y un <xref:System.Data.OracleClient.OracleParameter.Direction%2A> de **Output**.</span><span class="sxs-lookup"><span data-stu-id="7a7e5-109">To execute a stored procedure that returns REF CURSORs, you must define the parameters in the <xref:System.Data.OracleClient.OracleParameterCollection> with an <xref:System.Data.OracleClient.OracleType> of **Cursor** and a <xref:System.Data.OracleClient.OracleParameter.Direction%2A> of **Output**.</span></span> <span data-ttu-id="7a7e5-110">El proveedor de datos admite el enlace de cursores REF CURSOR sólo como parámetros de salida;</span><span class="sxs-lookup"><span data-stu-id="7a7e5-110">The data provider supports binding REF CURSORs as output parameters only.</span></span> <span data-ttu-id="7a7e5-111">no los admite como parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="7a7e5-111">The provider does not support REF CURSORs as input parameters.</span></span>  
  
- <span data-ttu-id="7a7e5-112">No se permite la obtención de un <xref:System.Data.OracleClient.OracleDataReader> del valor del parámetro.</span><span class="sxs-lookup"><span data-stu-id="7a7e5-112">Obtaining an <xref:System.Data.OracleClient.OracleDataReader> from the parameter value is not supported.</span></span> <span data-ttu-id="7a7e5-113">Los valores son del tipo <xref:System.DBNull> después de la ejecución del comando.</span><span class="sxs-lookup"><span data-stu-id="7a7e5-113">The values are of type <xref:System.DBNull> after command execution.</span></span>  
  
- <span data-ttu-id="7a7e5-114">El único valor de enumeración de **CommandBehavior** que funciona con cursores REF cursor (por ejemplo, al llamar a <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A> ) es **CloseConnection**; se omiten todos los demás.</span><span class="sxs-lookup"><span data-stu-id="7a7e5-114">The only **CommandBehavior** enumeration value that works with REF CURSORs (for example, when calling <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>) is **CloseConnection**; all others are ignored.</span></span>  
  
- <span data-ttu-id="7a7e5-115">El orden de los CURSOres REF CURSOR en el objeto **OracleDataReader** depende del orden de los parámetros de **OracleParameterCollection**.</span><span class="sxs-lookup"><span data-stu-id="7a7e5-115">The order of REF CURSORs in the **OracleDataReader** depends on the order of the parameters in the **OracleParameterCollection**.</span></span> <span data-ttu-id="7a7e5-116">Se omite la propiedad <xref:System.Data.OracleClient.OracleParameter.ParameterName%2A>.</span><span class="sxs-lookup"><span data-stu-id="7a7e5-116">The <xref:System.Data.OracleClient.OracleParameter.ParameterName%2A> property is ignored.</span></span>  
  
- <span data-ttu-id="7a7e5-117">No se admite el tipo de datos de la **tabla** PL/SQL.</span><span class="sxs-lookup"><span data-stu-id="7a7e5-117">The PL/SQL **TABLE** data type is not supported.</span></span> <span data-ttu-id="7a7e5-118">No obstante, los cursores REF CURSOR resultan más eficientes.</span><span class="sxs-lookup"><span data-stu-id="7a7e5-118">However, REF CURSORs are more efficient.</span></span> <span data-ttu-id="7a7e5-119">Si debe utilizar un tipo de datos de **tabla** , use el proveedor de datos OLE DB .net con MSDAORA.</span><span class="sxs-lookup"><span data-stu-id="7a7e5-119">If you must use a **TABLE** data type, use the OLE DB .NET Data Provider with MSDAORA.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7a7e5-120">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7a7e5-120">In This Section</span></span>  

 [<span data-ttu-id="7a7e5-121">Ejemplos de REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="7a7e5-121">REF CURSOR Examples</span></span>](ref-cursor-examples.md)  
 <span data-ttu-id="7a7e5-122">Contiene tres ejemplos en los que se muestra el uso de cursores REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="7a7e5-122">Contains three examples that demonstrate using REF CURSORs.</span></span>  
  
 [<span data-ttu-id="7a7e5-123">Parámetros REF CURSOR en un objeto OracleDataReader</span><span class="sxs-lookup"><span data-stu-id="7a7e5-123">REF CURSOR Parameters in an OracleDataReader</span></span>](ref-cursor-parameters-in-an-oracledatareader.md)  
 <span data-ttu-id="7a7e5-124">Muestra cómo ejecutar un procedimiento almacenado PL/SQL que devuelve un parámetro REF CURSOR y lee el valor como **OracleDataReader**.</span><span class="sxs-lookup"><span data-stu-id="7a7e5-124">Demonstrates how to execute a PL/SQL stored procedure that returns a REF CURSOR parameter, and reads the value as an **OracleDataReader**.</span></span>  
  
 [<span data-ttu-id="7a7e5-125">Recuperar datos desde varios parámetros REF CURSOR utilizando un objeto OracleDataReader</span><span class="sxs-lookup"><span data-stu-id="7a7e5-125">Retrieving Data from Multiple REF CURSORs Using an OracleDataReader</span></span>](retrieving-data-from-multiple-ref-cursors.md)  
 <span data-ttu-id="7a7e5-126">Muestra cómo ejecutar un procedimiento almacenado PL/SQL que devuelve dos parámetros REF CURSOR y Lee los valores mediante un **OracleDataReader**.</span><span class="sxs-lookup"><span data-stu-id="7a7e5-126">Demonstrates how to execute a PL/SQL stored procedure that returns two REF CURSOR parameters, and reads the values using an **OracleDataReader**.</span></span>  
  
 [<span data-ttu-id="7a7e5-127">Rellenar un conjunto de datos utilizando uno o varios parámetros REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="7a7e5-127">Filling a DataSet Using One or More REF CURSORs</span></span>](filling-a-dataset-using-one-or-more-ref-cursors.md)  
 <span data-ttu-id="7a7e5-128">Muestra cómo ejecutar un procedimiento almacenado PL/SQL que devuelve dos parámetros REF CURSOR y llena un <xref:System.Data.DataSet> con las filas que se devuelven.</span><span class="sxs-lookup"><span data-stu-id="7a7e5-128">Demonstrates how to execute a PL/SQL stored procedure that returns two REF CURSOR parameters, and fills a <xref:System.Data.DataSet> with the rows that are returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a7e5-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a7e5-129">See also</span></span>

- [<span data-ttu-id="7a7e5-130">Oracle y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7a7e5-130">Oracle and ADO.NET</span></span>](oracle-and-adonet.md)
- [<span data-ttu-id="7a7e5-131">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7a7e5-131">ADO.NET Overview</span></span>](ado-net-overview.md)
