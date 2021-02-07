---
description: 'Más información acerca de: transacciones locales'
title: Transacciones locales
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8ae3712f-ef5e-41a1-9ea9-b3d0399439f1
ms.openlocfilehash: 998024a6b08ec9cb97c8bb8dbbe2c9d17f38f350
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99681648"
---
# <a name="local-transactions"></a>Transacciones locales

Las transacciones de ADO.NET se usan cuando se quiere enlazar varias tareas para que se ejecuten como una sola unidad de trabajo. Por ejemplo, imagine que una aplicación realiza dos tareas. Primero, actualiza una tabla con información de pedidos. Luego, actualiza una tabla que contiene la información de inventario, cargando en cuenta los elementos pedidos. Si no se puede realizar alguna de las tareas, las dos actualizaciones se revierten.  
  
## <a name="determining-the-transaction-type"></a>Determinación del tipo de transacción  

 Una transacción se considera local cuando consta de una única fase y la base de datos la controla directamente. Una transacción se considera distribuida cuando se coordina mediante un monitor de transacciones y usa mecanismos a prueba de errores (como la confirmación en dos fases) para su resolución.  
  
 Cada uno de los proveedores de datos de .NET Framework tiene su propio `Transaction` objeto para realizar transacciones locales. Si necesita que se realice una transacción en una base de datos de SQL Server, seleccione una transacción de <xref:System.Data.SqlClient>. En transacciones de Oracle, utilice el proveedor <xref:System.Data.OracleClient>. Además, existe una clase <xref:System.Data.Common.DbTransaction> disponible para escribir código independiente del proveedor que requiere transacciones.  
  
> [!NOTE]
> Las transacciones son más eficientes cuando se realizan en el servidor. Si trabaja con una base de datos de SQL Server que hace uso masivo de transacciones explícitas, debería estudiar la posibilidad de escribirlas como procedimientos almacenados mediante la instrucción BEGIN TRANSACTION de Transact-SQL.
  
## <a name="performing-a-transaction-using-a-single-connection"></a>Realización de una transacción mediante una única conexión  

 En ADO.NET, las transacciones se controlan con el objeto `Connection`. Puede iniciar una transacción local con el método `BeginTransaction`. Una vez iniciada una transacción, puede inscribir un comando en esa transacción con la propiedad `Transaction` de un objeto `Command`. Luego, puede confirmar o revertir las modificaciones realizadas en el origen de datos según el resultado correcto o incorrecto de los componentes de la transacción.  
  
> [!NOTE]
> El método `EnlistDistributedTransaction` no se debe emplear en transacciones locales.  
  
 El ámbito de la transacción está limitado a la conexión. En el siguiente ejemplo se realiza una transacción explícita que consta de por dos comandos independientes en el bloque `try`. Los comandos ejecutan instrucciones INSERT en la tabla Production. ScrapReason de la base de datos de ejemplo AdventureWorks SQL Server, que se confirman si no se inicia ninguna excepción. El código del bloque `catch` revierte la transacción si se lanza una excepción. Si la transacción se anula o la conexión se cierra antes de que se haya completado la transacción, ésta se revierte automáticamente.  
  
## <a name="example"></a>Ejemplo  

 Para llevar a cabo una transacción, siga estos pasos.  
  
1. Llame al método <xref:System.Data.SqlClient.SqlConnection.BeginTransaction%2A> del objeto <xref:System.Data.SqlClient.SqlConnection> para marcar el comienzo de la transacción. El método <xref:System.Data.SqlClient.SqlConnection.BeginTransaction%2A> devuelve una referencia a la transacción. Esta referencia se asigna a los objetos <xref:System.Data.SqlClient.SqlCommand> que están inscritos en la transacción.  
  
2. Asigne el objeto `Transaction` a la propiedad <xref:System.Data.SqlClient.SqlCommand.Transaction%2A> del objeto <xref:System.Data.SqlClient.SqlCommand> que se va a ejecutar. Si el comando se ejecuta en una conexión con una transacción activa y el objeto `Transaction` no se ha asignado a la propiedad `Transaction` del objeto `Command`, se inicia una excepción.  
  
3. Ejecute los comandos necesarios.  
  
4. Llame al método <xref:System.Data.SqlClient.SqlTransaction.Commit%2A> del objeto <xref:System.Data.SqlClient.SqlTransaction> para completar la transacción, o al método <xref:System.Data.SqlClient.SqlTransaction.Rollback%2A> para finalizarla. Si la conexión se cierra o elimina antes de que se hayan ejecutado los métodos <xref:System.Data.SqlClient.SqlTransaction.Commit%2A> o <xref:System.Data.SqlClient.SqlTransaction.Rollback%2A>, la transacción se revierte.  
  
 En el ejemplo de código siguiente se muestra la lógica transaccional mediante ADO.NET con Microsoft SQL Server.  
  
 [!code-csharp[DataWorks SqlTransaction.Local#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTransaction.Local/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTransaction.Local#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTransaction.Local/VB/source.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Transacciones y simultaneidad](transactions-and-concurrency.md)
- [Transacciones distribuidas](distributed-transactions.md)
- [Integración de System. Transactions con SQL Server](system-transactions-integration-with-sql-server.md)
- [Información general de ADO.NET](ado-net-overview.md)
