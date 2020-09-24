---
title: Transacciones distribuidas
ms.date: 03/30/2017
ms.assetid: 718b257c-bcb2-408e-b004-a7b0adb1c176
ms.openlocfilehash: b6553d50039ca0f4888f0610b187c6b419a462b5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153202"
---
# <a name="distributed-transactions"></a>Transacciones distribuidas

Entre otras cosas, una transacción es un conjunto de tareas relacionadas que se ejecutan correctamente (confirman) o dan error (anulan) como una unidad. Una *transacción distribuida* es una transacción que afecta a varios recursos. Para que una transacción distribuida se confirme, todos los participantes deben garantizar que los cambios en los datos serán permanentes. Los cambios deben conservarse a pesar de bloqueos del sistema u otros eventos imprevistos. Si alguno de los participantes no cumple esta garantía, toda la transacción da error y se revertirán los cambios en los datos en el ámbito de la transacción.  
  
> [!NOTE]
> Si intenta confirmar o revertir una transacción al iniciar un `DataReader` mientras la transacción está activa, se produce una excepción.  
  
## <a name="working-with-systemtransactions"></a>Trabajo con System.Transactions  

 En .NET Framework, las transacciones distribuidas se administran a través de la API del espacio de nombres <xref:System.Transactions>. Cuando hay implicados varios administradores de recursos persistentes, la API <xref:System.Transactions> delegará el control de las transacciones distribuidas en un monitor de transacciones como el Coordinador de transacciones distribuidas de Microsoft (MS DTC). Para obtener más información, vea [conceptos básicos](../transactions/transaction-fundamentals.md)de las transacciones.  
  
 ADO.NET 2.0 incorporó la compatibilidad con la inscripción en una transacción distribuida mediante el método `EnlistTransaction`, que inscribe una conexión en una instancia de <xref:System.Transactions.Transaction>. En las versiones anteriores de ADO.NET, la inscripción explícita en transacciones distribuidas se realizaba mediante el método `EnlistDistributedTransaction` de una conexión que inscribía ésta en una instancia <xref:System.EnterpriseServices.ITransaction>, en la que se permitía la compatibilidad con versiones anteriores. Para obtener más información acerca de las transacciones de Enterprise Services, consulte [interoperabilidad con Enterprise Services y transacciones de com+](../transactions/interoperability-with-enterprise-services-and-com-transactions.md).  
  
 Cuando se usa una transacción <xref:System.Transactions> con el proveedor .NET Framework para SQL Server en una base de datos de SQL Server, se usará automáticamente un objeto <xref:System.Transactions.Transaction> ligero. A continuación, la transacción se puede promover a una transacción distribuida completa si es necesario. Para obtener más información, vea [integración de System. Transactions con SQL Server](system-transactions-integration-with-sql-server.md).  
  
> [!NOTE]
> El número máximo de transacciones distribuidas en las que puede participar una base de datos de Oracle a la vez se establece de forma predeterminada en 10. Después de la décima transacción en una conexión a una base de datos de Oracle, se inicia una excepción. Oracle no admite `DDL` en las transacciones distribuidas.  
  
## <a name="automatically-enlisting-in-a-distributed-transaction"></a>Inscripción automática en una transacción distribuida  

 La inscripción automática es el método predeterminado (y preferido) de integrar conexiones ADO.NET con `System.Transactions`. Un objeto de conexión se inscribirá automáticamente en una transacción distribuida existente si se determina que hay una transacción activa, que, en términos de `System.Transaction`, significa que `Transaction.Current` no es nula. La inscripción automática en transacciones tiene lugar cuando se abre la conexión. No ocurrirá después, incluso si se ejecuta un comando dentro del ámbito de una transacción. Puede deshabilitar la inscripción automática en transacciones existentes si especifica `Enlist=false` como un parámetro de cadena de conexión para una <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=nameWithType>, o `OLE DB Services=-7` como un parámetro de cadena de conexión para una <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A?displayProperty=nameWithType>. Para obtener más información acerca de los parámetros de cadena de conexión de Oracle y ODBC, vea <xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A?displayProperty=nameWithType> y <xref:System.Data.Odbc.OdbcConnection.ConnectionString%2A?displayProperty=nameWithType>.  
  
