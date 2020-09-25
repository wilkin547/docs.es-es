---
title: Transacciones locales
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8ae3712f-ef5e-41a1-9ea9-b3d0399439f1
ms.openlocfilehash: a0b713ab0b81cb2f0661212dae22db34b7f9f3ae
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175400"
---
# <a name="local-transactions"></a>Transacciones locales

Las transacciones de ADO.NET se usan cuando se desea enlazar varias tareas juntas para que se ejecuten como una sola unidad de trabajo. Por ejemplo, imagine que una aplicación realiza dos tareas. Primero, actualiza una tabla con información de pedidos. Luego, actualiza una tabla que contiene la información de inventario, cargando en cuenta los elementos pedidos. Si se produce un error en cualquiera de las tareas, se revierten ambas.  
  
## <a name="determining-the-transaction-type"></a>Determinación del tipo de transacción  

 Una transacción se considera una transacción local cuando es una transacción de una sola fase y se controla directamente por la base de datos. Una transacción se considera una transacción distribuida cuando está coordinada por un monitor de transacciones y utiliza mecanismos de error (como confirmación en dos fases) para la resolución de transacciones.  
  
 Cada uno de los proveedores de datos de .NET Framework tiene su propio `Transaction` objeto para realizar transacciones locales. Si necesita que se realice una transacción en una base de datos de SQL Server, seleccione una transacción de <xref:System.Data.SqlClient>. En transacciones de Oracle, utilice el proveedor <xref:System.Data.OracleClient>. Además, hay una <xref:System.Data.Common.DbTransaction> clase que está disponible para escribir código independiente del proveedor que requiere transacciones.  
  
> [!NOTE]
> Las transacciones son más eficaces cuando se realizan en el servidor. Si trabaja con una base de datos de SQL Server que hace uso masivo de transacciones explícitas, debería estudiar la posibilidad de escribirlas como procedimientos almacenados mediante la instrucción BEGIN TRANSACTION de Transact-SQL.
  
## <a name="performing-a-transaction-using-a-single-connection"></a>Realización de una transacción mediante una única conexión  

 En ADO.NET, las transacciones se controlan con el `Connection` objeto. Puede iniciar una transacción local con el método `BeginTransaction`. Una vez iniciada una transacción, puede inscribir un comando en esa transacción con la propiedad `Transaction` de un objeto `Command`. Luego, puede confirmar o revertir las modificaciones realizadas en el origen de datos según el resultado correcto o incorrecto de los componentes de la transacción.  
  
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
  
## <a name="see-also"></a>Consulte también

- [Transacciones y simultaneidad](transactions-and-concurrency.md)
- [Transacciones distribuidas](distributed-transactions.md)
- [Integración de System.Transactions con SQL Server](system-transactions-integration-with-sql-server.md)
- [Información general de ADO.NET](ado-net-overview.md)
