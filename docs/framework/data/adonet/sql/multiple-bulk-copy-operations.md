---
title: Varias operaciones de copia masiva
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5ad12f94-7459-4a93-a421-4160d1a90715
ms.openlocfilehash: d447f09fcbfe108346b81a2bced44cf305e2844b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172676"
---
# <a name="multiple-bulk-copy-operations"></a><span data-ttu-id="46830-102">Varias operaciones de copia masiva</span><span class="sxs-lookup"><span data-stu-id="46830-102">Multiple Bulk Copy Operations</span></span>

<span data-ttu-id="46830-103">Puede realizar varias operaciones de copia masiva con una única instancia de una clase <xref:System.Data.SqlClient.SqlBulkCopy>.</span><span class="sxs-lookup"><span data-stu-id="46830-103">You can perform multiple bulk copy operations using a single instance of a <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span> <span data-ttu-id="46830-104">Si los parámetros de la operación cambian entre copias (por ejemplo, el nombre de la tabla de destino), debe actualizarlos antes de las llamadas subsiguientes a cualquiera de los métodos **WriteToServer** , como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="46830-104">If the operation parameters change between copies (for example, the name of the destination table), you must update them prior to any subsequent calls to any of the **WriteToServer** methods, as demonstrated in the following example.</span></span> <span data-ttu-id="46830-105">A menos que se cambien explícitamente, todos los valores de propiedad permanecen igual que estaban en la operación de copia masiva anterior para una instancia determinada.</span><span class="sxs-lookup"><span data-stu-id="46830-105">Unless explicitly changed, all property values remain the same as they were on the previous bulk copy operation for a given instance.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="46830-106">Generalmente, es más eficaz realizar varias operaciones de copia masiva con la misma instancia de <xref:System.Data.SqlClient.SqlBulkCopy> que usar una instancia independiente para cada operación.</span><span class="sxs-lookup"><span data-stu-id="46830-106">Performing multiple bulk copy operations using the same instance of <xref:System.Data.SqlClient.SqlBulkCopy> is usually more efficient than using a separate instance for each operation.</span></span>  
  
 <span data-ttu-id="46830-107">Si se realizan varias operaciones de copia masiva con el mismo objeto <xref:System.Data.SqlClient.SqlBulkCopy>, no hay restricciones en cuanto a si la información de origen o destino es igual o diferente en cada operación.</span><span class="sxs-lookup"><span data-stu-id="46830-107">If you perform several bulk copy operations using the same <xref:System.Data.SqlClient.SqlBulkCopy> object, there are no restrictions on whether source or target information is equal or different in each operation.</span></span> <span data-ttu-id="46830-108">Sin embargo, debe asegurarse de que la información de asociación de la columna está establecida correctamente cada vez que se escribe en el servidor.</span><span class="sxs-lookup"><span data-stu-id="46830-108">However, you must ensure that column association information is properly set each time you write to the server.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="46830-109">Este ejemplo no se ejecutará a menos que haya creado las tablas de trabajo como se describe en el ejemplo de configuración de la [copia masiva](bulk-copy-example-setup.md).</span><span class="sxs-lookup"><span data-stu-id="46830-109">This sample will not run unless you have created the work tables as described in [Bulk Copy Example Setup](bulk-copy-example-setup.md).</span></span> <span data-ttu-id="46830-110">Este código se proporciona para mostrar la sintaxis para usar **SqlBulkCopy**.</span><span class="sxs-lookup"><span data-stu-id="46830-110">This code is provided to demonstrate the syntax for using **SqlBulkCopy** only.</span></span> <span data-ttu-id="46830-111">Si las tablas de origen y destino se encuentran en la misma instancia de SQL Server, es más fácil y rápido usar una instrucción `INSERT … SELECT` de Transact-SQL para copiar los datos.</span><span class="sxs-lookup"><span data-stu-id="46830-111">If the source and destination tables are located in the same SQL Server instance, it is easier and faster to use a Transact-SQL `INSERT … SELECT` statement to copy the data.</span></span>  
  
 [!code-csharp[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="46830-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="46830-112">See also</span></span>

- [<span data-ttu-id="46830-113">Operaciones de copia masiva en SQL Server</span><span class="sxs-lookup"><span data-stu-id="46830-113">Bulk Copy Operations in SQL Server</span></span>](bulk-copy-operations-in-sql-server.md)
- [<span data-ttu-id="46830-114">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="46830-114">ADO.NET Overview</span></span>](../ado-net-overview.md)
