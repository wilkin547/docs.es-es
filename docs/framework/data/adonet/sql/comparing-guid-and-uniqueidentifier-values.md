---
title: "Comparaci&#243;n de valores GUID y uniqueidentifier | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: aababd75-2335-43e3-ace8-4b7ae84191a8
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Comparaci&#243;n de valores GUID y uniqueidentifier
El tipo de datos de identificador único global \(GUID\) de SQL Server viene representado por el tipo de datos `uniqueidentifier`, que almacena un valor binario de 16 bytes.  Un GUID es un número binario que sirve principalmente como identificador, el cual que debe ser único en una red formada por varios equipos en muchos sitios.  Los GUID se pueden generar con la llamada a la función NEWID de Transact\-SQL, y se tiene la garantía de que son únicos en todo el mundo.  Para obtener más información, vea "Utilizar datos uniqueidentifier" en los Libros en pantalla de SQL Server.  
  
## Trabajo con valores SqlGuid  
 Como los valores GUID son largos y poco claros, no resultan significativos para los usuarios.  Si utiliza GUID generados de forma aleatoria en valores de claves e inserta muchas filas, obtendrá E\/S aleatoria en los índices, lo que puede afectar al rendimiento negativamente.  Los GUID son también relativamente grandes si se comparan con otros tipos de datos.  En general, se recomienda el uso de GUID solo en situaciones muy limitadas en las que no resulta adecuado ningún otro tipo de datos.  
  
### Comparación de valores GUID  
 Los operadores de comparación se pueden utilizar con valores `uniqueidentifier`.  Sin embargo, al comparar los patrones de bits de los dos valores no se implementa el orden.  Las únicas operaciones que se permiten con respecto a un valor `uniqueidentifier` son las comparaciones \(\=, \<\>, \<, \>, \<\=, \>\=\) y la comprobación de NULL \(IS NULL y IS NOT NULL\).  No se permite ninguna otra operación aritmética.  
  
 Tanto <xref:System.Guid> como <xref:System.Data.SqlTypes.SqlGuid> tienen un método `CompareTo` para comparar diferentes valores GUID.  Sin embargo, `System.Guid.CompareTo` y `SqlTypes.SqlGuid.CompareTo` se implementan de forma distinta.  <xref:System.Data.SqlTypes.SqlGuid> implementa `CompareTo` mediante el comportamiento de SQL Server, en el que los últimos seis bytes de un valor son los más significativos.  <xref:System.Guid> evalúa los 16 bytes.  En el siguiente ejemplo se muestra esta diferencia conductual.  La primera sección del código muestra valores <xref:System.Guid> sin ordenar; la segunda sección muestra los valores <xref:System.Guid> ordenados y  la tercera sección muestra los valores <xref:System.Data.SqlTypes.SqlGuid> ordenados.  El resultado se muestra debajo del listado de código.  
  
 [!code-csharp[DataWorks SqlTypes.Guid#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.Guid/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.Guid#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.Guid/VB/source.vb#1)]  
  
 Este ejemplo produce los siguientes resultados.  
  
```  
Unsorted Guids:  
3aaaaaaa-bbbb-cccc-dddd-2eeeeeeeeeee  
2aaaaaaa-bbbb-cccc-dddd-1eeeeeeeeeee  
1aaaaaaa-bbbb-cccc-dddd-3eeeeeeeeeee  
  
Sorted Guids:  
1aaaaaaa-bbbb-cccc-dddd-3eeeeeeeeeee  
2aaaaaaa-bbbb-cccc-dddd-1eeeeeeeeeee  
3aaaaaaa-bbbb-cccc-dddd-2eeeeeeeeeee  
  
Sorted SqlGuids:  
2aaaaaaa-bbbb-cccc-dddd-1eeeeeeeeeee  
3aaaaaaa-bbbb-cccc-dddd-2eeeeeeeeeee  
1aaaaaaa-bbbb-cccc-dddd-3eeeeeeeeeee  
```  
  
## Vea también  
 [Tipos de datos de SQL Server y ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)