---
title: Valores de columna de SQL XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d97ce4da-f09c-4d1e-85b7-a0ccedd7246a
ms.openlocfilehash: cd55e2263d4b71fe62910ac918e331ebe37833eb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177285"
---
# <a name="sql-xml-column-values"></a><span data-ttu-id="f45f7-102">Valores de columna de SQL XML</span><span class="sxs-lookup"><span data-stu-id="f45f7-102">SQL XML Column Values</span></span>

<span data-ttu-id="f45f7-103">SQL Server admite el tipo de datos `xml` y los desarrolladores pueden recuperar conjuntos de resultados que incluyan este tipo mediante el comportamiento estándar de la clase <xref:System.Data.SqlClient.SqlCommand>.</span><span class="sxs-lookup"><span data-stu-id="f45f7-103">SQL Server supports the `xml` data type, and developers can retrieve result sets including this type using standard behavior of the <xref:System.Data.SqlClient.SqlCommand> class.</span></span> <span data-ttu-id="f45f7-104">Una columna `xml` se puede recuperar tal como se recupera cualquier columna (en <xref:System.Data.SqlClient.SqlDataReader>, por ejemplo), pero si desea trabajar con el contenido de la columna como XML, debe usar <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="f45f7-104">An `xml` column can be retrieved just as any column is retrieved (into a <xref:System.Data.SqlClient.SqlDataReader>, for example) but if you want to work with the content of the column as XML, you must use an <xref:System.Xml.XmlReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f45f7-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f45f7-105">Example</span></span>  

 <span data-ttu-id="f45f7-106">La siguiente aplicación de consola selecciona dos filas, cada una de las cuales contiene una columna `xml`, de la tabla **Sales.Store** de la base de datos **AdventureWorks** para una instancia <xref:System.Data.SqlClient.SqlDataReader>.</span><span class="sxs-lookup"><span data-stu-id="f45f7-106">The following console application selects two rows, each containing an `xml` column, from the **Sales.Store** table in the **AdventureWorks** database to a <xref:System.Data.SqlClient.SqlDataReader> instance.</span></span> <span data-ttu-id="f45f7-107">Para cada fila, se lee el valor de la columna `xml` mediante el método <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> de <xref:System.Data.SqlClient.SqlDataReader>.</span><span class="sxs-lookup"><span data-stu-id="f45f7-107">For each row, the value of the `xml` column is read using the <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> method of <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="f45f7-108">El valor se almacena en <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="f45f7-108">The value is stored in an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="f45f7-109">Tenga en cuenta que debe usar <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> en lugar del método <xref:System.Data.IDataRecord.GetValue%2A> si desea establecer el contenido en una variable <xref:System.Data.SqlTypes.SqlXml>; <xref:System.Data.IDataRecord.GetValue%2A> devuelve el valor de la columna `xml` como una cadena.</span><span class="sxs-lookup"><span data-stu-id="f45f7-109">Note that you must use <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> rather than the <xref:System.Data.IDataRecord.GetValue%2A> method if you want to set the contents to a <xref:System.Data.SqlTypes.SqlXml> variable; <xref:System.Data.IDataRecord.GetValue%2A> returns the value of the `xml` column as a string.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f45f7-110">De forma predeterminada, la base de datos de ejemplo **AdventureWorks** no se instala al instalar SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f45f7-110">The **AdventureWorks** sample database is not installed by default when you install SQL Server.</span></span> <span data-ttu-id="f45f7-111">Puede instalarlo mediante la ejecución del programa de instalación de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f45f7-111">You can install it by running SQL Server Setup.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f45f7-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f45f7-112">See also</span></span>

- <xref:System.Data.SqlTypes.SqlXml>
- [<span data-ttu-id="f45f7-113">Datos XML en SQL Server</span><span class="sxs-lookup"><span data-stu-id="f45f7-113">XML Data in SQL Server</span></span>](xml-data-in-sql-server.md)
- [<span data-ttu-id="f45f7-114">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f45f7-114">ADO.NET Overview</span></span>](../ado-net-overview.md)
