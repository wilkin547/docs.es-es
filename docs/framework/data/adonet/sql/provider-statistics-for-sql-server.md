---
description: 'Más información acerca de: estadísticas de proveedor para SQL Server'
title: Estadísticas de proveedor de SQL Server
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 429c9d09-92ac-46ec-829a-fbff0a9575a2
ms.openlocfilehash: ece5a6214d438ecac64e8738755d5fb5d0ed7245
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767601"
---
# <a name="provider-statistics-for-sql-server"></a><span data-ttu-id="df1b1-103">Estadísticas de proveedor de SQL Server</span><span class="sxs-lookup"><span data-stu-id="df1b1-103">Provider Statistics for SQL Server</span></span>

<span data-ttu-id="df1b1-104">Desde .NET Framework versión 2.0, el proveedor de datos .NET Framework para servidor SQL Server admite estadísticas en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="df1b1-104">Starting with the .NET Framework version 2.0, the .NET Framework Data Provider for SQL Server supports run-time statistics.</span></span> <span data-ttu-id="df1b1-105">Debe habilitar las estadísticas estableciendo la propiedad <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A> del objeto <xref:System.Data.SqlClient.SqlConnection> en `True` después de haber creado un objeto de conexión válido.</span><span class="sxs-lookup"><span data-stu-id="df1b1-105">You must enable statistics by setting the <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A> property of the <xref:System.Data.SqlClient.SqlConnection> object to `True` after you have a valid connection object created.</span></span> <span data-ttu-id="df1b1-106">Una vez habilitadas las estadísticas, puede revisarlas como una "instantánea en el tiempo" recuperando una referencia <xref:System.Collections.IDictionary> a través del método <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> del objeto <xref:System.Data.SqlClient.SqlConnection>.</span><span class="sxs-lookup"><span data-stu-id="df1b1-106">After statistics are enabled, you can review them as a "snapshot in time" by retrieving an <xref:System.Collections.IDictionary> reference via the <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> method of the <xref:System.Data.SqlClient.SqlConnection> object.</span></span> <span data-ttu-id="df1b1-107">Se enumeran a través de la lista como un conjunto de entradas de diccionario de pares nombre-valor.</span><span class="sxs-lookup"><span data-stu-id="df1b1-107">You enumerate through the list as a set of name/value pair dictionary entries.</span></span> <span data-ttu-id="df1b1-108">Estos pares nombre-valor están desordenados.</span><span class="sxs-lookup"><span data-stu-id="df1b1-108">These name/value pairs are unordered.</span></span> <span data-ttu-id="df1b1-109">En cualquier momento, puede llamar al método <xref:System.Data.SqlClient.SqlConnection.ResetStatistics%2A> del objeto <xref:System.Data.SqlClient.SqlConnection> para restablecer los contadores.</span><span class="sxs-lookup"><span data-stu-id="df1b1-109">At any time, you can call the <xref:System.Data.SqlClient.SqlConnection.ResetStatistics%2A> method of the <xref:System.Data.SqlClient.SqlConnection> object to reset the counters.</span></span> <span data-ttu-id="df1b1-110">Si no se ha habilitado la recopilación de estadísticas, no se genera una excepción.</span><span class="sxs-lookup"><span data-stu-id="df1b1-110">If statistic gathering has not been enabled, an exception is not generated.</span></span> <span data-ttu-id="df1b1-111">Además, si se llama a <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> sin haber llamado a <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A> primero, los valores recuperados son los valores iniciales de cada entrada.</span><span class="sxs-lookup"><span data-stu-id="df1b1-111">In addition, if <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> is called without <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A> having been called first, the values retrieved are the initial values for each entry.</span></span> <span data-ttu-id="df1b1-112">Si habilita las estadísticas, ejecuta la aplicación durante un tiempo y, a continuación, deshabilita las estadísticas, los valores recuperados reflejarán los valores recopilados hasta el momento en que se deshabilitaron las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="df1b1-112">If you enable statistics, run your application for a while, and then disable statistics, the values retrieved will reflect the values collected up to the point where statistics were disabled.</span></span> <span data-ttu-id="df1b1-113">Todos los valores estadísticos se recopilan por conexión.</span><span class="sxs-lookup"><span data-stu-id="df1b1-113">All statistical values gathered are on a per-connection basis.</span></span>  
  
