---
title: Crear columnas de incremento automático
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
ms.openlocfilehash: 5e4a36829107480a44980c7210b39c21231c67f4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786457"
---
# <a name="creating-autoincrement-columns"></a><span data-ttu-id="007d8-102">Crear columnas de incremento automático</span><span class="sxs-lookup"><span data-stu-id="007d8-102">Creating AutoIncrement Columns</span></span>
<span data-ttu-id="007d8-103">Para garantizar que los valores de una columna son únicos, éstos se pueden establecer de manera que se incrementen automáticamente cuando se agregan filas a la tabla.</span><span class="sxs-lookup"><span data-stu-id="007d8-103">To ensure unique column values, you can set the column values to increment automatically when new rows are added to the table.</span></span> <span data-ttu-id="007d8-104">Para crear un incremento <xref:System.Data.DataColumn>automático, establezca la <xref:System.Data.DataColumn.AutoIncrement%2A> propiedad de la columna en **true**.</span><span class="sxs-lookup"><span data-stu-id="007d8-104">To create an auto-incrementing <xref:System.Data.DataColumn>, set the <xref:System.Data.DataColumn.AutoIncrement%2A> property of the column to **true**.</span></span> <span data-ttu-id="007d8-105">A continuación, comienza con el valor definido en <xref:System.Data.DataColumn.AutoIncrementSeed%2A> la propiedad y, con cada fila agregada, el valor de la columna **incremento automático** aumenta según el valor <xref:System.Data.DataColumn.AutoIncrementStep%2A> definido en la propiedad de la columna. <xref:System.Data.DataColumn></span><span class="sxs-lookup"><span data-stu-id="007d8-105">The <xref:System.Data.DataColumn> then starts with the value defined in the <xref:System.Data.DataColumn.AutoIncrementSeed%2A> property, and with each row added the value of the **AutoIncrement** column increases by the value defined in the <xref:System.Data.DataColumn.AutoIncrementStep%2A> property of the column.</span></span>  
  
 <span data-ttu-id="007d8-106">En el caso de las columnas de **incremento automático** , se recomienda establecer la <xref:System.Data.DataColumn.ReadOnly%2A> propiedad de **DataColumn** en **true**.</span><span class="sxs-lookup"><span data-stu-id="007d8-106">For **AutoIncrement** columns, we recommend that the <xref:System.Data.DataColumn.ReadOnly%2A> property of the **DataColumn** be set to **true**.</span></span>  
  
 <span data-ttu-id="007d8-107">En el ejemplo siguiente se muestra cómo se crea una columna que comienza con un valor de 200 y va aumentando de tres en tres.</span><span class="sxs-lookup"><span data-stu-id="007d8-107">The following example demonstrates how to create a column that starts with a value of 200 and adds incrementally in steps of 3.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="007d8-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="007d8-108">See also</span></span>

- <xref:System.Data.DataColumn>
- [<span data-ttu-id="007d8-109">Definición del esquema de DataTable</span><span class="sxs-lookup"><span data-stu-id="007d8-109">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="007d8-110">Objetos DataTable</span><span class="sxs-lookup"><span data-stu-id="007d8-110">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="007d8-111">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="007d8-111">ADO.NET Overview</span></span>](../ado-net-overview.md)
