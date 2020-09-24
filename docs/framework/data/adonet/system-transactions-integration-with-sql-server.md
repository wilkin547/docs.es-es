---
title: Integración de System.Transactions con SQL Server
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b555544e-7abb-4814-859b-ab9cdd7d8716
ms.openlocfilehash: 5adf40f96854e08736cdef77300d69e452de5eea
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91191689"
---
# <a name="systemtransactions-integration-with-sql-server"></a><span data-ttu-id="d4d3d-102">Integración de System.Transactions con SQL Server</span><span class="sxs-lookup"><span data-stu-id="d4d3d-102">System.Transactions Integration with SQL Server</span></span>

<span data-ttu-id="d4d3d-103">La versión .NET Framework 2,0 presentó un marco de trabajo de transacciones al que se puede tener acceso a través del <xref:System.Transactions> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-103">The .NET Framework version 2.0 introduced a transaction framework that can be accessed through the <xref:System.Transactions> namespace.</span></span> <span data-ttu-id="d4d3d-104">Este marco de trabajo expone las transacciones de una manera totalmente integrada en el .NET Framework, incluido ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-104">This framework exposes transactions in a way that is fully integrated in the .NET Framework, including ADO.NET.</span></span>  
  
 <span data-ttu-id="d4d3d-105">Además de las mejoras de programación, <xref:System.Transactions> y ADO.net pueden funcionar juntos para coordinar las optimizaciones al trabajar con transacciones.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-105">In addition to the programmability enhancements, <xref:System.Transactions> and ADO.NET can work together to coordinate optimizations when you work with transactions.</span></span> <span data-ttu-id="d4d3d-106">Una transacción promovible es una transacción ligera (local) que, en caso necesario, se puede promover automáticamente a una transacción completamente distribuida.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-106">A promotable transaction is a lightweight (local) transaction that can be automatically promoted to a fully distributed transaction on an as-needed basis.</span></span>  
  
 <span data-ttu-id="d4d3d-107">A partir de ADO.NET 2,0, <xref:System.Data.SqlClient> admite transacciones promocionadas al trabajar con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-107">Starting with ADO.NET 2.0, <xref:System.Data.SqlClient> supports promotable transactions when you work with SQL Server.</span></span> <span data-ttu-id="d4d3d-108">Las transacciones promovibles no invocan la sobrecarga adicional de las transacciones distribuidas a menos que sea necesario.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-108">A promotable transaction does not invoke the added overhead of a distributed transaction unless the added overhead is required.</span></span> <span data-ttu-id="d4d3d-109">Las transacciones promocionadas son automáticas y no requieren la intervención del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-109">Promotable transactions are automatic and require no intervention from the developer.</span></span>  
  
 <span data-ttu-id="d4d3d-110">Las transacciones promocionadas solo están disponibles cuando se usa el proveedor de datos de .NET Framework para SQL Server ( `SqlClient` ) con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-110">Promotable transactions are only available when you use the .NET Framework Data Provider for SQL Server (`SqlClient`) with SQL Server.</span></span>  
  
## <a name="creating-promotable-transactions"></a><span data-ttu-id="d4d3d-111">Creación de transacciones promocionadas</span><span class="sxs-lookup"><span data-stu-id="d4d3d-111">Creating Promotable Transactions</span></span>  

 <span data-ttu-id="d4d3d-112">El proveedor de .NET Framework para SQL Server proporciona compatibilidad con las transacciones promocionadas, que se administran a través de las clases en el <xref:System.Transactions> espacio de nombres .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-112">The .NET Framework Provider for SQL Server provides support for promotable transactions, which are handled through the classes in the .NET Framework <xref:System.Transactions> namespace.</span></span> <span data-ttu-id="d4d3d-113">Las transacciones promocionadas optimizan las transacciones distribuidas ya que aplazan la creación de las mismas hasta que es necesario.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-113">Promotable transactions optimize distributed transactions by deferring creating a distributed transaction until it is needed.</span></span> <span data-ttu-id="d4d3d-114">Si solo se necesita un administrador de recursos, no tiene lugar ninguna transacción distribuida.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-114">If only one resource manager is required, no distributed transaction occurs.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d4d3d-115">En un caso que no es de plena confianza, se requiere <xref:System.Transactions.DistributedTransactionPermission> cuando la transacción se promueve al nivel de transacción distribuida.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-115">In a partially trusted scenario, the <xref:System.Transactions.DistributedTransactionPermission> is required when a transaction is promoted to a distributed transaction.</span></span>  
  
