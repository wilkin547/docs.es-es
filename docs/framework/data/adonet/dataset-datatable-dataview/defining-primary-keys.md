---
title: Definir claves principales
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
ms.assetid: 2ea85959-e763-4669-8bd9-46a9dab894bd
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: a2ba353353b52e5a866887e7f0dc4b743e336bd0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="defining-primary-keys"></a><span data-ttu-id="ed17d-102">Definir claves principales</span><span class="sxs-lookup"><span data-stu-id="ed17d-102">Defining Primary Keys</span></span>
<span data-ttu-id="ed17d-103">Generalmente, una tabla de base de datos tiene una columna o grupo de columnas que identifican de manera exclusiva cada fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="ed17d-103">A database table commonly has a column or group of columns that uniquely identifies each row in the table.</span></span> <span data-ttu-id="ed17d-104">Esta columna o grupo de columnas de identificación se denomina clave principal.</span><span class="sxs-lookup"><span data-stu-id="ed17d-104">This identifying column or group of columns is called the primary key.</span></span>  
  
 <span data-ttu-id="ed17d-105">Cuando se identifica una sola <xref:System.Data.DataColumn> como el <xref:System.Data.DataTable.PrimaryKey%2A> para un <xref:System.Data.DataTable>, establece automáticamente la tabla el <xref:System.Data.DataColumn.AllowDBNull%2A> propiedad de la columna a **false** y la <xref:System.Data.DataColumn.Unique%2A> propiedad  **True**.</span><span class="sxs-lookup"><span data-stu-id="ed17d-105">When you identify a single <xref:System.Data.DataColumn> as the <xref:System.Data.DataTable.PrimaryKey%2A> for a <xref:System.Data.DataTable>, the table automatically sets the <xref:System.Data.DataColumn.AllowDBNull%2A> property of the column to **false** and the <xref:System.Data.DataColumn.Unique%2A> property to **true**.</span></span> <span data-ttu-id="ed17d-106">Para varias columnas las claves principales, solo el **AllowDBNull** propiedad se establece automáticamente en **false**.</span><span class="sxs-lookup"><span data-stu-id="ed17d-106">For multiple-column primary keys, only the **AllowDBNull** property is automatically set to **false**.</span></span>  
  
 <span data-ttu-id="ed17d-107">El **PrimaryKey** propiedad de un <xref:System.Data.DataTable> recibe como valor una matriz de uno o varios **DataColumn** objetos, como se muestra en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="ed17d-107">The **PrimaryKey** property of a <xref:System.Data.DataTable> receives as its value an array of one or more **DataColumn** objects, as shown in the following examples.</span></span> <span data-ttu-id="ed17d-108">En el primer ejemplo se define una sola columna como clave principal.</span><span class="sxs-lookup"><span data-stu-id="ed17d-108">The first example defines a single column as the primary key.</span></span>  
  
```vb  
workTable.PrimaryKey = New DataColumn() {workTable.Columns("CustID")}  
  
' Or  
  
Dim columns(1) As DataColumn  
columns(0) = workTable.Columns("CustID")  
workTable.PrimaryKey = columns  
```  
  
```csharp  
workTable.PrimaryKey = new DataColumn[] {workTable.Columns["CustID"]};  
  
// Or  
  
DataColumn[] columns = new DataColumn[1];  
columns[0] = workTable.Columns["CustID"];  
workTable.PrimaryKey = columns;  
```  
  
 <span data-ttu-id="ed17d-109">En el siguiente ejemplo se definen dos columnas como clave principal.</span><span class="sxs-lookup"><span data-stu-id="ed17d-109">The following example defines two columns as a primary key.</span></span>  
  
```vb  
workTable.PrimaryKey = New DataColumn() {workTable.Columns("CustLName"), _  
                                         workTable.Columns("CustFName")}  
  
' Or  
  
Dim keyColumn(2) As DataColumn  
keyColumn(0) = workTable.Columns("CustLName")  
keyColumn(1) = workTable.Columns("CustFName")  
workTable.PrimaryKey = keyColumn  
```  
  
```csharp  
workTable.PrimaryKey = new DataColumn[] {workTable.Columns["CustLName"],   
                                         workTable.Columns["CustFName"]};  
  
// Or  
  
DataColumn[] keyColumn = new DataColumn[2];  
keyColumn[0] = workTable.Columns["CustLName"];  
keyColumn[1] = workTable.Columns["CustFName"];  
workTable.PrimaryKey = keyColumn;  
```  
  
## <a name="see-also"></a><span data-ttu-id="ed17d-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed17d-110">See Also</span></span>  
 <xref:System.Data.DataTable>  
 [<span data-ttu-id="ed17d-111">Definición de esquema de DataTable</span><span class="sxs-lookup"><span data-stu-id="ed17d-111">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [<span data-ttu-id="ed17d-112">Objetos DataTable</span><span class="sxs-lookup"><span data-stu-id="ed17d-112">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="ed17d-113">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="ed17d-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
