---
title: Valores de columna de SQL XML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d97ce4da-f09c-4d1e-85b7-a0ccedd7246a
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c31ec6ae2b50870da7b999e20cd8ae44f1d42e03
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="sql-xml-column-values"></a>Valores de columna de SQL XML
[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] admite el nuevo tipo de datos `xml` y los programadores pueden recuperar conjuntos de resultados que incluyan este tipo mediante el comportamiento estándar de la clase <xref:System.Data.SqlClient.SqlCommand>. Las columnas `xml` se pueden recuperar como se recupera cualquier columna (por ejemplo, en un <xref:System.Data.SqlClient.SqlDataReader>) pero si desea trabajar con el contenido de la columna en XML, deberá utilizar un <xref:System.Xml.XmlReader>.  
  
## <a name="example"></a>Ejemplo  
 La siguiente aplicación de consola selecciona dos filas, cada uno con un `xml` columna, desde el **Sales.Store** tabla el **AdventureWorks** base de datos a un <xref:System.Data.SqlClient.SqlDataReader> instancia. Para cada fila, el valor de la columna `xml` se lee mediante el método <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> de <xref:System.Data.SqlClient.SqlDataReader>. El valor se almacena en un <xref:System.Xml.XmlReader>. Tenga en cuenta que debe utilizar <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> en lugar del método <xref:System.Data.IDataRecord.GetValue%2A> si desea establecer el contenido en una variable <xref:System.Data.SqlTypes.SqlXml>; <xref:System.Data.IDataRecord.GetValue%2A> devuelve el valor de la columna `xml` como una cadena.  
  
> [!NOTE]
>  El **AdventureWorks** base de datos de ejemplo no está instalado de forma predeterminada al instalar [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]. Para instalarla, ejecute el programa de instalación de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  
  
 [!code-csharp[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/VB/source.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Data.SqlTypes.SqlXml>  
 [Datos XML en SQL Server](../../../../../docs/framework/data/adonet/sql/xml-data-in-sql-server.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