## <a name="promotable-transaction-scenarios"></a><span data-ttu-id="d4d3d-116">Situaciones de uso de transacciones promocionadas</span><span class="sxs-lookup"><span data-stu-id="d4d3d-116">Promotable Transaction Scenarios</span></span>  

 <span data-ttu-id="d4d3d-117">Normalmente, las transacciones distribuidas consumen muchos recursos del sistema, siendo el encargado de administrarlas Microsoft DTC (Coordinador de transacciones distribuidas), que integra todos los administradores de recursos a los que se tiene acceso en la transacción.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-117">Distributed transactions typically consume significant system resources, being managed by Microsoft Distributed Transaction Coordinator (MS DTC), which integrates all the resource managers accessed in the transaction.</span></span> <span data-ttu-id="d4d3d-118">Una transacción promocionada es una forma especial de una <xref:System.Transactions> transacción que delega eficazmente el trabajo a una transacción de SQL Server simple.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-118">A promotable transaction is a special form of a <xref:System.Transactions> transaction that effectively delegates the work to a simple SQL Server transaction.</span></span> <span data-ttu-id="d4d3d-119"><xref:System.Transactions>, <xref:System.Data.SqlClient> y SQL Server coordinar el trabajo implicado en el control de la transacción y promoverla a una transacción distribuida completa según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-119"><xref:System.Transactions>, <xref:System.Data.SqlClient>, and SQL Server coordinate the work involved in handling the transaction, promoting it to a full distributed transaction as needed.</span></span>  
  
 <span data-ttu-id="d4d3d-120">La ventaja de utilizar transacciones promocionadas es que cuando se abre una conexión utilizando una transacción <xref:System.Transactions.TransactionScope> activa, y no hay ninguna otra conexión abierta, la transacción se confirma como una transacción ligera, en lugar de incurrir en la sobrecarga adicional de una transacción completamente distribuida.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-120">The benefit of using promotable transactions is that when a connection is opened by using an active <xref:System.Transactions.TransactionScope> transaction, and no other connections are opened, the transaction commits as a lightweight transaction, instead of incurring the additional overhead of a full distributed transaction.</span></span>  
  
### <a name="connection-string-keywords"></a><span data-ttu-id="d4d3d-121">Palabras clave de cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="d4d3d-121">Connection String Keywords</span></span>  

 <span data-ttu-id="d4d3d-122">La propiedad <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> admite una palabra clave, `Enlist`, que indica si <xref:System.Data.SqlClient> detectará contextos transaccionales e inscribirá automáticamente la conexión en una transacción distribuida.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-122">The <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> property supports a keyword, `Enlist`, which indicates whether <xref:System.Data.SqlClient> will detect transactional contexts and automatically enlist the connection in a distributed transaction.</span></span> <span data-ttu-id="d4d3d-123">Si `Enlist=true`, la conexión se inscribe automáticamente en el contexto de transacción actual del subproceso de apertura.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-123">If `Enlist=true`, the connection is automatically enlisted in the opening thread's current transaction context.</span></span> <span data-ttu-id="d4d3d-124">Si `Enlist=false`, la conexión `SqlClient` no interactúa con una transacción distribuida.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-124">If `Enlist=false`, the `SqlClient` connection does not interact with a distributed transaction.</span></span> <span data-ttu-id="d4d3d-125">El valor predeterminado de `Enlist` es true.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-125">The default value for `Enlist` is true.</span></span> <span data-ttu-id="d4d3d-126">Si no se especifica `Enlist` en la cadena de conexión, la conexión se da de alta automáticamente en una transacción distribuida si se detecta una al abrirse la conexión.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-126">If `Enlist` is not specified in the connection string, the connection is automatically enlisted in a distributed transaction if one is detected when the connection is opened.</span></span>  
  
 <span data-ttu-id="d4d3d-127">Las palabras clave `Transaction Binding` en una cadena de conexión <xref:System.Data.SqlClient.SqlConnection> controlan la asociación de la conexión con una transacción `System.Transactions` dada de alta.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-127">The `Transaction Binding` keywords in a <xref:System.Data.SqlClient.SqlConnection> connection string control the connection's association with an enlisted `System.Transactions` transaction.</span></span> <span data-ttu-id="d4d3d-128">También está disponible mediante la propiedad <xref:System.Data.SqlClient.SqlConnectionStringBuilder.TransactionBinding%2A> de <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-128">It is also available through the <xref:System.Data.SqlClient.SqlConnectionStringBuilder.TransactionBinding%2A> property of a <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.</span></span>  
  
 <span data-ttu-id="d4d3d-129">La siguiente tabla describe los posibles valores.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-129">The following table describes the possible values.</span></span>  
  
