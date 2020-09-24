---
title: Agregar un objeto DataTable a un objeto DataSet
description: Consulte este código de ejemplo para obtener información sobre cómo crear objetos DataTable y cómo agregarlos a un conjunto de DataSet existente en ADO.NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 556d29a3-8fc9-4e38-b3ee-c188f7e7b155
ms.openlocfilehash: 6a5e3a89870b3959a6ac042b93414694e8a6cc1c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164901"
---
# <a name="adding-a-datatable-to-a-dataset"></a><span data-ttu-id="ca1c1-103">Agregar un objeto DataTable a un objeto DataSet</span><span class="sxs-lookup"><span data-stu-id="ca1c1-103">Adding a DataTable to a DataSet</span></span>

<span data-ttu-id="ca1c1-104">ADO.NET permite crear objetos <xref:System.Data.DataTable> y agregarlos a un <xref:System.Data.DataSet> existente.</span><span class="sxs-lookup"><span data-stu-id="ca1c1-104">ADO.NET enables you to create <xref:System.Data.DataTable> objects and add them to an existing <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="ca1c1-105">Es posible establecer información de restricciones para una <xref:System.Data.DataTable> mediante las propiedades  <xref:System.Data.DataTable.PrimaryKey%2A> y <xref:System.Data.DataColumn.Unique%2A>.</span><span class="sxs-lookup"><span data-stu-id="ca1c1-105">You can set constraint information for a <xref:System.Data.DataTable> by using the <xref:System.Data.DataTable.PrimaryKey%2A> and <xref:System.Data.DataColumn.Unique%2A> properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca1c1-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ca1c1-106">Example</span></span>  

 <span data-ttu-id="ca1c1-107">En el siguiente ejemplo se construye un <xref:System.Data.DataSet>, se agrega un objeto <xref:System.Data.DataTable> nuevo al <xref:System.Data.DataSet> y, a continuación, se agregan tres objetos <xref:System.Data.DataColumn> a la tabla.</span><span class="sxs-lookup"><span data-stu-id="ca1c1-107">The following example constructs a <xref:System.Data.DataSet>, adds a new <xref:System.Data.DataTable> object to the <xref:System.Data.DataSet>, and then adds three <xref:System.Data.DataColumn> objects to the table.</span></span> <span data-ttu-id="ca1c1-108">Por ultimo, el código establece una columna como columna de clave principal.</span><span class="sxs-lookup"><span data-stu-id="ca1c1-108">Finally, the code sets one column as the primary key column.</span></span>  
  
 [!code-csharp[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/VB/source.vb#1)]  
  
## <a name="case-sensitivity"></a><span data-ttu-id="ca1c1-109">Distinción entre mayúsculas y minúsculas</span><span class="sxs-lookup"><span data-stu-id="ca1c1-109">Case Sensitivity</span></span>  

 <span data-ttu-id="ca1c1-110">Pueden existir dos o más tablas o relaciones con el mismo nombre, pero que difieran en mayúsculas y minúsculas, en un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="ca1c1-110">Two or more tables or relations with the same name, but different casing, can exist in a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="ca1c1-111">En estos casos, las referencias a tablas y relaciones por nombre distinguen mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="ca1c1-111">In such cases, references by name to tables and relations are case sensitive.</span></span> <span data-ttu-id="ca1c1-112">Por ejemplo, si el <xref:System.Data.DataSet> **conjunto de DataSet** contiene las tablas **Table1** y **Table1**, haría referencia a **tabla1** por nombre como **DataSet. Tables ["Table1"]** y **Table1** as **DataSet. Tables ["Table1"]**.</span><span class="sxs-lookup"><span data-stu-id="ca1c1-112">For example, if the <xref:System.Data.DataSet> **dataSet** contains tables **Table1** and **table1**, you would reference **Table1** by name as **dataSet.Tables["Table1"]**, and **table1** as **dataSet.Tables["table1"]**.</span></span> <span data-ttu-id="ca1c1-113">Al intentar hacer referencia a cualquiera de las tablas como **DataSet. Tables ["TABLE1"]** se generaría una excepción.</span><span class="sxs-lookup"><span data-stu-id="ca1c1-113">Attempting to reference either of the tables as **dataSet.Tables["TABLE1"]** would generate an exception.</span></span>  
  
 <span data-ttu-id="ca1c1-114">El comportamiento de distinción entre mayúsculas y minúsculas no se aplica si sólo hay una tabla o relación con un nombre concreto.</span><span class="sxs-lookup"><span data-stu-id="ca1c1-114">The case-sensitivity behavior does not apply if only one table or relation has a particular name.</span></span> <span data-ttu-id="ca1c1-115">Por ejemplo, si <xref:System.Data.DataSet> solo tiene **Table1**, puede hacer referencia a él mediante **DataSet. Tables ["Table1"]**.</span><span class="sxs-lookup"><span data-stu-id="ca1c1-115">For example, if the <xref:System.Data.DataSet> has only **Table1**, you can reference it using **dataSet.Tables["TABLE1"]**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ca1c1-116">La propiedad <xref:System.Data.DataSet.CaseSensitive%2A> del <xref:System.Data.DataSet> no afecta a este comportamiento.</span><span class="sxs-lookup"><span data-stu-id="ca1c1-116">The <xref:System.Data.DataSet.CaseSensitive%2A> property of the <xref:System.Data.DataSet> does not affect this behavior.</span></span> <span data-ttu-id="ca1c1-117">La propiedad <xref:System.Data.DataSet.CaseSensitive%2A> se aplica a los datos del <xref:System.Data.DataSet> y afecta a la ordenación, la búsqueda, el filtrado, la aplicación de restricciones, etc.</span><span class="sxs-lookup"><span data-stu-id="ca1c1-117">The <xref:System.Data.DataSet.CaseSensitive%2A> property applies to the data in the <xref:System.Data.DataSet> and affects sorting, searching, filtering, enforcing constraints, and so on.</span></span>  
  
## <a name="namespace-support"></a><span data-ttu-id="ca1c1-118">Compatibilidad con los espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="ca1c1-118">Namespace Support</span></span>  

 <span data-ttu-id="ca1c1-119">En las versiones de ADO.NET anteriores a la versión 2.0, dos tablas no podían tener el mismo nombre, aunque se encontrasen en espacios de nombres diferentes.</span><span class="sxs-lookup"><span data-stu-id="ca1c1-119">In versions of ADO.NET earlier than 2.0, two tables could not have the same name, even if they were in different namespaces.</span></span> <span data-ttu-id="ca1c1-120">Esta limitación se quitó en ADO.NET 2.0.</span><span class="sxs-lookup"><span data-stu-id="ca1c1-120">This limitation was removed in ADO.NET 2.0.</span></span> <span data-ttu-id="ca1c1-121">Un <xref:System.Data.DataSet> puede contener dos tablas con el mismo valor de propiedad <xref:System.Data.DataTable.TableName%2A>, pero con valores de propiedad <xref:System.Data.DataTable.Namespace%2A> diferentes.</span><span class="sxs-lookup"><span data-stu-id="ca1c1-121">A <xref:System.Data.DataSet> can contain two tables that have the same <xref:System.Data.DataTable.TableName%2A> property value but different <xref:System.Data.DataTable.Namespace%2A> property values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca1c1-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ca1c1-122">See also</span></span>

- [<span data-ttu-id="ca1c1-123">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="ca1c1-123">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="ca1c1-124">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ca1c1-124">ADO.NET Overview</span></span>](../ado-net-overview.md)
