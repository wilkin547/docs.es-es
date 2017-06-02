---
title: "M&#233;todos gen&#233;ricos Field y SetField (LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1883365f-9d6c-4ccb-9187-df309f47706d
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# M&#233;todos gen&#233;ricos Field y SetField (LINQ to DataSet)
[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] proporciona métodos de extensión a la clase <xref:System.Data.DataRow> para obtener acceso a los valores de columna: el método <xref:System.Data.DataRowExtensions.Field%2A> y el método <xref:System.Data.DataRowExtensions.SetField%2A>. Estos métodos facilitan el acceso a los valores de columna a los desarrolladores, sobre todo en lo relativo a valores NULL. <xref:System.Data.DataSet> usa <xref:System.DBNull.Value> para representar valores NULL, en tanto que [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] usa la compatibilidad con tipos que admiten valores NULL presentada en [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].  Utilizar el descriptor de acceso de columna preexistente en <xref:System.Data.DataRow> exige convertir el objeto de valor devuelto al tipo apropiado.  Si un campo determinado de <xref:System.Data.DataRow> puede ser NULL, se debe comprobar de manera explícita si hay un valor NULL porque la devolución de <xref:System.DBNull.Value> y su conversión implícita a otro tipo produce una <xref:System.InvalidCastException>.  En el ejemplo siguiente, si no se utilizara el método <xref:System.Data.DataRow.IsNull%2A> para comprobar si hay un valor NULL, se produciría una excepción si el indizador devolviera <xref:System.DBNull.Value> e intentara convertirlo en <xref:System.String>.  
  
 [!code-csharp[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#whereisnull)]
 [!code-vb[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#whereisnull)]  
  
 El método <xref:System.Data.DataRowExtensions.Field%2A> proporciona acceso a los valores de columna de <xref:System.Data.DataRow> y <xref:System.Data.DataRowExtensions.SetField%2A> establece los valores de columna en <xref:System.Data.DataRow>.  Tanto el método <xref:System.Data.DataRowExtensions.Field%2A> como el método <xref:System.Data.DataRowExtensions.SetField%2A> controlan tipos que admiten valores NULL, por lo que no es necesario comprobar explícitamente si hay valores NULL, como en el ejemplo anterior.  Además, ambos son métodos genéricos, lo que significa que no es necesario convertir el tipo de valor devuelto.  
  
 El siguiente ejemplo utiliza el método <xref:System.Data.DataRowExtensions.Field%2A>.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where3)]
 [!code-vb[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where3)]  
  
 Observe que el tipo de datos especificado en el parámetro `T` genérico de los métodos <xref:System.Data.DataRowExtensions.Field%2A> y <xref:System.Data.DataRowExtensions.SetField%2A> deben coincidir con el tipo del valor subyacente.  De lo contrario, se producirá una excepción <xref:System.InvalidCastException>.  El nombre de columna especificado debe también coincidir con el nombre de una columna en <xref:System.Data.DataSet>; en caso contrario, se producirá una <xref:System.ArgumentException>.  En ambos casos, la excepción se produce en tiempo de ejecución durante la enumeración de datos cuando se ejecuta la consulta.  
  
 El método <xref:System.Data.DataRowExtensions.SetField%2A> en sí no realiza ninguna conversión de tipos.  Sin embargo, esto no significa que no se realizará una conversión de tipos.  El método <xref:System.Data.DataRowExtensions.SetField%2A> expone el comportamiento [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] de la clase <xref:System.Data.DataRow>.  El objeto <xref:System.Data.DataRow> consiguió realizar una conversión de tipos y el valor convertido se guardará en el objeto <xref:System.Data.DataRow>.  
  
## Vea también  
 <xref:System.Data.DataRowExtensions>