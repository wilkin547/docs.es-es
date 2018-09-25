---
title: Valores de columna de SQL XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d97ce4da-f09c-4d1e-85b7-a0ccedd7246a
ms.openlocfilehash: b46c763e7cddfc7617c9a6a23428f83a54955ba0
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47072741"
---
# <a name="sql-xml-column-values"></a><span data-ttu-id="ae29e-102">Valores de columna de SQL XML</span><span class="sxs-lookup"><span data-stu-id="ae29e-102">SQL XML Column Values</span></span>
<span data-ttu-id="ae29e-103">SQL Server admite la `xml` tipo de datos, y los programadores pueden recuperar conjuntos de resultados que incluyan este tipo mediante el comportamiento estándar de la <xref:System.Data.SqlClient.SqlCommand> clase.</span><span class="sxs-lookup"><span data-stu-id="ae29e-103">SQL Server supports the `xml` data type, and developers can retrieve result sets including this type using standard behavior of the <xref:System.Data.SqlClient.SqlCommand> class.</span></span> <span data-ttu-id="ae29e-104">Las columnas `xml` se pueden recuperar como se recupera cualquier columna (por ejemplo, en un <xref:System.Data.SqlClient.SqlDataReader>) pero si desea trabajar con el contenido de la columna en XML, deberá utilizar un <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="ae29e-104">An `xml` column can be retrieved just as any column is retrieved (into a <xref:System.Data.SqlClient.SqlDataReader>, for example) but if you want to work with the content of the column as XML, you must use an <xref:System.Xml.XmlReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae29e-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ae29e-105">Example</span></span>  
 <span data-ttu-id="ae29e-106">La siguiente aplicación de consola selecciona dos filas, cada uno con un `xml` columna, desde el **Sales.Store** tabla el **AdventureWorks** base de datos a un <xref:System.Data.SqlClient.SqlDataReader> instancia.</span><span class="sxs-lookup"><span data-stu-id="ae29e-106">The following console application selects two rows, each containing an `xml` column, from the **Sales.Store** table in the **AdventureWorks** database to a <xref:System.Data.SqlClient.SqlDataReader> instance.</span></span> <span data-ttu-id="ae29e-107">Para cada fila, el valor de la columna `xml` se lee mediante el método <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> de <xref:System.Data.SqlClient.SqlDataReader>.</span><span class="sxs-lookup"><span data-stu-id="ae29e-107">For each row, the value of the `xml` column is read using the <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> method of <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="ae29e-108">El valor se almacena en un <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="ae29e-108">The value is stored in an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="ae29e-109">Tenga en cuenta que debe utilizar <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> en lugar del método <xref:System.Data.IDataRecord.GetValue%2A> si desea establecer el contenido en una variable <xref:System.Data.SqlTypes.SqlXml>; <xref:System.Data.IDataRecord.GetValue%2A> devuelve el valor de la columna `xml` como una cadena.</span><span class="sxs-lookup"><span data-stu-id="ae29e-109">Note that you must use <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> rather than the <xref:System.Data.IDataRecord.GetValue%2A> method if you want to set the contents to a <xref:System.Data.SqlTypes.SqlXml> variable; <xref:System.Data.IDataRecord.GetValue%2A> returns the value of the `xml` column as a string.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae29e-110">El **AdventureWorks** base de datos de ejemplo no se instala de forma predeterminada al instalar SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ae29e-110">The **AdventureWorks** sample database is not installed by default when you install SQL Server.</span></span> <span data-ttu-id="ae29e-111">Para instalarla, ejecute el programa de instalación de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ae29e-111">You can install it by running SQL Server Setup.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="ae29e-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae29e-112">See Also</span></span>  
 <xref:System.Data.SqlTypes.SqlXml>  
 [<span data-ttu-id="ae29e-113">Datos XML en SQL Server</span><span class="sxs-lookup"><span data-stu-id="ae29e-113">XML Data in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/xml-data-in-sql-server.md)  
 [<span data-ttu-id="ae29e-114">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="ae29e-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
