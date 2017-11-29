---
title: Transacciones locales
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
ms.assetid: 8ae3712f-ef5e-41a1-9ea9-b3d0399439f1
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f9b1280f3a05a42a2f713adf993bb439245c95a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="local-transactions"></a>Transacciones locales
Las transacciones de [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] se utilizan cuando se desea enlazar varias tareas para que se ejecuten como una sola unidad de trabajo. Por ejemplo, imagine que una aplicación realiza dos tareas. Primero, actualiza una tabla con información de pedidos. Luego, actualiza una tabla que contiene la información de inventario, cargando en cuenta los elementos pedidos. Si se produce un error en alguna de las tareas, a continuación, ambas actualizaciones se revierten.  
  
## <a name="determining-the-transaction-type"></a>Determinación del tipo de transacción  
 Una transacción se considera una transacción local cuando se trata de una transacción única fase y es controlada directamente por la base de datos. Una transacción se considera una transacción distribuida cuando se coordinan mediante un monitor de transacciones y utiliza mecanismos a prueba de errores (como confirmación en dos fases) para la resolución de transacciones.  
  
 Cada proveedor de datos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] tiene su propio objeto `Transaction` para realizar transacciones locales. Si necesita que se realice una transacción en una base de datos de SQL Server, seleccione una transacción de <xref:System.Data.SqlClient>. En transacciones de Oracle, utilice el proveedor <xref:System.Data.OracleClient>. Además, existe una nueva clase <xref:System.Data.Common.DbTransaction> disponible para la escritura de código independiente del proveedor que requiere transacciones.  
  
> [!NOTE]
>  Las transacciones son más eficientes cuando se realizan en el servidor. Si trabaja con una base de datos de SQL Server que hace uso masivo de transacciones explícitas, debería estudiar la posibilidad de escribirlas como procedimientos almacenados mediante la instrucción BEGIN TRANSACTION de Transact-SQL. Para obtener más información acerca de la realización de transacciones de servidor, vea los Libros en pantalla de SQL Server.  
  
## <a name="performing-a-transaction-using-a-single-connection"></a>Realización de una transacción mediante una única conexión  
 En [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], las transacciones se controlan con el objeto `Connection`. Puede iniciar una transacción local con el método `BeginTransaction`. Una vez iniciada una transacción, puede inscribir un comando en esa transacción con la propiedad `Transaction` de un objeto `Command`. Luego, puede confirmar o revertir las modificaciones realizadas en el origen de datos según el resultado correcto o incorrecto de los componentes de la transacción.  
  
> [!NOTE]
>  El método `EnlistDistributedTransaction` no se debe emplear en transacciones locales.  
  
 El ámbito de la transacción está limitado a la conexión. En el siguiente ejemplo se realiza una transacción explícita que consta de por dos comandos independientes en el bloque `try`. Los comandos ejecutan instrucciones INSERT con respecto a la tabla Production.ScrapReason de la base de datos de ejemplo AdventureWorks de [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)], que se confirman si no se produce ninguna excepción. El código del bloque `catch` revierte la transacción si se produce una excepción. Si la transacción se anula o la conexión se cierra antes de que se haya completado la transacción, ésta se revierte automáticamente.  
  
## <a name="example"></a>Ejemplo  
 Para llevar a cabo una transacción, siga estos pasos.  
  
1.  Llame al método <xref:System.Data.SqlClient.SqlConnection.BeginTransaction%2A> del objeto <xref:System.Data.SqlClient.SqlConnection> para marcar el comienzo de la transacción. El método <xref:System.Data.SqlClient.SqlConnection.BeginTransaction%2A> devuelve una referencia a la transacción. Esta referencia se asigna a los objetos <xref:System.Data.SqlClient.SqlCommand> que están inscritos en la transacción.  
  
2.  Asigne el objeto `Transaction` a la propiedad <xref:System.Data.SqlClient.SqlCommand.Transaction%2A> del objeto <xref:System.Data.SqlClient.SqlCommand> que se va a ejecutar. Si el comando se ejecuta en una conexión con una transacción activa y el objeto `Transaction` no se ha asignado a la propiedad `Transaction` del objeto `Command`, se inicia una excepción.  
  
3.  Ejecute los comandos necesarios.  
  
4.  Llame al método <xref:System.Data.SqlClient.SqlTransaction.Commit%2A> del objeto <xref:System.Data.SqlClient.SqlTransaction> para completar la transacción, o al método <xref:System.Data.SqlClient.SqlTransaction.Rollback%2A> para finalizarla. Si la conexión se cierra o elimina antes de que se hayan ejecutado los métodos <xref:System.Data.SqlClient.SqlTransaction.Commit%2A> o <xref:System.Data.SqlClient.SqlTransaction.Rollback%2A>, la transacción se revierte.  
  
 En el siguiente código de ejemplo se muestra la lógica transaccional utilizando [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] con Microsoft SQL Server.  
  
 [!code-csharp[DataWorks SqlTransaction.Local#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTransaction.Local/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTransaction.Local#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTransaction.Local/VB/source.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 [Las transacciones y simultaneidad](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [Transacciones distribuidas](../../../../docs/framework/data/adonet/distributed-transactions.md)  
 [Integración de System.Transactions con SQL Server](../../../../docs/framework/data/adonet/system-transactions-integration-with-sql-server.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
