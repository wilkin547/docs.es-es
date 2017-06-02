---
title: "Valores de columna XML de SQL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d97ce4da-f09c-4d1e-85b7-a0ccedd7246a
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Valores de columna XML de SQL
[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] admite el nuevo tipo de datos `xml` y los programadores pueden recuperar conjuntos de resultados que incluyan este tipo mediante el comportamiento estándar de la clase <xref:System.Data.SqlClient.SqlCommand>.  Las columnas `xml` se pueden recuperar como se recupera cualquier columna \(por ejemplo, en un <xref:System.Data.SqlClient.SqlDataReader>\) pero si desea trabajar con el contenido de la columna en XML, deberá utilizar un <xref:System.Xml.XmlReader>.  
  
## Ejemplo  
 La siguiente aplicación de consola selecciona dos filas, cada una de las cuales contiene una columna `xml`, de la tabla **Sales.Store** de la base de datos **AdventureWorks** para una instancia <xref:System.Data.SqlClient.SqlDataReader>.  Para cada fila, el valor de la columna `xml` se lee mediante el método <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> de <xref:System.Data.SqlClient.SqlDataReader>.  El valor se almacena en un <xref:System.Xml.XmlReader>.  Tenga en cuenta que debe utilizar <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> en lugar del método <xref:System.Data.IDataRecord.GetValue%2A> si desea establecer el contenido en una variable <xref:System.Data.SqlTypes.SqlXml>; <xref:System.Data.IDataRecord.GetValue%2A> devuelve el valor de la columna `xml` como una cadena.  
  
> [!NOTE]
>  De forma predeterminada, la base de datos de ejemplo **AdventureWorks** no se instala al instalar [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  Para instalarla, ejecute el programa de instalación de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  
  
 [!code-csharp[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/VB/source.vb#1)]  
  
## Vea también  
 <xref:System.Data.SqlTypes.SqlXml>   
 [Datos XML en SQL Server](../../../../../docs/framework/data/adonet/sql/xml-data-in-sql-server.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)