## <a name="manually-enlisting-in-a-distributed-transaction"></a>Inscripción manual en una transacción distribuida  

 Si la inscripción automática está deshabilitada o es necesario inscribir la conexión en una transacción que se ha iniciado después de abierta la conexión, puede inscribirla en una transacción distribuida existente mediante el método `EnlistTransaction` del objeto <xref:System.Data.Common.DbConnection> correspondiente al proveedor con el que esté trabajando. La inscripción en una transacción distribuida existente garantiza que, si la transacción se confirma o revierte, también se confirmarán o revertirán las modificaciones realizadas por el código en el origen de datos.  
  
 La inscripción en transacciones distribuidas es especialmente conveniente al agrupar objetos empresariales. Si se agrupa un objeto empresarial con una conexión abierta, la inscripción automática en transacciones sólo se produce cuando se abre esa conexión. Si se realizan varias transacciones con el objeto empresarial agrupado, la conexión abierta para ese objeto no se inscribirá automáticamente en las transacciones recién iniciadas. En este caso, puede deshabilitar la inscripción automática de la conexión en la transacción e inscribir la conexión en las transacciones mediante `EnlistTransaction`.  
  
 `EnlistTransaction` toma un único argumento de tipo <xref:System.Transactions.Transaction> que es una referencia a la transacción existente. Después de llamar al método `EnlistTransaction` de la conexión, todas las modificaciones realizadas en el origen de datos mediante la conexión se incluyen en la transacción. Si se pasa un valor nulo, se anula la inscripción de la conexión de su inscripción actual en transacciones distribuidas. Tenga en cuenta que la conexión se debe abrir antes de llamar a `EnlistTransaction`.  
  
> [!NOTE]
> Una vez que una conexión se inscribe explícitamente en una transacción, no se puede anular su inscripción ni inscribirse en otra transacción hasta que finaliza la primera transacción.  
  
> [!CAUTION]
> Si la conexión ya ha comenzado una transacción mediante el método `EnlistTransaction` de la conexión, <xref:System.Data.Common.DbConnection.BeginTransaction%2A> inicia una excepción. No obstante, si la transacción es una transacción local iniciada en el origen de datos (por ejemplo, al ejecutar la instrucción BEGIN TRANSACTION de forma explícita mediante un <xref:System.Data.SqlClient.SqlCommand>), `EnlistTransaction` la revertirá e inscribirá en la transacción distribuida existente como se ha solicitado. No recibirá aviso de que la transacción local se ha revertido y deberá administrar todas las transacciones locales no iniciadas mediante <xref:System.Data.Common.DbConnection.BeginTransaction%2A>. Si usa el proveedor de datos .NET Framework para SQL Server (`SqlClient`) con SQL Server, se producirá una excepción al intentar una inscripción. Todos los demás casos no se detectarán.  
  
## <a name="promotable-transactions-in-sql-server"></a>Transacciones que se pueden promover en SQL Server  

 SQL Server 2005 admite transacciones que se pueden promover en las que se pueda promover automáticamente una transacción ligera local a una transacción distribuida solamente cuando es necesario. Las transacciones promovibles no invocan la sobrecarga adicional de las transacciones distribuidas a menos que sea necesario. Para obtener más información y un ejemplo de código, vea [integración de System. Transactions con SQL Server](system-transactions-integration-with-sql-server.md).  
  
## <a name="configuring-distributed-transactions"></a>Configuración de transacciones distribuidas  

 Puede que necesite habilitar MS DTC a través de la red para usar transacciones distribuidas. Si tiene Firewall de Windows habilitado, debe permitir que el servicio MS DTC use la red o abrir el puerto MS DTC.  
  
## <a name="see-also"></a>Vea también

- [Transacciones y simultaneidad](transactions-and-concurrency.md)
- [Integración de System.Transactions con SQL Server](system-transactions-integration-with-sql-server.md)
- [Información general de ADO.NET](ado-net-overview.md)