|<span data-ttu-id="d4d3d-130">Palabra clave</span><span class="sxs-lookup"><span data-stu-id="d4d3d-130">Keyword</span></span>|<span data-ttu-id="d4d3d-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="d4d3d-131">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d4d3d-132">Desenlace implícito</span><span class="sxs-lookup"><span data-stu-id="d4d3d-132">Implicit Unbind</span></span>|<span data-ttu-id="d4d3d-133">El valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-133">The default.</span></span> <span data-ttu-id="d4d3d-134">La conexión se separa de la transacción cuando termina, y vuelve a cambiar al modo de confirmación automática.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-134">The connection detaches from the transaction when it ends, switching back to autocommit mode.</span></span>|  
|<span data-ttu-id="d4d3d-135">Desenlace explícito</span><span class="sxs-lookup"><span data-stu-id="d4d3d-135">Explicit Unbind</span></span>|<span data-ttu-id="d4d3d-136">La conexión sigue adjuntada a la transacción hasta que ésta se cierra.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-136">The connection remains attached to the transaction until the transaction is closed.</span></span> <span data-ttu-id="d4d3d-137">La conexión producirá errores si no está activa o no coincide con <xref:System.Transactions.Transaction.Current%2A>.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-137">The connection will fail if the associated transaction is not active or does not match <xref:System.Transactions.Transaction.Current%2A>.</span></span>|  
  
