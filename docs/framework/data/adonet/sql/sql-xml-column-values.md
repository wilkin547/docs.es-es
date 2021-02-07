---
description: 'Más información acerca de: valores de columna XML de SQL'
title: Valores de columna de SQL XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d97ce4da-f09c-4d1e-85b7-a0ccedd7246a
ms.openlocfilehash: 357d55e2ce497c9929b8e7e7459ebf23ccaafede
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767185"
---
# <a name="sql-xml-column-values"></a>Valores de columna de SQL XML

SQL Server admite el tipo de datos `xml` y los desarrolladores pueden recuperar conjuntos de resultados que incluyan este tipo mediante el comportamiento estándar de la clase <xref:System.Data.SqlClient.SqlCommand>. Una columna `xml` se puede recuperar tal como se recupera cualquier columna (en <xref:System.Data.SqlClient.SqlDataReader>, por ejemplo), pero si desea trabajar con el contenido de la columna como XML, debe usar <xref:System.Xml.XmlReader>.  
  
## <a name="example"></a>Ejemplo  

 La siguiente aplicación de consola selecciona dos filas, cada una de las cuales contiene una columna `xml`, de la tabla **Sales.Store** de la base de datos **AdventureWorks** para una instancia <xref:System.Data.SqlClient.SqlDataReader>. Para cada fila, se lee el valor de la columna `xml` mediante el método <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> de <xref:System.Data.SqlClient.SqlDataReader>. El valor se almacena en <xref:System.Xml.XmlReader>. Tenga en cuenta que debe usar <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> en lugar del método <xref:System.Data.IDataRecord.GetValue%2A> si desea establecer el contenido en una variable <xref:System.Data.SqlTypes.SqlXml>; <xref:System.Data.IDataRecord.GetValue%2A> devuelve el valor de la columna `xml` como una cadena.  
  
> [!NOTE]
> De forma predeterminada, la base de datos de ejemplo **AdventureWorks** no se instala al instalar SQL Server. Puede instalarlo mediante la ejecución del programa de instalación de SQL Server.  
  
 [!code-csharp[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/VB/source.vb#1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Data.SqlTypes.SqlXml>
- [Datos XML en SQL Server](xml-data-in-sql-server.md)
- [Información general de ADO.NET](../ado-net-overview.md)
