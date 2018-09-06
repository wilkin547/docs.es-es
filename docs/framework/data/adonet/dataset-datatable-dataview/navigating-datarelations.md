---
title: Navegar por objetos DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5e673f4-9b44-45ae-aaea-c504d1cc5d3e
ms.openlocfilehash: 1819d468d12c03ce0c4faac11f4b20b8fe0f9c33
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43731279"
---
# <a name="navigating-datarelations"></a><span data-ttu-id="087e6-102">Navegar por objetos DataRelation</span><span class="sxs-lookup"><span data-stu-id="087e6-102">Navigating DataRelations</span></span>
<span data-ttu-id="087e6-103">Una de las principales funciones de una <xref:System.Data.DataRelation> es permitir la navegación de una <xref:System.Data.DataTable> a otra dentro de un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="087e6-103">One of the primary functions of a <xref:System.Data.DataRelation> is to allow navigation from one <xref:System.Data.DataTable> to another within a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="087e6-104">Esto le permite recuperar todos relacionado <xref:System.Data.DataRow> objetos en una **DataTable** cuando se especifica una sola **DataRow** desde un relacionados **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="087e6-104">This allows you to retrieve all the related <xref:System.Data.DataRow> objects in one **DataTable** when given a single **DataRow** from a related **DataTable**.</span></span> <span data-ttu-id="087e6-105">Por ejemplo, después de establecer un **DataRelation** entre una tabla de clientes y una tabla de pedidos, puede recuperar todas las filas de pedido para un cliente determinado de filas mediante **GetChildRows**.</span><span class="sxs-lookup"><span data-stu-id="087e6-105">For example, after establishing a **DataRelation** between a table of customers and a table of orders, you can retrieve all the order rows for a particular customer row using **GetChildRows**.</span></span>  
  
 <span data-ttu-id="087e6-106">En el ejemplo de código siguiente se crea un **DataRelation** entre el **clientes** tabla y el **pedidos** tabla de un **DataSet** y devuelve todos los pedidos de cada cliente.</span><span class="sxs-lookup"><span data-stu-id="087e6-106">The following code example creates a **DataRelation** between the **Customers** table and the **Orders** table of a **DataSet** and returns all the orders for each customer.</span></span>  
  
 [!code-csharp[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/VB/source.vb#1)]  
  
 <span data-ttu-id="087e6-107">El ejemplo siguiente se basa en el anterior; se relacionan cuatro tablas y se navega por dichas relaciones.</span><span class="sxs-lookup"><span data-stu-id="087e6-107">The next example builds on the preceding example, relating four tables together and navigating those relationships.</span></span> <span data-ttu-id="087e6-108">Como se muestra en el ejemplo anterior, **CustomerID** se relaciona con la **clientes** la tabla a la **pedidos** tabla.</span><span class="sxs-lookup"><span data-stu-id="087e6-108">As in the previous example, **CustomerID** relates the **Customers** table to the **Orders** table.</span></span> <span data-ttu-id="087e6-109">Para cada cliente en el **clientes** de tabla, todas las filas secundarias en el **pedidos** se determinan la tabla, con el fin de devolver el número de pedidos que tiene un cliente concreto y sus **OrderID** valores.</span><span class="sxs-lookup"><span data-stu-id="087e6-109">For each customer in the **Customers** table, all the child rows in the **Orders** table are determined, in order to return the number of orders a particular customer has and their **OrderID** values.</span></span>  
  
 <span data-ttu-id="087e6-110">El ejemplo ampliado también devuelve los valores de la **OrderDetails** y **productos** tablas.</span><span class="sxs-lookup"><span data-stu-id="087e6-110">The expanded example also returns the values from the **OrderDetails** and **Products** tables.</span></span> <span data-ttu-id="087e6-111">El **pedidos** tabla se relaciona con la **OrderDetails** tabla mediante **OrderID** para determinar, para cada pedido de cliente, qué productos y cantidades se pidieron.</span><span class="sxs-lookup"><span data-stu-id="087e6-111">The **Orders** table is related to the **OrderDetails** table using **OrderID** to determine, for each customer order, what products and quantities were ordered.</span></span> <span data-ttu-id="087e6-112">Dado que el **OrderDetails** tabla sólo contiene el **ProductID** de un producto pedido, **OrderDetails** está relacionado con **productos** uso de **ProductID** con el fin de devolver el **ProductName**.</span><span class="sxs-lookup"><span data-stu-id="087e6-112">Because the **OrderDetails** table only contains the **ProductID** of an ordered product, **OrderDetails** is related to **Products** using **ProductID** in order to return the **ProductName**.</span></span> <span data-ttu-id="087e6-113">En esta relación, el **productos** es la tabla primaria y la **Order Details** tabla es el elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="087e6-113">In this relation, the **Products** table is the parent and the **Order Details** table is the child.</span></span> <span data-ttu-id="087e6-114">Como resultado, al recorrer en iteración el **OrderDetails** tabla, **GetParentRow** se llama para recuperar el relacionados **ProductName** valor.</span><span class="sxs-lookup"><span data-stu-id="087e6-114">As a result, when iterating through the **OrderDetails** table, **GetParentRow** is called to retrieve the related **ProductName** value.</span></span>  
  
 <span data-ttu-id="087e6-115">Tenga en cuenta que, cuando el **DataRelation** se crea para el **clientes** y **pedidos** tablas, se especifica ningún valor para el **createConstraints**marca (el valor predeterminado es **true**).</span><span class="sxs-lookup"><span data-stu-id="087e6-115">Notice that when the **DataRelation** is created for the **Customers** and **Orders** tables, no value is specified for the **createConstraints** flag (the default is **true**).</span></span> <span data-ttu-id="087e6-116">Se supone que todas las filas de la **pedidos** tabla tiene un **CustomerID** valor que existe en el elemento primario **clientes** tabla.</span><span class="sxs-lookup"><span data-stu-id="087e6-116">This assumes that all the rows in the **Orders** table have a **CustomerID** value that exists in the parent **Customers** table.</span></span> <span data-ttu-id="087e6-117">Si un **CustomerID** existe en el **pedidos** tabla que no existe en el **clientes** tabla, un <xref:System.Data.ForeignKeyConstraint> hace que se produzca una excepción.</span><span class="sxs-lookup"><span data-stu-id="087e6-117">If a **CustomerID** exists in the **Orders** table that does not exist in the **Customers** table, a <xref:System.Data.ForeignKeyConstraint> causes an exception to be thrown.</span></span>  
  
 <span data-ttu-id="087e6-118">Cuando la columna secundaria pueda contener valores que no contiene la columna primaria, establezca la **createConstraints** marca **false** al agregar el **DataRelation**.</span><span class="sxs-lookup"><span data-stu-id="087e6-118">When the child column might contain values that the parent column does not contain, set the **createConstraints** flag to **false** when adding the **DataRelation**.</span></span> <span data-ttu-id="087e6-119">En el ejemplo, el **createConstraints** marca se establece en **false** para el **DataRelation** entre el **pedidos** tabla y el  **OrderDetails** tabla.</span><span class="sxs-lookup"><span data-stu-id="087e6-119">In the example, the **createConstraints** flag is set to **false** for the **DataRelation** between the **Orders** table and the **OrderDetails** table.</span></span> <span data-ttu-id="087e6-120">Esto permite que la aplicación devolver todos los registros de la **OrderDetails** tabla y solo un subconjunto de registros desde el **pedidos** tabla sin generar una excepción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="087e6-120">This enables the application to return all the records from the **OrderDetails** table and only a subset of records from the **Orders** table without generating a run-time exception.</span></span> <span data-ttu-id="087e6-121">El ejemplo ampliado genera el resultado con el siguiente formato.</span><span class="sxs-lookup"><span data-stu-id="087e6-121">The expanded sample generates output in the following format.</span></span>  
  
```  
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
  
 <span data-ttu-id="087e6-122">El ejemplo de código siguiente es un ejemplo ampliado donde los valores de la **OrderDetails** y **productos** se devuelven las tablas, con solo un subconjunto de los registros de la **pedidos**tabla que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="087e6-122">The following code example is an expanded sample where the values from the **OrderDetails** and **Products** tables are returned, with only a subset of the records in the **Orders** table being returned.</span></span>  
  
 [!code-csharp[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="087e6-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="087e6-123">See Also</span></span>  
 [<span data-ttu-id="087e6-124">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="087e6-124">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="087e6-125">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="087e6-125">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