## <a name="using-transactionscope"></a><span data-ttu-id="d4d3d-138">Uso de TransactionScope</span><span class="sxs-lookup"><span data-stu-id="d4d3d-138">Using TransactionScope</span></span>  

 <span data-ttu-id="d4d3d-139">La clase <xref:System.Transactions.TransactionScope> crea un bloque de código transaccional dando de alta implícitamente las conexiones en una transacción distribuida.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-139">The <xref:System.Transactions.TransactionScope> class makes a code block transactional by implicitly enlisting connections in a distributed transaction.</span></span> <span data-ttu-id="d4d3d-140">Debe llamar al método <xref:System.Transactions.TransactionScope.Complete%2A> al final del bloque <xref:System.Transactions.TransactionScope> antes de abandonarlo.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-140">You must call the <xref:System.Transactions.TransactionScope.Complete%2A> method at the end of the <xref:System.Transactions.TransactionScope> block before leaving it.</span></span> <span data-ttu-id="d4d3d-141">Al salir del bloque se invoca el método <xref:System.Transactions.TransactionScope.Dispose%2A> .</span><span class="sxs-lookup"><span data-stu-id="d4d3d-141">Leaving the block invokes the <xref:System.Transactions.TransactionScope.Dispose%2A> method.</span></span> <span data-ttu-id="d4d3d-142">Si se ha producido una excepción que ocasiona que el código salga del ámbito, la transacción se considera anulada.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-142">If an exception has been thrown that causes the code to leave scope, the transaction is considered aborted.</span></span>  
  
 <span data-ttu-id="d4d3d-143">Se recomienda el uso de un bloque `using` para asegurarse de que se llama a <xref:System.Transactions.TransactionScope.Dispose%2A> en el objeto <xref:System.Transactions.TransactionScope> cuando se sale de dicho bloque.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-143">We recommend that you use a `using` block to make sure that <xref:System.Transactions.TransactionScope.Dispose%2A> is called on the <xref:System.Transactions.TransactionScope> object when the using block is exited.</span></span> <span data-ttu-id="d4d3d-144">Si no se confirman ni revierten las transacciones pendientes, el rendimiento puede verse seriamente afectado ya que el tiempo de espera predeterminado de <xref:System.Transactions.TransactionScope> es un minuto.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-144">Failure to commit or roll back pending transactions can significantly damage performance because the default time-out for the <xref:System.Transactions.TransactionScope> is one minute.</span></span> <span data-ttu-id="d4d3d-145">Si no utiliza una instrucción `using`, debe realizar todo el trabajo de un bloque `Try` y llamar explícitamente al método <xref:System.Transactions.TransactionScope.Dispose%2A> del bloque `Finally`.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-145">If you do not use a `using` statement, you must perform all work in a `Try` block and explicitly call the <xref:System.Transactions.TransactionScope.Dispose%2A> method in the `Finally` block.</span></span>  
  
 <span data-ttu-id="d4d3d-146">Si se produce una excepción en <xref:System.Transactions.TransactionScope>, la transacción se marca como incoherente y se abandona.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-146">If an exception occurs in the <xref:System.Transactions.TransactionScope>, the transaction is marked as inconsistent and is abandoned.</span></span> <span data-ttu-id="d4d3d-147">Se revertirá cuando se elimine el <xref:System.Transactions.TransactionScope> .</span><span class="sxs-lookup"><span data-stu-id="d4d3d-147">It will be rolled back when the <xref:System.Transactions.TransactionScope> is disposed.</span></span> <span data-ttu-id="d4d3d-148">Si no se produce ninguna excepción, las transacciones participantes se confirman.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-148">If no exception occurs, participating transactions commit.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d4d3d-149">La clase `TransactionScope` crea una transacción con <xref:System.Transactions.Transaction.IsolationLevel%2A> de `Serializable` de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-149">The `TransactionScope` class creates a transaction with a <xref:System.Transactions.Transaction.IsolationLevel%2A> of `Serializable` by default.</span></span> <span data-ttu-id="d4d3d-150">Dependiendo de la aplicación, puede considerar la opción de reducir el nivel de aislamiento para evitar conflictos en ella.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-150">Depending on your application, you might want to consider lowering the isolation level to avoid high contention in your application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d4d3d-151">Se recomienda que solo realice actualizaciones, inserciones y eliminaciones en transacciones distribuidas, ya que consumen una cantidad considerable de recursos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-151">We recommend that you perform only updates, inserts, and deletes within distributed transactions because they consume significant database resources.</span></span> <span data-ttu-id="d4d3d-152">Las instrucciones SELECT pueden bloquear los recursos de base de datos de forma innecesaria y, en algunas situaciones, es posible que tengan que utilizarse transacciones para las selecciones.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-152">Select statements may lock database resources unnecessarily, and in some scenarios, you may have to use transactions for selects.</span></span> <span data-ttu-id="d4d3d-153">Todo el trabajo que no sea de base de datos debe realizarse fuera del ámbito de la transacción, a menos que estén implicados otros administradores de recursos de transacción.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-153">Any non-database work should be done outside the scope of the transaction, unless it involves other transacted resource managers.</span></span> <span data-ttu-id="d4d3d-154">Aunque una excepción en el ámbito de la transacción impide que se confirme la misma, la clase <xref:System.Transactions.TransactionScope> no deja revertir los cambios que haya realizado el código fuera del ámbito de la propia transacción.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-154">Although an exception in the scope of the transaction prevents the transaction from committing, the <xref:System.Transactions.TransactionScope> class has no provision for rolling back any changes your code has made outside the scope of the transaction itself.</span></span> <span data-ttu-id="d4d3d-155">Si es necesario realizar alguna acción cuando se revierta la transacción, deberá escribir su propia implementación de la interfaz <xref:System.Transactions.IEnlistmentNotification> y darla de alta explícitamente en la transacción.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-155">If you have to take some action when the transaction is rolled back, you must write your own implementation of the <xref:System.Transactions.IEnlistmentNotification> interface and explicitly enlist in the transaction.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4d3d-156">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d4d3d-156">Example</span></span>  

 <span data-ttu-id="d4d3d-157">Trabajar con <xref:System.Transactions> requiere disponer de una referencia a System.Transactions.dll.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-157">Working with <xref:System.Transactions> requires that you have a reference to System.Transactions.dll.</span></span>  
  
 <span data-ttu-id="d4d3d-158">La siguiente función muestra cómo crear una transacción promocionada en dos instancias de SQL Server diferentes, representadas por dos objetos <xref:System.Data.SqlClient.SqlConnection> diferentes, que se incluyen en un bloque <xref:System.Transactions.TransactionScope> .</span><span class="sxs-lookup"><span data-stu-id="d4d3d-158">The following function demonstrates how to create a promotable transaction against two different SQL Server instances, represented by two different <xref:System.Data.SqlClient.SqlConnection> objects, which are wrapped in a <xref:System.Transactions.TransactionScope> block.</span></span> <span data-ttu-id="d4d3d-159">El código crea el bloque <xref:System.Transactions.TransactionScope> con una instrucción `using` y abre la primera conexión, que automáticamente se da de alta en <xref:System.Transactions.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-159">The code creates the <xref:System.Transactions.TransactionScope> block with a `using` statement and opens the first connection, which automatically enlists it in the <xref:System.Transactions.TransactionScope>.</span></span> <span data-ttu-id="d4d3d-160">La transacción se da de alta inicialmente como una transacción ligera, no como una transacción distribuida completa.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-160">The transaction is initially enlisted as a lightweight transaction, not a full distributed transaction.</span></span> <span data-ttu-id="d4d3d-161">La segunda conexión se inscribe en <xref:System.Transactions.TransactionScope> únicamente si el comando de la primera conexión no produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-161">The second connection is enlisted in the <xref:System.Transactions.TransactionScope> only if the command in the first connection does not throw an exception.</span></span> <span data-ttu-id="d4d3d-162">Cuando se abre la segunda conexión, la transacción se promociona automáticamente a una transacción completamente distribuida.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-162">When the second connection is opened, the transaction is automatically promoted to a full distributed transaction.</span></span> <span data-ttu-id="d4d3d-163">Se invoca el método <xref:System.Transactions.TransactionScope.Complete%2A> , que confirma la transacción únicamente si no se han producido excepciones.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-163">The <xref:System.Transactions.TransactionScope.Complete%2A> method is invoked, which commits the transaction only if no exceptions have been thrown.</span></span> <span data-ttu-id="d4d3d-164">Si en algún punto del bloque <xref:System.Transactions.TransactionScope> se ha producido una excepción, no se llamará a `Complete` y, cuando se elimine <xref:System.Transactions.TransactionScope> al final de su bloque `using` , se revertirá la transacción distribuida.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-164">If an exception has been thrown at any point in the <xref:System.Transactions.TransactionScope> block, `Complete` will not be called, and the distributed transaction will roll back when the <xref:System.Transactions.TransactionScope> is disposed at the end of its `using` block.</span></span>  
  
