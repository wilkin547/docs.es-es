---
description: Más información sobre cómo navegar por los objetos DataRelation
title: Navegar por objetos DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5e673f4-9b44-45ae-aaea-c504d1cc5d3e
ms.openlocfilehash: 72d5bbb282b3b43434e528390769e1203519e8e2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651813"
---
# <a name="navigating-datarelations"></a><span data-ttu-id="c792a-103">Navegar por objetos DataRelation</span><span class="sxs-lookup"><span data-stu-id="c792a-103">Navigating DataRelations</span></span>

<span data-ttu-id="c792a-104">Una de las principales funciones de una <xref:System.Data.DataRelation> es permitir la navegación de una <xref:System.Data.DataTable> a otra dentro de un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="c792a-104">One of the primary functions of a <xref:System.Data.DataRelation> is to allow navigation from one <xref:System.Data.DataTable> to another within a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="c792a-105">Esto permite recuperar todos los <xref:System.Data.DataRow> objetos relacionados en un **objeto DataTable** cuando se proporciona una única **DataRow** desde un **DataTable** relacionado.</span><span class="sxs-lookup"><span data-stu-id="c792a-105">This allows you to retrieve all the related <xref:System.Data.DataRow> objects in one **DataTable** when given a single **DataRow** from a related **DataTable**.</span></span> <span data-ttu-id="c792a-106">Por ejemplo, después de establecer una **DataRelation** entre una tabla de clientes y una tabla de pedidos, puede recuperar todas las filas de pedidos de una fila de cliente determinada mediante **GetChildRows**.</span><span class="sxs-lookup"><span data-stu-id="c792a-106">For example, after establishing a **DataRelation** between a table of customers and a table of orders, you can retrieve all the order rows for a particular customer row using **GetChildRows**.</span></span>  
  
 <span data-ttu-id="c792a-107">En el ejemplo de código siguiente se crea una **DataRelation** entre la tabla **Customers** y la tabla **Orders** de un **DataSet** y se devuelven todos los pedidos de cada cliente.</span><span class="sxs-lookup"><span data-stu-id="c792a-107">The following code example creates a **DataRelation** between the **Customers** table and the **Orders** table of a **DataSet** and returns all the orders for each customer.</span></span>  
  
 [!code-csharp[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/VB/source.vb#1)]  
  
 <span data-ttu-id="c792a-108">El ejemplo siguiente se basa en el anterior; se relacionan cuatro tablas y se navega por dichas relaciones.</span><span class="sxs-lookup"><span data-stu-id="c792a-108">The next example builds on the preceding example, relating four tables together and navigating those relationships.</span></span> <span data-ttu-id="c792a-109">Como en el ejemplo anterior, **CustomerID** relaciona la tabla **Customers** con la tabla **Orders** .</span><span class="sxs-lookup"><span data-stu-id="c792a-109">As in the previous example, **CustomerID** relates the **Customers** table to the **Orders** table.</span></span> <span data-ttu-id="c792a-110">Para cada cliente de la tabla **Customers** , se determinan todas las filas secundarias de la tabla **Orders** , con el fin de devolver el número de pedidos que tiene un cliente determinado y sus valores **OrderID** .</span><span class="sxs-lookup"><span data-stu-id="c792a-110">For each customer in the **Customers** table, all the child rows in the **Orders** table are determined, in order to return the number of orders a particular customer has and their **OrderID** values.</span></span>  
  
 <span data-ttu-id="c792a-111">El ejemplo expandido también devuelve los valores de las tablas **OrderDetails** y **Products** .</span><span class="sxs-lookup"><span data-stu-id="c792a-111">The expanded example also returns the values from the **OrderDetails** and **Products** tables.</span></span> <span data-ttu-id="c792a-112">La tabla **Orders** está relacionada con la tabla **OrderDetails** mediante **OrderID** para determinar, para cada pedido de cliente, qué productos y cantidades se han pedido.</span><span class="sxs-lookup"><span data-stu-id="c792a-112">The **Orders** table is related to the **OrderDetails** table using **OrderID** to determine, for each customer order, what products and quantities were ordered.</span></span> <span data-ttu-id="c792a-113">Dado que la tabla **OrderDetails** solo contiene el **ProductID** de un producto pedido, **OrderDetails** se relaciona con los **productos** que usan **ProductID** para devolver el **NombreProducto**.</span><span class="sxs-lookup"><span data-stu-id="c792a-113">Because the **OrderDetails** table only contains the **ProductID** of an ordered product, **OrderDetails** is related to **Products** using **ProductID** in order to return the **ProductName**.</span></span> <span data-ttu-id="c792a-114">En esta relación, la tabla **Products** es el elemento primario y la tabla **Order Details** es el elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="c792a-114">In this relation, the **Products** table is the parent and the **Order Details** table is the child.</span></span> <span data-ttu-id="c792a-115">Como resultado, al recorrer en iteración la tabla **OrderDetails** , se llama a **GetParentRow** para recuperar el valor **ProductName** relacionado.</span><span class="sxs-lookup"><span data-stu-id="c792a-115">As a result, when iterating through the **OrderDetails** table, **GetParentRow** is called to retrieve the related **ProductName** value.</span></span>  
  
 <span data-ttu-id="c792a-116">Tenga en cuenta que cuando se crea la **DataRelation** para las tablas **Customers** y **Orders** , no se especifica ningún valor para la marca **createConstraints** (el valor predeterminado es **true**).</span><span class="sxs-lookup"><span data-stu-id="c792a-116">Notice that when the **DataRelation** is created for the **Customers** and **Orders** tables, no value is specified for the **createConstraints** flag (the default is **true**).</span></span> <span data-ttu-id="c792a-117">Se supone que todas las filas de la tabla **Orders** tienen un valor **CustomerID** que existe en la tabla primaria **Customers** .</span><span class="sxs-lookup"><span data-stu-id="c792a-117">This assumes that all the rows in the **Orders** table have a **CustomerID** value that exists in the parent **Customers** table.</span></span> <span data-ttu-id="c792a-118">Si existe un **CustomerID** en la tabla **Orders** que no existe en la tabla **Customers** , <xref:System.Data.ForeignKeyConstraint> se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="c792a-118">If a **CustomerID** exists in the **Orders** table that does not exist in the **Customers** table, a <xref:System.Data.ForeignKeyConstraint> causes an exception to be thrown.</span></span>  
  
 <span data-ttu-id="c792a-119">Cuando la columna secundaria pueda contener valores que no contenga la columna primaria, establezca el marcador **createConstraints** en **false** al agregar la **DataRelation**.</span><span class="sxs-lookup"><span data-stu-id="c792a-119">When the child column might contain values that the parent column does not contain, set the **createConstraints** flag to **false** when adding the **DataRelation**.</span></span> <span data-ttu-id="c792a-120">En el ejemplo, el marcador **createConstraints** se establece en **false** para la **DataRelation** entre la tabla **Orders** y la tabla **OrderDetails** .</span><span class="sxs-lookup"><span data-stu-id="c792a-120">In the example, the **createConstraints** flag is set to **false** for the **DataRelation** between the **Orders** table and the **OrderDetails** table.</span></span> <span data-ttu-id="c792a-121">Esto permite que la aplicación devuelva todos los registros de la tabla **OrderDetails** y solo un subconjunto de registros de la tabla **Orders** sin generar una excepción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c792a-121">This enables the application to return all the records from the **OrderDetails** table and only a subset of records from the **Orders** table without generating a run-time exception.</span></span> <span data-ttu-id="c792a-122">El ejemplo ampliado genera el resultado con el siguiente formato.</span><span class="sxs-lookup"><span data-stu-id="c792a-122">The expanded sample generates output in the following format.</span></span>  
  
```output  
Customer ID: NORTS  
  Order ID: 10517  
        Order Date: 4/24/1997 12:00:00 AM  
           Product: Filo Mix  
          Quantity: 6  
           Product: Raclette Courdavault  
          Quantity: 4  
           Product: Outback Lager  
          Quantity: 6  
  Order ID: 11057  
        Order Date: 4/29/1998 12:00:00 AM  
           Product: Outback Lager  
          Quantity: 3  
```  
  
 <span data-ttu-id="c792a-123">El siguiente ejemplo de código es un ejemplo ampliado en el que se devuelven los valores de las tablas **OrderDetails** y **Products** , con solo un subconjunto de los registros de la tabla **Orders** que se devuelve.</span><span class="sxs-lookup"><span data-stu-id="c792a-123">The following code example is an expanded sample where the values from the **OrderDetails** and **Products** tables are returned, with only a subset of the records in the **Orders** table being returned.</span></span>  
  
 [!code-csharp[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c792a-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="c792a-124">See also</span></span>

- [<span data-ttu-id="c792a-125">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="c792a-125">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="c792a-126">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c792a-126">ADO.NET Overview</span></span>](../ado-net-overview.md)
