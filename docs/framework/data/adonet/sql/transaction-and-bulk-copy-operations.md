---
title: "Transacci&#243;n y operaciones de copia masiva | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f6f0cbc9-f7bf-4d6e-875f-ad1ba0b4aa62
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Transacci&#243;n y operaciones de copia masiva
Las operaciones de copia masiva se pueden realizar como operaciones aisladas o como parte de una transacción en varios pasos.  Esta última opción permite realizar más de una operación de copia masiva en la misma transacción, así como otras operaciones de base de datos \(como inserciones, actualizaciones y eliminaciones\) y, al mismo tiempo, seguir teniendo la posibilidad de confirmar o revertir la transacción entera.  
  
 De forma predeterminada, las operaciones de copia masiva se realizan como una operación aislada.  la operación de copia masiva tiene lugar sin transacción, sin la oportunidad de revertirla.  Si necesita revertir la copia masiva total o parcialmente cuando se produce un error, puede utilizar una transacción administrada por <xref:System.Data.SqlClient.SqlBulkCopy>, realizar la operación de copia masiva en una transacción existente o inscribirla en **System.Transactions** <xref:System.Transactions.Transaction>.  
  
## Realización de una operación de copia masiva sin transacción  
 La siguiente aplicación de consola muestra lo que pasa cuando una operación de copia masiva sin transacción encuentra un error a mitad de camino.  
  
 En el ejemplo, la tabla de origen y de destino incluye cada una una columna `Identity` llamada **ProductID**.  Primero, el código prepara la tabla de destino para lo cual elimina todas las filas y luego inserta una sola cuyo **ProductID** se sabe que existe en la tabla de origen.  De forma predeterminada, se genera un nuevo valor para la columna `Identity` en la tabla de destino por cada fila agregada.  En este ejemplo se establece una opción cuando se abre la conexión que obliga al proceso de carga masiva a utilizar en su lugar los valores `Identity` de la tabla de origen.  
  
 La operación de copia masiva se ejecuta con la propiedad <xref:System.Data.SqlClient.SqlBulkCopy.BatchSize%2A> establecida en 10.  Cuando la operación encuentra la fila no válida, se produce una excepción.  En este primer ejemplo, la operación de copia masiva es sin transacción.  Todos los lotes copiados hasta el punto del error se confirman, el lote que contiene la clave duplicada se revierte y la operación de copia masiva se detiene antes de procesar el resto de los lotes.  
  
> [!NOTE]
>  Este ejemplo no se ejecutará a menos que haya creado las tablas de trabajo como se describe en [Configuración de ejemplo de copia masiva](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md).  Este código se proporciona para mostrar cuál debe ser la sintaxis cuando solo se utiliza **SqlBulkCopy**.  Si las tablas de origen y de destino se encuentran en la misma instancia de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)], lo más rápido y sencillo es usar una instrucción [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] `INSERT … SELECT` para copiar los datos.  
  
 [!code-csharp[DataWorks SqlBulkCopy.DefaultTransaction#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.DefaultTransaction/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.DefaultTransaction#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.DefaultTransaction/VB/source.vb#1)]  
  
## Realización de una operación de copia masiva dedicada en una transacción  
 De forma predeterminada, una operación de copia masiva es su propia transacción.  Si desea realizar una operación de copia masiva dedicada, cree una nueva instancia de <xref:System.Data.SqlClient.SqlBulkCopy> con una cadena de conexión o utilice un objeto <xref:System.Data.SqlClient.SqlConnection> existente sin una transacción activa.  En cada situación, la operación de copia masiva crea la transacción y, después, la confirma o revierte.  
  
 Puede especificar explícitamente la opción <xref:System.Data.SqlClient.SqlBulkCopyOptions> en el constructor de clases <xref:System.Data.SqlClient.SqlBulkCopy> y provocar de forma explícita una operación de copia masiva para ejecutarla en su propia transacción, lo que da lugar a que cada lote de la operación de copia masiva se ejecute en una transacción distinta.  
  
> [!NOTE]
>  Dado que diferentes lotes se ejecutan en diferentes transacciones, si se produjera un error durante la operación de copia masiva, todas las filas del lote actual se revertirían, pero las filas de los lotes anteriores permanecerían en la base de datos.  
  
 La siguiente aplicación de consola es similar a la del ejemplo anterior, pero con una diferencia: en este ejemplo, la operación de copia masiva administra sus propias transacciones.  Todos los lotes copiados hasta el punto del error se confirman, el lote que contiene la clave duplicada se revierte y la operación de copia masiva se detiene antes de procesar el resto de los lotes.  
  
> [!IMPORTANT]
>  Este ejemplo no se ejecutará a menos que haya creado las tablas de trabajo como se describe en [Configuración de ejemplo de copia masiva](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md).  Este código se proporciona para mostrar cuál debe ser la sintaxis cuando solo se utiliza **SqlBulkCopy**.  Si las tablas de origen y de destino se encuentran en la misma instancia de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)], lo más rápido y sencillo es usar una instrucción [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] `INSERT … SELECT` para copiar los datos.  
  
 [!code-csharp[DataWorks SqlBulkCopy.InternalTransaction#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.InternalTransaction/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.InternalTransaction#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.InternalTransaction/VB/source.vb#1)]  
  
## Uso de transacciones existentes  
 Puede especificar un objeto <xref:System.Data.SqlClient.SqlTransaction> existente como un parámetro en un constructor <xref:System.Data.SqlClient.SqlBulkCopy>.  En esta situación, la operación de copia masiva se realiza en una transacción existente y no se efectúa cambio alguno en el estado de la transacción \(lo que significa que ni se confirma ni se anula\).  De esta forma, las aplicaciones pueden incluir la operación de copia masiva en una transacción con otras operaciones de base de datos.  No obstante, si no especifica un objeto <xref:System.Data.SqlClient.SqlTransaction> y pasa una referencia nula mientras la conexión tiene una transacción activa, se produce una excepción.  
  
 Si se produce un error y necesita revertir toda la operación de copia masiva, o si la copia masiva debe ejecutarse como parte de un proceso más grande que se pueda revertir, puede proporcionar un objeto <xref:System.Data.SqlClient.SqlTransaction> al constructor <xref:System.Data.SqlClient.SqlBulkCopy>.  
  
 La siguiente aplicación de consola es similar a la primera \(sin transacción\), pero con una diferencia: en este ejemplo, la operación de copia masiva se incluye en una transacción externa más grande.  Cuando se produce la infracción de la clave principal, toda la transacción se revierte y no se agrega ninguna fila a la tabla de destino.  
  
> [!IMPORTANT]
>  Este ejemplo no se ejecutará a menos que haya creado las tablas de trabajo como se describe en [Configuración de ejemplo de copia masiva](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md).  Este código se proporciona para mostrar cuál debe ser la sintaxis cuando solo se utiliza **SqlBulkCopy**.  Si las tablas de origen y de destino se encuentran en la misma instancia de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)], lo más rápido y sencillo es usar una instrucción [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] `INSERT … SELECT` para copiar los datos.  
  
 [!code-csharp[DataWorks SqlBulkCopy.SqlTransaction#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.SqlTransaction/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.SqlTransaction#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.SqlTransaction/VB/source.vb#1)]  
  
## Vea también  
 [Operaciones de copia masiva en SQL Server](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)