```csharp  
// This function takes arguments for the 2 connection strings and commands in order  
// to create a transaction involving two SQL Servers. It returns a value > 0 if the  
// transaction committed, 0 if the transaction rolled back. To test this code, you can
// connect to two different databases on the same server by altering the connection string,  
// or to another RDBMS such as Oracle by altering the code in the connection2 code block.  
static public int CreateTransactionScope(  
    string connectString1, string connectString2,  
    string commandText1, string commandText2)  
{  
    // Initialize the return value to zero and create a StringWriter to display results.  
    int returnValue = 0;  
    System.IO.StringWriter writer = new System.IO.StringWriter();  
  
    // Create the TransactionScope in which to execute the commands, guaranteeing  
    // that both commands will commit or roll back as a single unit of work.  
    using (TransactionScope scope = new TransactionScope())  
    {  
        using (SqlConnection connection1 = new SqlConnection(connectString1))  
        {  
            try  
            {  
                // Opening the connection automatically enlists it in the
                // TransactionScope as a lightweight transaction.  
                connection1.Open();  
  
                // Create the SqlCommand object and execute the first command.  
                SqlCommand command1 = new SqlCommand(commandText1, connection1);  
                returnValue = command1.ExecuteNonQuery();  
                writer.WriteLine("Rows to be affected by command1: {0}", returnValue);  
  
                // if you get here, this means that command1 succeeded. By nesting  
                // the using block for connection2 inside that of connection1, you  
                // conserve server and network resources by opening connection2
                // only when there is a chance that the transaction can commit.
                using (SqlConnection connection2 = new SqlConnection(connectString2))  
                    try  
                    {  
                        // The transaction is promoted to a full distributed  
                        // transaction when connection2 is opened.  
                        connection2.Open();  
  
                        // Execute the second command in the second database.  
                        returnValue = 0;  
                        SqlCommand command2 = new SqlCommand(commandText2, connection2);  
                        returnValue = command2.ExecuteNonQuery();  
                        writer.WriteLine("Rows to be affected by command2: {0}", returnValue);  
                    }  
                    catch (Exception ex)  
                    {  
                        // Display information that command2 failed.  
                        writer.WriteLine("returnValue for command2: {0}", returnValue);  
                        writer.WriteLine("Exception Message2: {0}", ex.Message);  
                    }  
            }  
            catch (Exception ex)  
            {  
                // Display information that command1 failed.  
                writer.WriteLine("returnValue for command1: {0}", returnValue);  
                writer.WriteLine("Exception Message1: {0}", ex.Message);  
            }  
        }  
  
        // If an exception has been thrown, Complete will not
        // be called and the transaction is rolled back.  
        scope.Complete();  
    }  
  
    // The returnValue is greater than 0 if the transaction committed.  
    if (returnValue > 0)  
    {  
        writer.WriteLine("Transaction was committed.");  
    }  
    else  
    {  
        // You could write additional business logic here, notify the caller by  
        // throwing a TransactionAbortedException, or log the failure.  
        writer.WriteLine("Transaction rolled back.");  
    }  
  
    // Display messages.  
    Console.WriteLine(writer.ToString());  
  
    return returnValue;  
}  
```  
  
