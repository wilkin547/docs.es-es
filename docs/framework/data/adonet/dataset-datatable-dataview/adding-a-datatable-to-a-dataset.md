---
title: Agregar un objeto DataTable a un objeto DataSet
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 556d29a3-8fc9-4e38-b3ee-c188f7e7b155
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f70292794866530de5b7abf7dac1edd09d300c94
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="adding-a-datatable-to-a-dataset"></a><span data-ttu-id="28ee6-102">Agregar un objeto DataTable a un objeto DataSet</span><span class="sxs-lookup"><span data-stu-id="28ee6-102">Adding a DataTable to a DataSet</span></span>
<span data-ttu-id="28ee6-103">ADO.NET permite crear objetos <xref:System.Data.DataTable> y agregarlos a un <xref:System.Data.DataSet> existente.</span><span class="sxs-lookup"><span data-stu-id="28ee6-103">ADO.NET enables you to create <xref:System.Data.DataTable> objects and add them to an existing <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="28ee6-104">Es posible establecer información de restricciones para una <xref:System.Data.DataTable> mediante las propiedades  <xref:System.Data.DataTable.PrimaryKey%2A> y <xref:System.Data.DataColumn.Unique%2A>.</span><span class="sxs-lookup"><span data-stu-id="28ee6-104">You can set constraint information for a <xref:System.Data.DataTable> by using the <xref:System.Data.DataTable.PrimaryKey%2A> and <xref:System.Data.DataColumn.Unique%2A> properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28ee6-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="28ee6-105">Example</span></span>  
 <span data-ttu-id="28ee6-106">En el siguiente ejemplo se construye un <xref:System.Data.DataSet>, se agrega un objeto <xref:System.Data.DataTable> nuevo al <xref:System.Data.DataSet> y, a continuación, se agregan tres objetos <xref:System.Data.DataColumn> a la tabla.</span><span class="sxs-lookup"><span data-stu-id="28ee6-106">The following example constructs a <xref:System.Data.DataSet>, adds a new <xref:System.Data.DataTable> object to the <xref:System.Data.DataSet>, and then adds three <xref:System.Data.DataColumn> objects to the table.</span></span> <span data-ttu-id="28ee6-107">Por ultimo, el código establece una columna como columna de clave principal.</span><span class="sxs-lookup"><span data-stu-id="28ee6-107">Finally, the code sets one column as the primary key column.</span></span>  
  
 [!code-csharp[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/VB/source.vb#1)]  
  
## <a name="case-sensitivity"></a><span data-ttu-id="28ee6-108">Distinción de mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="28ee6-108">Case Sensitivity</span></span>  
 <span data-ttu-id="28ee6-109">Pueden existir dos o más tablas o relaciones con el mismo nombre, pero que difieran en mayúsculas y minúsculas, en un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="28ee6-109">Two or more tables or relations with the same name, but different casing, can exist in a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="28ee6-110">En estos casos, las referencias a tablas y relaciones por nombre distinguen mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="28ee6-110">In such cases, references by name to tables and relations are case sensitive.</span></span> <span data-ttu-id="28ee6-111">Por ejemplo, si la <xref:System.Data.DataSet> **conjunto de datos** contiene tablas **Table1** y **table1**, debe hacer referencia a **Table1** por su nombre como **dataSet.Tables["Table1"]**, y **table1** como **dataSet.Tables["table1"]**.</span><span class="sxs-lookup"><span data-stu-id="28ee6-111">For example, if the <xref:System.Data.DataSet> **dataSet** contains tables **Table1** and **table1**, you would reference **Table1** by name as **dataSet.Tables["Table1"]**, and **table1** as **dataSet.Tables["table1"]**.</span></span> <span data-ttu-id="28ee6-112">Intentar hacer referencia a cualquiera de las tablas mediante **dataSet.Tables["TABLE1"]** generaría una excepción.</span><span class="sxs-lookup"><span data-stu-id="28ee6-112">Attempting to reference either of the tables as **dataSet.Tables["TABLE1"]** would generate an exception.</span></span>  
  
 <span data-ttu-id="28ee6-113">El comportamiento de distinción entre mayúsculas y minúsculas no se aplica si sólo hay una tabla o relación con un nombre concreto.</span><span class="sxs-lookup"><span data-stu-id="28ee6-113">The case-sensitivity behavior does not apply if only one table or relation has a particular name.</span></span> <span data-ttu-id="28ee6-114">Por ejemplo, si la <xref:System.Data.DataSet> sólo tiene **Table1**, se puede hacer referencia a él mediante **dataSet.Tables["TABLE1"]**.</span><span class="sxs-lookup"><span data-stu-id="28ee6-114">For example, if the <xref:System.Data.DataSet> has only **Table1**, you can reference it using **dataSet.Tables["TABLE1"]**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="28ee6-115">La propiedad <xref:System.Data.DataSet.CaseSensitive%2A> del <xref:System.Data.DataSet> no afecta a este comportamiento.</span><span class="sxs-lookup"><span data-stu-id="28ee6-115">The <xref:System.Data.DataSet.CaseSensitive%2A> property of the <xref:System.Data.DataSet> does not affect this behavior.</span></span> <span data-ttu-id="28ee6-116">La propiedad <xref:System.Data.DataSet.CaseSensitive%2A> se aplica a los datos del <xref:System.Data.DataSet> y afecta a la ordenación, la búsqueda, el filtrado, la aplicación de restricciones, etc.</span><span class="sxs-lookup"><span data-stu-id="28ee6-116">The <xref:System.Data.DataSet.CaseSensitive%2A> property applies to the data in the <xref:System.Data.DataSet> and affects sorting, searching, filtering, enforcing constraints, and so on.</span></span>  
  
## <a name="namespace-support"></a><span data-ttu-id="28ee6-117">Compatibilidad con los espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="28ee6-117">Namespace Support</span></span>  
 <span data-ttu-id="28ee6-118">En las versiones de ADO.NET anteriores a la versión 2.0, dos tablas no podían tener el mismo nombre, aunque se encontrasen en espacios de nombres diferentes.</span><span class="sxs-lookup"><span data-stu-id="28ee6-118">In versions of ADO.NET earlier than 2.0, two tables could not have the same name, even if they were in different namespaces.</span></span> <span data-ttu-id="28ee6-119">Esta limitación se quitó en ADO.NET 2.0.</span><span class="sxs-lookup"><span data-stu-id="28ee6-119">This limitation was removed in ADO.NET 2.0.</span></span> <span data-ttu-id="28ee6-120">Un <xref:System.Data.DataSet> puede contener dos tablas con el mismo valor de propiedad <xref:System.Data.DataTable.TableName%2A>, pero con valores de propiedad <xref:System.Data.DataTable.Namespace%2A> diferentes.</span><span class="sxs-lookup"><span data-stu-id="28ee6-120">A <xref:System.Data.DataSet> can contain two tables that have the same <xref:System.Data.DataTable.TableName%2A> property value but different <xref:System.Data.DataTable.Namespace%2A> property values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28ee6-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="28ee6-121">See Also</span></span>  
 [<span data-ttu-id="28ee6-122">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="28ee6-122">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="28ee6-123">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="28ee6-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
