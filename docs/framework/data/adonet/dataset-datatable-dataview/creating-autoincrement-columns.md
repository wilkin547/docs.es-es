---
title: Crear columnas de incremento automático
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
ms.openlocfilehash: 9a979f39003e60c70c03206bd886bdd6827c82e6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203727"
---
# <a name="creating-autoincrement-columns"></a><span data-ttu-id="bc7a4-102">Crear columnas de incremento automático</span><span class="sxs-lookup"><span data-stu-id="bc7a4-102">Creating AutoIncrement Columns</span></span>

<span data-ttu-id="bc7a4-103">Para garantizar que los valores de una columna son únicos, éstos se pueden establecer de manera que se incrementen automáticamente cuando se agregan filas a la tabla.</span><span class="sxs-lookup"><span data-stu-id="bc7a4-103">To ensure unique column values, you can set the column values to increment automatically when new rows are added to the table.</span></span> <span data-ttu-id="bc7a4-104">Para crear un incremento automático <xref:System.Data.DataColumn> , establezca la <xref:System.Data.DataColumn.AutoIncrement%2A> propiedad de la columna en **true**.</span><span class="sxs-lookup"><span data-stu-id="bc7a4-104">To create an auto-incrementing <xref:System.Data.DataColumn>, set the <xref:System.Data.DataColumn.AutoIncrement%2A> property of the column to **true**.</span></span> <span data-ttu-id="bc7a4-105"><xref:System.Data.DataColumn>A continuación, comienza con el valor definido en la <xref:System.Data.DataColumn.AutoIncrementSeed%2A> propiedad y, con cada fila agregada, el valor de la columna **incremento automático** aumenta según el valor definido en la <xref:System.Data.DataColumn.AutoIncrementStep%2A> propiedad de la columna.</span><span class="sxs-lookup"><span data-stu-id="bc7a4-105">The <xref:System.Data.DataColumn> then starts with the value defined in the <xref:System.Data.DataColumn.AutoIncrementSeed%2A> property, and with each row added the value of the **AutoIncrement** column increases by the value defined in the <xref:System.Data.DataColumn.AutoIncrementStep%2A> property of the column.</span></span>  
  
 <span data-ttu-id="bc7a4-106">En el caso de las columnas de **incremento automático** , se recomienda <xref:System.Data.DataColumn.ReadOnly%2A> establecer la propiedad de **DataColumn** en **true**.</span><span class="sxs-lookup"><span data-stu-id="bc7a4-106">For **AutoIncrement** columns, we recommend that the <xref:System.Data.DataColumn.ReadOnly%2A> property of the **DataColumn** be set to **true**.</span></span>  
  
 <span data-ttu-id="bc7a4-107">En el ejemplo siguiente se muestra cómo se crea una columna que comienza con un valor de 200 y va aumentando de tres en tres.</span><span class="sxs-lookup"><span data-stu-id="bc7a4-107">The following example demonstrates how to create a column that starts with a value of 200 and adds incrementally in steps of 3.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bc7a4-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bc7a4-108">See also</span></span>

- <xref:System.Data.DataColumn>
- [<span data-ttu-id="bc7a4-109">Definición del esquema de DataTable</span><span class="sxs-lookup"><span data-stu-id="bc7a4-109">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="bc7a4-110">Objetos DataTable</span><span class="sxs-lookup"><span data-stu-id="bc7a4-110">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="bc7a4-111">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="bc7a4-111">ADO.NET Overview</span></span>](../ado-net-overview.md)
