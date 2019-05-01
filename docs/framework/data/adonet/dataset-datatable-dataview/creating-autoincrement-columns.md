---
title: Crear columnas de incremento automático
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
ms.openlocfilehash: 99c52b93cee858511d50aba2f30f2b9f96d91ccd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034377"
---
# <a name="creating-autoincrement-columns"></a><span data-ttu-id="aa2cc-102">Crear columnas de incremento automático</span><span class="sxs-lookup"><span data-stu-id="aa2cc-102">Creating AutoIncrement Columns</span></span>
<span data-ttu-id="aa2cc-103">Para garantizar que los valores de una columna son únicos, éstos se pueden establecer de manera que se incrementen automáticamente cuando se agregan filas a la tabla.</span><span class="sxs-lookup"><span data-stu-id="aa2cc-103">To ensure unique column values, you can set the column values to increment automatically when new rows are added to the table.</span></span> <span data-ttu-id="aa2cc-104">Para crear un incremento automático <xref:System.Data.DataColumn>, establezca el <xref:System.Data.DataColumn.AutoIncrement%2A> propiedad de la columna a **true**.</span><span class="sxs-lookup"><span data-stu-id="aa2cc-104">To create an auto-incrementing <xref:System.Data.DataColumn>, set the <xref:System.Data.DataColumn.AutoIncrement%2A> property of the column to **true**.</span></span> <span data-ttu-id="aa2cc-105">El <xref:System.Data.DataColumn> , a continuación, se inicia con el valor definido en el <xref:System.Data.DataColumn.AutoIncrementSeed%2A> propiedad y con cada fila agregada, el valor de la **AutoIncrement** columna aumenta con el valor definido en el <xref:System.Data.DataColumn.AutoIncrementStep%2A> propiedad de la columna.</span><span class="sxs-lookup"><span data-stu-id="aa2cc-105">The <xref:System.Data.DataColumn> then starts with the value defined in the <xref:System.Data.DataColumn.AutoIncrementSeed%2A> property, and with each row added the value of the **AutoIncrement** column increases by the value defined in the <xref:System.Data.DataColumn.AutoIncrementStep%2A> property of the column.</span></span>  
  
 <span data-ttu-id="aa2cc-106">Para **AutoIncrement** columnas, se recomienda que el <xref:System.Data.DataColumn.ReadOnly%2A> propiedad de la **DataColumn** establecerse **true**.</span><span class="sxs-lookup"><span data-stu-id="aa2cc-106">For **AutoIncrement** columns, we recommend that the <xref:System.Data.DataColumn.ReadOnly%2A> property of the **DataColumn** be set to **true**.</span></span>  
  
 <span data-ttu-id="aa2cc-107">En el ejemplo siguiente se muestra cómo se crea una columna que comienza con un valor de 200 y va aumentando de tres en tres.</span><span class="sxs-lookup"><span data-stu-id="aa2cc-107">The following example demonstrates how to create a column that starts with a value of 200 and adds incrementally in steps of 3.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="aa2cc-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa2cc-108">See also</span></span>

- <xref:System.Data.DataColumn>
- [<span data-ttu-id="aa2cc-109">Definición del esquema de DataTable</span><span class="sxs-lookup"><span data-stu-id="aa2cc-109">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)
- [<span data-ttu-id="aa2cc-110">Objetos DataTable</span><span class="sxs-lookup"><span data-stu-id="aa2cc-110">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [<span data-ttu-id="aa2cc-111">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="aa2cc-111">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