```vb  
' This function takes arguments for the 2 connection strings and commands in order  
' to create a transaction involving two SQL Servers. It returns a value > 0 if the  
' transaction committed, 0 if the transaction rolled back. To test this code, you can
' connect to two different databases on the same server by altering the connection string,  
' or to another RDBMS such as Oracle by altering the code in the connection2 code block.  
Public Function CreateTransactionScope( _  
  ByVal connectString1 As String, ByVal connectString2 As String, _  
  ByVal commandText1 As String, ByVal commandText2 As String) As Integer  
  
    ' Initialize the return value to zero and create a StringWriter to display results.  
    Dim returnValue As Integer = 0  
    Dim writer As System.IO.StringWriter = New System.IO.StringWriter  
  
    ' Create the TransactionScope in which to execute the commands, guaranteeing  
    ' that both commands will commit or roll back as a single unit of work.  
    Using scope As New TransactionScope()  
        Using connection1 As New SqlConnection(connectString1)  
            Try  
                ' Opening the connection automatically enlists it in the
                ' TransactionScope as a lightweight transaction.  
                connection1.Open()  
  
                ' Create the SqlCommand object and execute the first command.  
                Dim command1 As SqlCommand = New SqlCommand(commandText1, connection1)  
                returnValue = command1.ExecuteNonQuery()  
                writer.WriteLine("Rows to be affected by command1: {0}", returnValue)  
  
                ' If you get here, this means that command1 succeeded. By nesting  
                ' the Using block for connection2 inside that of connection1, you  
                ' conserve server and network resources by opening connection2
                ' only when there is a chance that the transaction can commit.
                Using connection2 As New SqlConnection(connectString2)  
                    Try  
                        ' The transaction is promoted to a full distributed  
                        ' transaction when connection2 is opened.  
                        connection2.Open()  
  
                        ' Execute the second command in the second database.  
                        returnValue = 0  
                        Dim command2 As SqlCommand = New SqlCommand(commandText2, connection2)  
                        returnValue = command2.ExecuteNonQuery()  
                        writer.WriteLine("Rows to be affected by command2: {0}", returnValue)  
  
                    Catch ex As Exception  
                        ' Display information that command2 failed.  
                        writer.WriteLine("returnValue for command2: {0}", returnValue)  
                        writer.WriteLine("Exception Message2: {0}", ex.Message)  
                    End Try  
                End Using  
  
            Catch ex As Exception  
                ' Display information that command1 failed.  
                writer.WriteLine("returnValue for command1: {0}", returnValue)  
                writer.WriteLine("Exception Message1: {0}", ex.Message)  
            End Try  
        End Using  
  
        ' If an exception has been thrown, Complete will
        ' not be called and the transaction is rolled back.  
        scope.Complete()  
    End Using  
  
    ' The returnValue is greater than 0 if the transaction committed.  
    If returnValue > 0 Then  
        writer.WriteLine("Transaction was committed.")  
    Else  
        ' You could write additional business logic here, notify the caller by  
        ' throwing a TransactionAbortedException, or log the failure.  
       writer.WriteLine("Transaction rolled back.")  
     End If  
  
    ' Display messages.  
    Console.WriteLine(writer.ToString())  
  
    Return returnValue  
End Function  
```  
  
## <a name="see-also"></a><span data-ttu-id="d4d3d-165">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d4d3d-165">See also</span></span>

- [<span data-ttu-id="d4d3d-166">Transacciones y simultaneidad</span><span class="sxs-lookup"><span data-stu-id="d4d3d-166">Transactions and Concurrency</span></span>](transactions-and-concurrency.md)
- [<span data-ttu-id="d4d3d-167">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d4d3d-167">ADO.NET Overview</span></span>](ado-net-overview.md)