## <a name="statistical-values-available"></a><span data-ttu-id="df1b1-114">Valores estadísticos disponibles</span><span class="sxs-lookup"><span data-stu-id="df1b1-114">Statistical Values Available</span></span>  

 <span data-ttu-id="df1b1-115">Actualmente hay 18 elementos diferentes disponibles en el proveedor de Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="df1b1-115">Currently there are 18 different items available from the Microsoft SQL Server provider.</span></span> <span data-ttu-id="df1b1-116">Se puede acceder al número de elementos disponibles mediante la propiedad **Count** de la referencia de la interfaz <xref:System.Collections.IDictionary> devuelta por <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A>.</span><span class="sxs-lookup"><span data-stu-id="df1b1-116">The number of items available can be accessed via the **Count** property of the <xref:System.Collections.IDictionary> interface reference returned by <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A>.</span></span> <span data-ttu-id="df1b1-117">Todos los contadores de las estadísticas de proveedor usan el tipo <xref:System.Int64> de Common Language Runtime (**long** en C# y Visual Basic), que tiene un ancho de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="df1b1-117">All of the counters for provider statistics use the common language runtime <xref:System.Int64> type (**long** in C# and Visual Basic), which is 64 bits wide.</span></span> <span data-ttu-id="df1b1-118">El valor máximo del tipo de datos **int64**, como se define en el campo **int64.MaxValue**, es ((2^63)-1)).</span><span class="sxs-lookup"><span data-stu-id="df1b1-118">The maximum value of the **int64** data type, as defined by the **int64.MaxValue** field, is ((2^63)-1)).</span></span> <span data-ttu-id="df1b1-119">Cuando los valores de los contadores alcanzan este valor máximo, ya no se deben considerar precisos.</span><span class="sxs-lookup"><span data-stu-id="df1b1-119">When the values for the counters reach this maximum value, they should no longer be considered accurate.</span></span> <span data-ttu-id="df1b1-120">Esto significa que **int64.MaxValue**-1((2^63)-2) es realmente el valor válido más alto de cualquier estadística.</span><span class="sxs-lookup"><span data-stu-id="df1b1-120">This means that **int64.MaxValue**-1((2^63)-2) is effectively the greatest valid value for any statistic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="df1b1-121">Se usa un diccionario para devolver las estadísticas del proveedor porque el número, los nombres y el orden de las estadísticas devueltas pueden cambiar en el futuro.</span><span class="sxs-lookup"><span data-stu-id="df1b1-121">A dictionary is used for returning provider statistics because the number, names and order of the returned statistics may change in the future.</span></span> <span data-ttu-id="df1b1-122">Las aplicaciones no deben depender de que haya un valor específico en el diccionario, sino que, en su lugar, deben comprobar si el valor está ahí y, en ese caso, crear una rama.</span><span class="sxs-lookup"><span data-stu-id="df1b1-122">Applications should not rely on a specific value being found in the dictionary, but should instead check whether the value is there and branch accordingly.</span></span>  
  
 <span data-ttu-id="df1b1-123">En la tabla siguiente se describen los valores estadísticos actuales disponibles.</span><span class="sxs-lookup"><span data-stu-id="df1b1-123">The following table describes the current statistical values available.</span></span> <span data-ttu-id="df1b1-124">Tenga en cuenta que los nombres de claves de los valores individuales no se localizan en las versiones regionales de Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="df1b1-124">Note that the key names for the individual values are not localized across regional versions of the Microsoft .NET Framework.</span></span>  
  
|<span data-ttu-id="df1b1-125">Nombre de clave</span><span class="sxs-lookup"><span data-stu-id="df1b1-125">Key Name</span></span>|<span data-ttu-id="df1b1-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="df1b1-126">Description</span></span>|  
|--------------|-----------------|  
|`BuffersReceived`|<span data-ttu-id="df1b1-127">Devuelve el número de paquetes de flujo TDS recibidos por el proveedor de SQL Server después de que la aplicación se haya iniciado con el proveedor y haya habilitado las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="df1b1-127">Returns the number of tabular data stream (TDS) packets received by the provider from SQL Server after the application has started using the provider and has enabled statistics.</span></span>|  
|`BuffersSent`|<span data-ttu-id="df1b1-128">Devuelve el número de paquetes TDS enviados a SQL Server por el proveedor una vez que se han habilitado las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="df1b1-128">Returns the number of TDS packets sent to SQL Server by the provider after statistics have been enabled.</span></span> <span data-ttu-id="df1b1-129">Los comandos grandes pueden requerir varios búferes.</span><span class="sxs-lookup"><span data-stu-id="df1b1-129">Large commands can require multiple buffers.</span></span> <span data-ttu-id="df1b1-130">Por ejemplo, si se envía un comando grande al servidor y se requieren seis paquetes, `ServerRoundtrips` se incrementa en uno y `BuffersSent` se incrementa en seis.</span><span class="sxs-lookup"><span data-stu-id="df1b1-130">For example, if a large command is sent to the server and it requires six packets, `ServerRoundtrips` is incremented by one and `BuffersSent` is incremented by six.</span></span>|  
|`BytesReceived`|<span data-ttu-id="df1b1-131">Devuelve el número de bytes de datos de los paquetes TDS recibidos por el proveedor de SQL Server una vez que la aplicación se ha iniciado con el proveedor y ha habilitado las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="df1b1-131">Returns the number of bytes of data in the TDS packets received by the provider from SQL Server once the application has started using the provider and has enabled statistics.</span></span>|  
|`BytesSent`|<span data-ttu-id="df1b1-132">Devuelve el número de bytes de datos enviados a SQL Server en paquetes TDS después de que la aplicación se haya iniciado con el proveedor y haya habilitado las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="df1b1-132">Returns the number of bytes of data sent to SQL Server in TDS packets after the application has started using the provider and has enabled statistics.</span></span>|  
|`ConnectionTime`|<span data-ttu-id="df1b1-133">Cantidad de tiempo (en milisegundos) que se ha abierto la conexión después de habilitarse las estadísticas (el tiempo total de conexión si las estadísticas se han habilitado antes de abrir la conexión).</span><span class="sxs-lookup"><span data-stu-id="df1b1-133">The amount of time (in milliseconds) that the connection has been opened after statistics have been enabled (total connection time if statistics were enabled before opening the connection).</span></span>|  
|`CursorOpens`|<span data-ttu-id="df1b1-134">Devuelve el número de veces que se abrió un cursor a través de la conexión una vez que la aplicación se ha iniciado con el proveedor y ha habilitado las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="df1b1-134">Returns the number of times a cursor was open through the connection once the application has started using the provider and has enabled statistics.</span></span><br /><br /> <span data-ttu-id="df1b1-135">Tenga en cuenta que los resultados de solo lectura y solo avance devueltos por las instrucciones SELECT no se consideran cursores y, por tanto, no afectan a este contador.</span><span class="sxs-lookup"><span data-stu-id="df1b1-135">Note that read-only/forward-only results returned by SELECT statements are not considered cursors and thus do not affect this counter.</span></span>|  
|`ExecutionTime`|<span data-ttu-id="df1b1-136">Devuelve la cantidad acumulada de tiempo (en milisegundos) que ha invertido el proveedor en el procesamiento una vez que se han habilitado las estadísticas, lo que incluye el tiempo dedicado a esperar una respuesta del servidor, así como el tiempo dedicado a ejecutar código en el propio proveedor.</span><span class="sxs-lookup"><span data-stu-id="df1b1-136">Returns the cumulative amount of time (in milliseconds) that the provider has spent processing once statistics have been enabled, including the time spent waiting for replies from the server as well as the time spent executing code in the provider itself.</span></span><br /><br /> <span data-ttu-id="df1b1-137">Las clases que incluyen código de tiempo son:</span><span class="sxs-lookup"><span data-stu-id="df1b1-137">The classes that include timing code are:</span></span><br /><br /> <span data-ttu-id="df1b1-138">SqlConnection</span><span class="sxs-lookup"><span data-stu-id="df1b1-138">SqlConnection</span></span><br /><br /> <span data-ttu-id="df1b1-139">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="df1b1-139">SqlCommand</span></span><br /><br /> <span data-ttu-id="df1b1-140">SqlDataReader</span><span class="sxs-lookup"><span data-stu-id="df1b1-140">SqlDataReader</span></span><br /><br /> <span data-ttu-id="df1b1-141">SqlDataAdapter</span><span class="sxs-lookup"><span data-stu-id="df1b1-141">SqlDataAdapter</span></span><br /><br /> <span data-ttu-id="df1b1-142">SqlTransaction</span><span class="sxs-lookup"><span data-stu-id="df1b1-142">SqlTransaction</span></span><br /><br /> <span data-ttu-id="df1b1-143">SqlCommandBuilder</span><span class="sxs-lookup"><span data-stu-id="df1b1-143">SqlCommandBuilder</span></span><br /><br /> <span data-ttu-id="df1b1-144">Para que el tamaño de los miembros esenciales para el rendimiento sea lo más reducido posible, no se cronometran los siguientes miembros:</span><span class="sxs-lookup"><span data-stu-id="df1b1-144">To keep performance-critical members as small as possible, the following members are not timed:</span></span><br /><br /> <span data-ttu-id="df1b1-145">SqlDataReader</span><span class="sxs-lookup"><span data-stu-id="df1b1-145">SqlDataReader</span></span><br /><br /> <span data-ttu-id="df1b1-146">Este operador [] (todas las sobrecargas)</span><span class="sxs-lookup"><span data-stu-id="df1b1-146">this[] operator (all overloads)</span></span><br /><br /> <span data-ttu-id="df1b1-147">GetBoolean</span><span class="sxs-lookup"><span data-stu-id="df1b1-147">GetBoolean</span></span><br /><br /> <span data-ttu-id="df1b1-148">GetChar</span><span class="sxs-lookup"><span data-stu-id="df1b1-148">GetChar</span></span><br /><br /> <span data-ttu-id="df1b1-149">GetDateTime</span><span class="sxs-lookup"><span data-stu-id="df1b1-149">GetDateTime</span></span><br /><br /> <span data-ttu-id="df1b1-150">GetDecimal</span><span class="sxs-lookup"><span data-stu-id="df1b1-150">GetDecimal</span></span><br /><br /> <span data-ttu-id="df1b1-151">GetDouble</span><span class="sxs-lookup"><span data-stu-id="df1b1-151">GetDouble</span></span><br /><br /> <span data-ttu-id="df1b1-152">GetFloat</span><span class="sxs-lookup"><span data-stu-id="df1b1-152">GetFloat</span></span><br /><br /> <span data-ttu-id="df1b1-153">GetGuid</span><span class="sxs-lookup"><span data-stu-id="df1b1-153">GetGuid</span></span><br /><br /> <span data-ttu-id="df1b1-154">GetInt16</span><span class="sxs-lookup"><span data-stu-id="df1b1-154">GetInt16</span></span><br /><br /> <span data-ttu-id="df1b1-155">GetInt32</span><span class="sxs-lookup"><span data-stu-id="df1b1-155">GetInt32</span></span><br /><br /> <span data-ttu-id="df1b1-156">GetInt64</span><span class="sxs-lookup"><span data-stu-id="df1b1-156">GetInt64</span></span><br /><br /> <span data-ttu-id="df1b1-157">GetName</span><span class="sxs-lookup"><span data-stu-id="df1b1-157">GetName</span></span><br /><br /> <span data-ttu-id="df1b1-158">GetOrdinal</span><span class="sxs-lookup"><span data-stu-id="df1b1-158">GetOrdinal</span></span><br /><br /> <span data-ttu-id="df1b1-159">GetSqlBinary</span><span class="sxs-lookup"><span data-stu-id="df1b1-159">GetSqlBinary</span></span><br /><br /> <span data-ttu-id="df1b1-160">GetSqlBoolean</span><span class="sxs-lookup"><span data-stu-id="df1b1-160">GetSqlBoolean</span></span><br /><br /> <span data-ttu-id="df1b1-161">GetSqlByte</span><span class="sxs-lookup"><span data-stu-id="df1b1-161">GetSqlByte</span></span><br /><br /> <span data-ttu-id="df1b1-162">GetSqlDateTime</span><span class="sxs-lookup"><span data-stu-id="df1b1-162">GetSqlDateTime</span></span><br /><br /> <span data-ttu-id="df1b1-163">GetSqlDecimal</span><span class="sxs-lookup"><span data-stu-id="df1b1-163">GetSqlDecimal</span></span><br /><br /> <span data-ttu-id="df1b1-164">GetSqlDouble</span><span class="sxs-lookup"><span data-stu-id="df1b1-164">GetSqlDouble</span></span><br /><br /> <span data-ttu-id="df1b1-165">GetSqlGuid</span><span class="sxs-lookup"><span data-stu-id="df1b1-165">GetSqlGuid</span></span><br /><br /> <span data-ttu-id="df1b1-166">GetSqlInt16</span><span class="sxs-lookup"><span data-stu-id="df1b1-166">GetSqlInt16</span></span><br /><br /> <span data-ttu-id="df1b1-167">GetSqlInt32</span><span class="sxs-lookup"><span data-stu-id="df1b1-167">GetSqlInt32</span></span><br /><br /> <span data-ttu-id="df1b1-168">GetSqlInt64</span><span class="sxs-lookup"><span data-stu-id="df1b1-168">GetSqlInt64</span></span><br /><br /> <span data-ttu-id="df1b1-169">GetSqlMoney</span><span class="sxs-lookup"><span data-stu-id="df1b1-169">GetSqlMoney</span></span><br /><br /> <span data-ttu-id="df1b1-170">GetSqlSingle</span><span class="sxs-lookup"><span data-stu-id="df1b1-170">GetSqlSingle</span></span><br /><br /> <span data-ttu-id="df1b1-171">GetSqlString</span><span class="sxs-lookup"><span data-stu-id="df1b1-171">GetSqlString</span></span><br /><br /> <span data-ttu-id="df1b1-172">GetString</span><span class="sxs-lookup"><span data-stu-id="df1b1-172">GetString</span></span><br /><br /> <span data-ttu-id="df1b1-173">IsDBNull</span><span class="sxs-lookup"><span data-stu-id="df1b1-173">IsDBNull</span></span>|  
|`IduCount`|<span data-ttu-id="df1b1-174">Devuelve el número total de instrucciones INSERT, DELETE y UPDATE ejecutadas a través de la conexión una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="df1b1-174">Returns the total number of INSERT, DELETE, and UPDATE statements executed through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
|`IduRows`|<span data-ttu-id="df1b1-175">Devuelve el número total de filas afectadas por las instrucciones INSERT, DELETE y UPDATE ejecutadas a través de la conexión una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="df1b1-175">Returns the total number of rows affected by INSERT, DELETE, and UPDATE statements executed through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
|`NetworkServerTime`|<span data-ttu-id="df1b1-176">Devuelve la cantidad acumulada de tiempo (en milisegundos) que el proveedor ha dedicado a esperar una respuesta del servidor una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="df1b1-176">Returns the cumulative amount of time (in milliseconds) that the provider spent waiting for replies from the server once the application has started using the provider and has enabled statistics.</span></span>|  
|`PreparedExecs`|<span data-ttu-id="df1b1-177">Devuelve el número de comandos preparados que se ejecutan a través de la conexión una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="df1b1-177">Returns the number of prepared commands executed through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
|`Prepares`|<span data-ttu-id="df1b1-178">Devuelve el número de instrucciones preparadas a través de la conexión una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="df1b1-178">Returns the number of statements prepared through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
|`SelectCount`|<span data-ttu-id="df1b1-179">Devuelve el número de instrucciones SELECT ejecutadas a través de la conexión una vez que la aplicación se ha iniciado con el proveedor y se han habilitado las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="df1b1-179">Returns the number of SELECT statements executed through the connection once the application has started using the provider and has enabled statistics.</span></span> <span data-ttu-id="df1b1-180">Esto incluye las instrucciones FETCH para recuperar las filas de los cursores, y el recuento de las instrucciones SELECT se actualiza cuando se alcanza el final de un objeto <xref:System.Data.SqlClient.SqlDataReader>.</span><span class="sxs-lookup"><span data-stu-id="df1b1-180">This includes FETCH statements to retrieve rows from cursors, and the count for SELECT statements is updated when the end of a <xref:System.Data.SqlClient.SqlDataReader> is reached.</span></span>|  
|`SelectRows`|<span data-ttu-id="df1b1-181">Devuelve el número de filas seleccionadas una vez que se ha iniciado la aplicación con el proveedor y se han habilitado las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="df1b1-181">Returns the number of rows selected once the application has started using the provider and has enabled statistics.</span></span> <span data-ttu-id="df1b1-182">Este contador refleja todas las filas generadas por las instrucciones SQL, incluso las que el autor de la llamada no usó realmente.</span><span class="sxs-lookup"><span data-stu-id="df1b1-182">This counter reflects all the rows generated by SQL statements, even those that were not actually consumed by the caller.</span></span> <span data-ttu-id="df1b1-183">Por ejemplo, cerrar un lector de datos antes de leer todo el conjunto de resultados no afectaría al recuento.</span><span class="sxs-lookup"><span data-stu-id="df1b1-183">For example, closing a data reader before reading the entire result set would not affect the count.</span></span> <span data-ttu-id="df1b1-184">Esto incluye las filas recuperadas de los cursores a través de las instrucciones FETCH.</span><span class="sxs-lookup"><span data-stu-id="df1b1-184">This includes the rows retrieved from cursors through FETCH statements.</span></span>|  
|`ServerRoundtrips`|<span data-ttu-id="df1b1-185">Devuelve el número de veces que la conexión envió comandos al servidor y recibió una respuesta una vez que la aplicación se ha iniciado con el proveedor y se han habilitado las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="df1b1-185">Returns the number of times the connection sent commands to the server and got a reply back once the application has started using the provider and has enabled statistics.</span></span>|  
|`SumResultSets`|<span data-ttu-id="df1b1-186">Devuelve el número de conjuntos de resultados que se han utilizado una vez que la aplicación se ha iniciado con el proveedor y se han habilitado las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="df1b1-186">Returns the number of result sets that have been used once the application has started using the provider and has enabled statistics.</span></span> <span data-ttu-id="df1b1-187">Por ejemplo, esto incluiría cualquier conjunto de resultados devuelto al cliente.</span><span class="sxs-lookup"><span data-stu-id="df1b1-187">For example this would include any result set returned to the client.</span></span> <span data-ttu-id="df1b1-188">En el caso de los cursores, cada operación de captura o bloqueo se considera un conjunto de resultados independiente.</span><span class="sxs-lookup"><span data-stu-id="df1b1-188">For cursors, each fetch or block-fetch operation is considered an independent result set.</span></span>|  
|`Transactions`|<span data-ttu-id="df1b1-189">Devuelve el número de transacciones de usuario que se inician una vez que la aplicación se ha iniciado con el proveedor y se han habilitado las estadísticas, incluidas las reversiones.</span><span class="sxs-lookup"><span data-stu-id="df1b1-189">Returns the number of user transactions started once the application has started using the provider and has enabled statistics, including rollbacks.</span></span> <span data-ttu-id="df1b1-190">Si una conexión se ejecuta con la confirmación automática activada, cada comando se considera una transacción.</span><span class="sxs-lookup"><span data-stu-id="df1b1-190">If a connection is running with auto commit on, each command is considered a transaction.</span></span><br /><br /> <span data-ttu-id="df1b1-191">Este contador incrementa el recuento de transacciones en cuanto se ejecuta una instrucción BEGIN TRAN, independientemente de si la transacción se confirma o se revierte más tarde.</span><span class="sxs-lookup"><span data-stu-id="df1b1-191">This counter increments the transaction count as soon as a BEGIN TRAN statement is executed, regardless of whether the transaction is committed or rolled back later.</span></span>|  
|`UnpreparedExecs`|<span data-ttu-id="df1b1-192">Devuelve el número de instrucciones no preparadas que se ejecutan a través de la conexión una vez que la aplicación se ha iniciado con el proveedor y ha habilitado las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="df1b1-192">Returns the number of unprepared statements executed through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
  
### <a name="retrieving-a-value"></a><span data-ttu-id="df1b1-193">Recuperación de un valor</span><span class="sxs-lookup"><span data-stu-id="df1b1-193">Retrieving a Value</span></span>  

 <span data-ttu-id="df1b1-194">La siguiente aplicación de consola muestra cómo habilitar las estadísticas en una conexión, recuperar cuatro valores de estadística individuales y escribirlos en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="df1b1-194">The following console application shows how to enable statistics on a connection, retrieve four individual statistic values, and write them out to the console window.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="df1b1-195">En el siguiente ejemplo se usa la base de datos de ejemplo **AdventureWorks** que se incluye con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="df1b1-195">The following example uses the sample **AdventureWorks** database included with SQL Server.</span></span> <span data-ttu-id="df1b1-196">La cadena de conexión proporcionada en el código de ejemplo da por sentado que la base de datos está instalada y disponible en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="df1b1-196">The connection string provided in the sample code assumes the database is installed and available on the local computer.</span></span> <span data-ttu-id="df1b1-197">Modifique la cadena de conexión según sea necesario para el entorno.</span><span class="sxs-lookup"><span data-stu-id="df1b1-197">Modify the connection string as necessary for your environment.</span></span>  
  
```vb  
Option Strict On  
  
Imports System  
Imports System.Collections  
Imports System.Data  
Imports System.Data.SqlClient  
  
Module Module1  
  
  Sub Main()  
    Dim connectionString As String = GetConnectionString()  
  
    Using awConnection As New SqlConnection(connectionString)  
      ' StatisticsEnabled is False by default.  
      ' It must be set to True to start the
      ' statistic collection process.  
      awConnection.StatisticsEnabled = True  
  
      Dim productSQL As String = "SELECT * FROM Production.Product"  
      Dim productAdapter As _  
          New SqlDataAdapter(productSQL, awConnection)  
  
      Dim awDataSet As New DataSet()  
  
      awConnection.Open()  
  
      productAdapter.Fill(awDataSet, "ProductTable")  
  
      ' Retrieve the current statistics as  
      ' a collection of values at this point  
      ' and time.  
      Dim currentStatistics As IDictionary = _  
          awConnection.RetrieveStatistics()  
  
      Console.WriteLine("Total Counters: " & _  
          currentStatistics.Count.ToString())  
      Console.WriteLine()  
  
      ' Retrieve a few individual values  
      ' related to the previous command.  
      Dim bytesReceived As Long = _  
          CLng(currentStatistics.Item("BytesReceived"))  
      Dim bytesSent As Long = _  
          CLng(currentStatistics.Item("BytesSent"))  
      Dim selectCount As Long = _  
          CLng(currentStatistics.Item("SelectCount"))  
      Dim selectRows As Long = _  
          CLng(currentStatistics.Item("SelectRows"))  
  
      Console.WriteLine("BytesReceived: " & bytesReceived.ToString())  
      Console.WriteLine("BytesSent: " & bytesSent.ToString())  
      Console.WriteLine("SelectCount: " & selectCount.ToString())  
      Console.WriteLine("SelectRows: " & selectRows.ToString())  
  
      Console.WriteLine()  
      Console.WriteLine("Press any key to continue")  
      Console.ReadLine()  
    End Using  
  
  End Sub  
  
  Function GetConnectionString() As String  
    ' To avoid storing the connection string in your code,  
    ' you can retrieve it from a configuration file.  
    Return "Data Source=localhost;Integrated Security=SSPI;" & _  
      "Initial Catalog=AdventureWorks"  
  End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Collections;  
using System.Collections.Generic;  
using System.Data;  
using System.Data.SqlClient;  
  
namespace CS_Stats_Console_GetValue  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string connectionString = GetConnectionString();  
  
      using (SqlConnection awConnection =
        new SqlConnection(connectionString))  
      {  
        // StatisticsEnabled is False by default.  
        // It must be set to True to start the
        // statistic collection process.  
        awConnection.StatisticsEnabled = true;  
  
        string productSQL = "SELECT * FROM Production.Product";  
        SqlDataAdapter productAdapter =
          new SqlDataAdapter(productSQL, awConnection);  
  
        DataSet awDataSet = new DataSet();  
  
        awConnection.Open();  
  
        productAdapter.Fill(awDataSet, "ProductTable");  
        // Retrieve the current statistics as  
        // a collection of values at this point  
        // and time.  
        IDictionary currentStatistics =  
          awConnection.RetrieveStatistics();  
  
        Console.WriteLine("Total Counters: " +  
          currentStatistics.Count.ToString());  
        Console.WriteLine();  
  
        // Retrieve a few individual values  
        // related to the previous command.  
        long bytesReceived =  
            (long) currentStatistics["BytesReceived"];  
        long bytesSent =  
            (long) currentStatistics["BytesSent"];  
        long selectCount =  
            (long) currentStatistics["SelectCount"];  
        long selectRows =  
            (long) currentStatistics["SelectRows"];  
  
        Console.WriteLine("BytesReceived: " +  
            bytesReceived.ToString());  
        Console.WriteLine("BytesSent: " +  
            bytesSent.ToString());  
        Console.WriteLine("SelectCount: " +  
            selectCount.ToString());  
        Console.WriteLine("SelectRows: " +  
            selectRows.ToString());  
  
        Console.WriteLine();  
        Console.WriteLine("Press any key to continue");  
        Console.ReadLine();  
      }  
  
    }  
    private static string GetConnectionString()  
    {  
      // To avoid storing the connection string in your code,  
      // you can retrieve it from a configuration file.  
      return "Data Source=localhost;Integrated Security=SSPI;" +
        "Initial Catalog=AdventureWorks";  
    }  
  }  
}  
```  
  
### <a name="retrieving-all-values"></a><span data-ttu-id="df1b1-198">Recuperación de todos los valores</span><span class="sxs-lookup"><span data-stu-id="df1b1-198">Retrieving All Values</span></span>  

 <span data-ttu-id="df1b1-199">La siguiente aplicación de consola muestra cómo habilitar las estadísticas en una conexión, recuperar todos los valores de estadística disponibles mediante el enumerador y escribirlos en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="df1b1-199">The following console application shows how to enable statistics on a connection, retrieve all available statistic values using the enumerator, and write them to the console window.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="df1b1-200">En el siguiente ejemplo se usa la base de datos de ejemplo **AdventureWorks** que se incluye con SQL Server.</span><span class="sxs-lookup"><span data-stu-id="df1b1-200">The following example uses the sample **AdventureWorks** database included with SQL Server.</span></span> <span data-ttu-id="df1b1-201">La cadena de conexión proporcionada en el código de ejemplo da por sentado que la base de datos está instalada y disponible en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="df1b1-201">The connection string provided in the sample code assumes the database is installed and available on the local computer.</span></span> <span data-ttu-id="df1b1-202">Modifique la cadena de conexión según sea necesario para el entorno.</span><span class="sxs-lookup"><span data-stu-id="df1b1-202">Modify the connection string as necessary for your environment.</span></span>  
  
```vb  
Option Strict On  
  
Imports System  
Imports System.Collections  
Imports System.Data  
Imports System.Data.SqlClient  
  
Module Module1  
  Sub Main()  
    Dim connectionString As String = GetConnectionString()  
  
    Using awConnection As New SqlConnection(connectionString)  
      ' StatisticsEnabled is False by default.  
      ' It must be set to True to start the
      ' statistic collection process.  
      awConnection.StatisticsEnabled = True  
  
      Dim productSQL As String = "SELECT * FROM Production.Product"  
      Dim productAdapter As _  
          New SqlDataAdapter(productSQL, awConnection)  
  
      Dim awDataSet As New DataSet()  
  
      awConnection.Open()  
  
      productAdapter.Fill(awDataSet, "ProductTable")  
  
      ' Retrieve the current statistics as  
      ' a collection of values at this point  
      ' and time.  
      Dim currentStatistics As IDictionary = _  
          awConnection.RetrieveStatistics()  
  
      Console.WriteLine("Total Counters: " & _  
          currentStatistics.Count.ToString())  
      Console.WriteLine()  
  
      Console.WriteLine("Key Name and Value")  
  
      ' Note the entries are unsorted.  
      For Each entry As DictionaryEntry In currentStatistics  
        Console.WriteLine(entry.Key.ToString() & _  
            ": " & entry.Value.ToString())  
      Next  
  
      Console.WriteLine()  
      Console.WriteLine("Press any key to continue")  
      Console.ReadLine()  
    End Using  
  
  End Sub  
  
  Function GetConnectionString() As String  
    ' To avoid storing the connection string in your code,  
    ' you can retrieve it from a configuration file.  
    Return "Data Source=localhost;Integrated Security=SSPI;" & _  
      "Initial Catalog=AdventureWorks"  
  End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Collections;  
using System.Collections.Generic;  
using System.Text;  
using System.Data;  
using System.Data.SqlClient;  
  
namespace CS_Stats_Console_GetAll  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string connectionString = GetConnectionString();  
  
      using (SqlConnection awConnection =
        new SqlConnection(connectionString))  
      {  
        // StatisticsEnabled is False by default.  
        // It must be set to True to start the
        // statistic collection process.  
        awConnection.StatisticsEnabled = true;  
  
        string productSQL = "SELECT * FROM Production.Product";  
        SqlDataAdapter productAdapter =  
            new SqlDataAdapter(productSQL, awConnection);  
  
        DataSet awDataSet = new DataSet();  
  
        awConnection.Open();  
  
        productAdapter.Fill(awDataSet, "ProductTable");  
  
        // Retrieve the current statistics as  
        // a collection of values at this point  
        // and time.  
        IDictionary currentStatistics =  
            awConnection.RetrieveStatistics();  
  
        Console.WriteLine("Total Counters: " +  
            currentStatistics.Count.ToString());  
        Console.WriteLine();  
  
        Console.WriteLine("Key Name and Value");  
  
        // Note the entries are unsorted.  
        foreach (DictionaryEntry entry in currentStatistics)  
        {  
          Console.WriteLine(entry.Key.ToString() +  
              ": " + entry.Value.ToString());  
        }  
  
        Console.WriteLine();  
        Console.WriteLine("Press any key to continue");  
        Console.ReadLine();  
      }  
  
    }  
    private static string GetConnectionString()  
    {  
      // To avoid storing the connection string in your code,  
      // you can retrieve it from a configuration file.  
      return "Data Source=localhost;Integrated Security=SSPI;" +
        "Initial Catalog=AdventureWorks";  
    }  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="df1b1-203">Vea también</span><span class="sxs-lookup"><span data-stu-id="df1b1-203">See also</span></span>

- [<span data-ttu-id="df1b1-204">SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="df1b1-204">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="df1b1-205">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="df1b1-205">ADO.NET Overview</span></span>](../ado-net-overview.md)
