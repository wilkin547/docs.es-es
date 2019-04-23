---
title: SqlTypes y DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9172c20a-9876-4b3b-9c97-1963c02b1993
ms.openlocfilehash: a218a8e0fe3d2c17a0f09a40645c7b3ad26fb5ed
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59072706"
---
# <a name="sqltypes-and-the-dataset"></a><span data-ttu-id="26890-102">SqlTypes y DataSet</span><span class="sxs-lookup"><span data-stu-id="26890-102">SqlTypes and the DataSet</span></span>
<span data-ttu-id="26890-103">ADO.NET 2.0 incorporó compatibilidad mejorada de tipos con el `DataSet` mediante el espacio de nombres <xref:System.Data.SqlTypes>.</span><span class="sxs-lookup"><span data-stu-id="26890-103">ADO.NET 2.0 introduced enhanced type support for the `DataSet` through the  <xref:System.Data.SqlTypes> namespace.</span></span> <span data-ttu-id="26890-104">Los tipos de <xref:System.Data.SqlTypes> se han diseñado para proporcionar tipos de datos con la misma semántica y precisión que los de una base de datos SQL Server.</span><span class="sxs-lookup"><span data-stu-id="26890-104">The types in <xref:System.Data.SqlTypes> are designed to provide data types with the same semantics and precision as the data types in a SQL Server database.</span></span> <span data-ttu-id="26890-105">Cada tipo de datos de <xref:System.Data.SqlTypes> tiene un tipo de datos equivalente en SQL Server, con la misma representación de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="26890-105">Each data type in <xref:System.Data.SqlTypes> has an equivalent data type in SQL Server, with the same underlying data representation.</span></span>  
  
 <span data-ttu-id="26890-106">El uso de <xref:System.Data.SqlTypes> directamente en un <xref:System.Data.DataSet> otorga varias ventajas cuando se trabaja con tipos de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="26890-106">Using <xref:System.Data.SqlTypes> directly in a <xref:System.Data.DataSet> confers several benefits when working with SQL Server data types.</span></span> <span data-ttu-id="26890-107"><xref:System.Data.SqlTypes> admite la misma semántica que los tipos de datos nativos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="26890-107"><xref:System.Data.SqlTypes> supports the same semantics as SQL Server native data types.</span></span> <span data-ttu-id="26890-108">La especificación de uno de los <xref:System.Data.SqlTypes> en la definición de un objeto <xref:System.Data.DataColumn> elimina la pérdida de precisión que se produce al convertir tipos de datos decimales o numéricos en uno de los tipos de datos de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="26890-108">Specifying one of the <xref:System.Data.SqlTypes> in the definition of a <xref:System.Data.DataColumn> eliminates the loss of precision that can occur when converting decimal or numeric data types to one of the common language runtime (CLR) data types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26890-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="26890-109">Example</span></span>  
 <span data-ttu-id="26890-110">En el siguiente ejemplo se crea un objeto <xref:System.Data.DataTable>, que define explícitamente los tipos de datos <xref:System.Data.DataColumn> utilizando <xref:System.Data.SqlTypes> en lugar de tipos CLR.</span><span class="sxs-lookup"><span data-stu-id="26890-110">The following example creates a <xref:System.Data.DataTable> object, explicitly defining the <xref:System.Data.DataColumn> data types by using <xref:System.Data.SqlTypes> instead of CLR types.</span></span> <span data-ttu-id="26890-111">El código llena la <xref:System.Data.DataTable> con los datos de la tabla Sales.SalesOrderDetail de la base de datos AdventureWorks de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="26890-111">The code fills the <xref:System.Data.DataTable> with data from the Sales.SalesOrderDetail table in the AdventureWorks database in SQL Server.</span></span> <span data-ttu-id="26890-112">El resultado que aparece en la ventana de la consola muestra el tipo de datos de cada columna y los valores recuperados de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="26890-112">The output displayed in the console window shows the data type of each column, and the values retrieved from SQL Server.</span></span>  
  
 [!code-csharp[DataWorks SqlTypes.GetTypeAW#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.GetTypeAW/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.GetTypeAW#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.GetTypeAW/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="26890-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="26890-113">See also</span></span>

- [<span data-ttu-id="26890-114">Asignaciones de tipos de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="26890-114">SQL Server Data Type Mappings</span></span>](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)
- [<span data-ttu-id="26890-115">Configuración de parámetros y tipos de datos de parámetros</span><span class="sxs-lookup"><span data-stu-id="26890-115">Configuring Parameters and Parameter Data Types</span></span>](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="26890-116">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="26890-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
