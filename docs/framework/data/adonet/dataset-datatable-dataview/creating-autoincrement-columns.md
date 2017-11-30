---
title: "Crear columnas de incremento automático"
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
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 7bc71e3ae817bbdaf5dc14f22041e297cab949b8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="creating-autoincrement-columns"></a><span data-ttu-id="8f64f-102">Crear columnas de incremento automático</span><span class="sxs-lookup"><span data-stu-id="8f64f-102">Creating AutoIncrement Columns</span></span>
<span data-ttu-id="8f64f-103">Para garantizar que los valores de una columna son únicos, éstos se pueden establecer de manera que se incrementen automáticamente cuando se agregan filas a la tabla.</span><span class="sxs-lookup"><span data-stu-id="8f64f-103">To ensure unique column values, you can set the column values to increment automatically when new rows are added to the table.</span></span> <span data-ttu-id="8f64f-104">Para crear un incremento automático <xref:System.Data.DataColumn>, establezca el <xref:System.Data.DataColumn.AutoIncrement%2A> propiedad de la columna a **true**.</span><span class="sxs-lookup"><span data-stu-id="8f64f-104">To create an auto-incrementing <xref:System.Data.DataColumn>, set the <xref:System.Data.DataColumn.AutoIncrement%2A> property of the column to **true**.</span></span> <span data-ttu-id="8f64f-105">El <xref:System.Data.DataColumn> , a continuación, se inicia con el valor definido en el <xref:System.Data.DataColumn.AutoIncrementSeed%2A> propiedad y con cada fila agregada, el valor de la **AutoIncrement** columna aumenta según el valor definido en el <xref:System.Data.DataColumn.AutoIncrementStep%2A> propiedad de la columna.</span><span class="sxs-lookup"><span data-stu-id="8f64f-105">The <xref:System.Data.DataColumn> then starts with the value defined in the <xref:System.Data.DataColumn.AutoIncrementSeed%2A> property, and with each row added the value of the **AutoIncrement** column increases by the value defined in the <xref:System.Data.DataColumn.AutoIncrementStep%2A> property of the column.</span></span>  
  
 <span data-ttu-id="8f64f-106">Para **AutoIncrement** columnas, se recomienda que el <xref:System.Data.DataColumn.ReadOnly%2A> propiedad de la **DataColumn** establecerse en **true**.</span><span class="sxs-lookup"><span data-stu-id="8f64f-106">For **AutoIncrement** columns, we recommend that the <xref:System.Data.DataColumn.ReadOnly%2A> property of the **DataColumn** be set to **true**.</span></span>  
  
 <span data-ttu-id="8f64f-107">En el ejemplo siguiente se muestra cómo se crea una columna que comienza con un valor de 200 y va aumentando de tres en tres.</span><span class="sxs-lookup"><span data-stu-id="8f64f-107">The following example demonstrates how to create a column that starts with a value of 200 and adds incrementally in steps of 3.</span></span>  
  
```vb  
Dim workColumn As DataColumn = workTable.Columns.Add( _  
    "CustomerID", typeof(Int32))  
workColumn.AutoIncrement = true  
workColumn.AutoIncrementSeed = 200  
workColumn.AutoIncrementStep = 3  
```  
  
```csharp  
DataColumn workColumn = workTable.Columns.Add(  
    "CustomerID", typeof(Int32));  
workColumn.AutoIncrement = true;  
workColumn.AutoIncrementSeed = 200;  
workColumn.AutoIncrementStep = 3;  
```  
  
## <a name="see-also"></a><span data-ttu-id="8f64f-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f64f-108">See Also</span></span>  
 <xref:System.Data.DataColumn>  
 [<span data-ttu-id="8f64f-109">Definición de esquema de DataTable</span><span class="sxs-lookup"><span data-stu-id="8f64f-109">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [<span data-ttu-id="8f64f-110">Objetos DataTable</span><span class="sxs-lookup"><span data-stu-id="8f64f-110">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="8f64f-111">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="8f64f-111">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
