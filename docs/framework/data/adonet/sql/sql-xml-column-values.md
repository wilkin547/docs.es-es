---
title: Valores de columna de SQL XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d97ce4da-f09c-4d1e-85b7-a0ccedd7246a
ms.openlocfilehash: 03b09d3a53c725bb0e84ba6b5d98944267bc564c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780799"
---
# <a name="sql-xml-column-values"></a>Valores de columna de SQL XML
SQL Server admite el `xml` tipo de datos y los desarrolladores pueden recuperar conjuntos de resultados que incluyan este tipo mediante <xref:System.Data.SqlClient.SqlCommand> el comportamiento estándar de la clase. Las columnas `xml` se pueden recuperar como se recupera cualquier columna (por ejemplo, en un <xref:System.Data.SqlClient.SqlDataReader>) pero si desea trabajar con el contenido de la columna en XML, deberá utilizar un <xref:System.Xml.XmlReader>.  
  
## <a name="example"></a>Ejemplo  
 La siguiente aplicación de consola selecciona dos filas, cada una `xml` de las cuales contiene una columna, de la tabla **sales. Store** de <xref:System.Data.SqlClient.SqlDataReader> la base de datos **AdventureWorks** a una instancia de. Para cada fila, el valor de la columna `xml` se lee mediante el método <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> de <xref:System.Data.SqlClient.SqlDataReader>. El valor se almacena en un <xref:System.Xml.XmlReader>. Tenga en cuenta que debe utilizar <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> en lugar del método <xref:System.Data.IDataRecord.GetValue%2A> si desea establecer el contenido en una variable <xref:System.Data.SqlTypes.SqlXml>; <xref:System.Data.IDataRecord.GetValue%2A> devuelve el valor de la columna `xml` como una cadena.  
  
> [!NOTE]
> La base de datos de ejemplo **AdventureWorks** no se instala de forma predeterminada al instalar SQL Server. Para instalarla, ejecute el programa de instalación de SQL Server.  
  
 [!code-csharp[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/VB/source.vb#1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Data.SqlTypes.SqlXml>
- [Datos XML en SQL Server](xml-data-in-sql-server.md)
- [Información general sobre ADO.NET](../ado-net-overview.md)
