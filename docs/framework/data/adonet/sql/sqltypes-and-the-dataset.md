---
title: SqlTypes y DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9172c20a-9876-4b3b-9c97-1963c02b1993
ms.openlocfilehash: 04f95cd7d3f6e52f644f23dd8a32c77d56a5ddda
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147513"
---
# <a name="sqltypes-and-the-dataset"></a><span data-ttu-id="7b395-102">SqlTypes y DataSet</span><span class="sxs-lookup"><span data-stu-id="7b395-102">SqlTypes and the DataSet</span></span>

<span data-ttu-id="7b395-103">ADO.NET 2.0 introdujo la compatibilidad de tipos mejorada con `DataSet` mediante el espacio de nombres <xref:System.Data.SqlTypes>.</span><span class="sxs-lookup"><span data-stu-id="7b395-103">ADO.NET 2.0 introduced enhanced type support for the `DataSet` through the  <xref:System.Data.SqlTypes> namespace.</span></span> <span data-ttu-id="7b395-104">Los tipos en <xref:System.Data.SqlTypes> se han diseñado para proporcionar tipos de datos con la misma semántica y precisión que los de una base de datos SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7b395-104">The types in <xref:System.Data.SqlTypes> are designed to provide data types with the same semantics and precision as the data types in a SQL Server database.</span></span> <span data-ttu-id="7b395-105">Cada tipo de datos de <xref:System.Data.SqlTypes> tiene un tipo de datos equivalente en SQL Server, con la misma representación de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="7b395-105">Each data type in <xref:System.Data.SqlTypes> has an equivalent data type in SQL Server, with the same underlying data representation.</span></span>  
  
 <span data-ttu-id="7b395-106">El uso de <xref:System.Data.SqlTypes> directamente en <xref:System.Data.DataSet> confiere varias ventajas cuando se trabaja con tipos de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7b395-106">Using <xref:System.Data.SqlTypes> directly in a <xref:System.Data.DataSet> confers several benefits when working with SQL Server data types.</span></span> <span data-ttu-id="7b395-107"><xref:System.Data.SqlTypes> admite la misma semántica que los tipos de datos nativos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7b395-107"><xref:System.Data.SqlTypes> supports the same semantics as SQL Server native data types.</span></span> <span data-ttu-id="7b395-108">Si se especifica uno de los tipos <xref:System.Data.SqlTypes> en la definición de <xref:System.Data.DataColumn>, se elimina la pérdida de precisión que se puede producir al convertir tipos de datos decimales o numéricos a uno de los tipos de datos de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="7b395-108">Specifying one of the <xref:System.Data.SqlTypes> in the definition of a <xref:System.Data.DataColumn> eliminates the loss of precision that can occur when converting decimal or numeric data types to one of the common language runtime (CLR) data types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7b395-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7b395-109">Example</span></span>  

 <span data-ttu-id="7b395-110">En el siguiente ejemplo se crea un objeto <xref:System.Data.DataTable> que define explícitamente los tipos de datos <xref:System.Data.DataColumn> mediante <xref:System.Data.SqlTypes> en lugar de tipos CLR.</span><span class="sxs-lookup"><span data-stu-id="7b395-110">The following example creates a <xref:System.Data.DataTable> object, explicitly defining the <xref:System.Data.DataColumn> data types by using <xref:System.Data.SqlTypes> instead of CLR types.</span></span> <span data-ttu-id="7b395-111">El código rellena <xref:System.Data.DataTable> con los datos de la tabla Sales.SalesOrderDetail de la base de datos AdventureWorks de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7b395-111">The code fills the <xref:System.Data.DataTable> with data from the Sales.SalesOrderDetail table in the AdventureWorks database in SQL Server.</span></span> <span data-ttu-id="7b395-112">La salida mostrada en la ventana de la consola muestra el tipo de datos de cada columna y los valores recuperados de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7b395-112">The output displayed in the console window shows the data type of each column, and the values retrieved from SQL Server.</span></span>  
  
 [!code-csharp[DataWorks SqlTypes.GetTypeAW#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.GetTypeAW/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.GetTypeAW#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.GetTypeAW/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="7b395-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b395-113">See also</span></span>

- [<span data-ttu-id="7b395-114">Asignaciones de tipos de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="7b395-114">SQL Server Data Type Mappings</span></span>](../sql-server-data-type-mappings.md)
- [<span data-ttu-id="7b395-115">Configurar parámetros y tipos de datos de parámetros</span><span class="sxs-lookup"><span data-stu-id="7b395-115">Configuring Parameters and Parameter Data Types</span></span>](../configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="7b395-116">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7b395-116">ADO.NET Overview</span></span>](../ado-net-overview.md)
