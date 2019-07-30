---
title: Introducción a Azure Table Storage mediante F#
description: Almacene datos estructurados en la nube mediante Azure Table Storage o Azure Cosmos DB.
author: sylvanc
ms.date: 03/26/2018
ms.openlocfilehash: c8ab2d61048523ac52f305c7bd035c73ca0d3f60
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630472"
---
# <a name="get-started-with-azure-table-storage-and-the-azure-cosmos-db-table-api-using-f"></a><span data-ttu-id="cd15f-103">Introducción a Azure Table Storage y el Table API de Azure Cosmos DB con F\#</span><span class="sxs-lookup"><span data-stu-id="cd15f-103">Get started with Azure Table storage and the Azure Cosmos DB Table API using F\#</span></span>

<span data-ttu-id="cd15f-104">Azure Table Storage es un servicio que almacena datos de NoSQL estructurados en la nube.</span><span class="sxs-lookup"><span data-stu-id="cd15f-104">Azure Table storage is a service that stores structured NoSQL data in the cloud.</span></span> <span data-ttu-id="cd15f-105">Table Storage es un almacén de claves y atributos con un diseño sin esquema.</span><span class="sxs-lookup"><span data-stu-id="cd15f-105">Table storage is a key/attribute store with a schemaless design.</span></span> <span data-ttu-id="cd15f-106">Dado que el almacenamiento de tabla no tiene esquemas, es fácil adaptar los datos a medida que evolucionen las necesidades de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cd15f-106">Because Table storage is schemaless, it's easy to adapt your data as the needs of your application evolve.</span></span> <span data-ttu-id="cd15f-107">El acceso a los datos es rápido y rentable para todos los tipos de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="cd15f-107">Access to data is fast and cost-effective for all kinds of applications.</span></span> <span data-ttu-id="cd15f-108">Normalmente, el almacenamiento de tablas es significativamente menor que el de SQL tradicional para volúmenes de datos similares.</span><span class="sxs-lookup"><span data-stu-id="cd15f-108">Table storage is typically significantly lower in cost than traditional SQL for similar volumes of data.</span></span>

<span data-ttu-id="cd15f-109">Puede usar Table Storage para almacenar conjuntos de datos flexibles, como datos de usuario para aplicaciones Web, libretas de direcciones, información de dispositivos y cualquier otro tipo de metadatos que requiera el servicio.</span><span class="sxs-lookup"><span data-stu-id="cd15f-109">You can use Table storage to store flexible datasets, such as user data for web applications, address books, device information, and any other type of metadata that your service requires.</span></span> <span data-ttu-id="cd15f-110">Puede almacenar cualquier número de entidades en una tabla y una cuenta de almacenamiento puede contener cualquier número de tablas, hasta el límite de capacidad de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="cd15f-110">You can store any number of entities in a table, and a storage account may contain any number of tables, up to the capacity limit of the storage account.</span></span>

<span data-ttu-id="cd15f-111">Azure Cosmos DB proporciona el Table API para las aplicaciones escritas para Azure Table Storage y que necesitan funcionalidades Premium como:</span><span class="sxs-lookup"><span data-stu-id="cd15f-111">Azure Cosmos DB provides the Table API for applications that are written for Azure Table storage and that require premium capabilities such as:</span></span>

- <span data-ttu-id="cd15f-112">Distribución global llave en mano.</span><span class="sxs-lookup"><span data-stu-id="cd15f-112">Turnkey global distribution.</span></span>
- <span data-ttu-id="cd15f-113">Rendimiento dedicado en todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="cd15f-113">Dedicated throughput worldwide.</span></span>
- <span data-ttu-id="cd15f-114">Latencias de milisegundos de un solo dígito en el percentil valores percentil.</span><span class="sxs-lookup"><span data-stu-id="cd15f-114">Single-digit millisecond latencies at the 99th percentile.</span></span>
- <span data-ttu-id="cd15f-115">Alta disponibilidad garantizada.</span><span class="sxs-lookup"><span data-stu-id="cd15f-115">Guaranteed high availability.</span></span>
- <span data-ttu-id="cd15f-116">Indexación secundaria automática.</span><span class="sxs-lookup"><span data-stu-id="cd15f-116">Automatic secondary indexing.</span></span>

<span data-ttu-id="cd15f-117">Las aplicaciones escritas para Azure Table Storage pueden migrar a Azure Cosmos DB mediante el Table API sin necesidad de realizar ningún cambio en el código y aprovechar las ventajas de las funcionalidades Premium.</span><span class="sxs-lookup"><span data-stu-id="cd15f-117">Applications written for Azure Table storage can migrate to Azure Cosmos DB by using the Table API with no code changes and take advantage of premium capabilities.</span></span> <span data-ttu-id="cd15f-118">El Table API tiene SDK de cliente disponibles para .NET, Java, Python y node. js.</span><span class="sxs-lookup"><span data-stu-id="cd15f-118">The Table API has client SDKs available for .NET, Java, Python, and Node.js.</span></span>

<span data-ttu-id="cd15f-119">Para obtener más información, vea [Introducción a la Table API de Azure Cosmos dB](https://docs.microsoft.com/azure/cosmos-db/table-introduction).</span><span class="sxs-lookup"><span data-stu-id="cd15f-119">For more information, see [Introduction to Azure Cosmos DB Table API](https://docs.microsoft.com/azure/cosmos-db/table-introduction).</span></span>

## <a name="about-this-tutorial"></a><span data-ttu-id="cd15f-120">Acerca de este tutorial</span><span class="sxs-lookup"><span data-stu-id="cd15f-120">About this tutorial</span></span>

<span data-ttu-id="cd15f-121">En este tutorial se muestra cómo F# escribir código para realizar algunas tareas comunes con el almacenamiento de tablas de Azure o el Table API Azure Cosmos dB, lo que incluye crear y eliminar una tabla e insertar, actualizar, eliminar y consultar datos de tabla.</span><span class="sxs-lookup"><span data-stu-id="cd15f-121">This tutorial shows how to write F# code to do some common tasks using Azure Table storage or the Azure Cosmos DB Table API, including creating and deleting a table and inserting, updating, deleting, and querying table data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cd15f-122">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="cd15f-122">Prerequisites</span></span>

<span data-ttu-id="cd15f-123">Para usar esta guía, primero debe [crear una cuenta de almacenamiento de Azure o una](/azure/storage/storage-create-storage-account) cuenta de [Azure Cosmos dB](https://azure.microsoft.com/try/cosmosdb/).</span><span class="sxs-lookup"><span data-stu-id="cd15f-123">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account) or [Azure Cosmos DB account](https://azure.microsoft.com/try/cosmosdb/).</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="cd15f-124">Creación de F# un script e F# Inicio interactivo</span><span class="sxs-lookup"><span data-stu-id="cd15f-124">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="cd15f-125">Los ejemplos de este artículo se pueden usar en una F# aplicación o en un F# script.</span><span class="sxs-lookup"><span data-stu-id="cd15f-125">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="cd15f-126">Para crear un F# script, cree un archivo con la `.fsx` extensión, por ejemplo `tables.fsx`, en el F# entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="cd15f-126">To create an F# script, create a file with the `.fsx` extension, for example `tables.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="cd15f-127">A continuación, use un [Administrador de paquetes](package-management.md) como [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) para instalar `WindowsAzure.Storage` el paquete y `WindowsAzure.Storage.dll` la referencia en el script `#r` mediante una directiva.</span><span class="sxs-lookup"><span data-stu-id="cd15f-127">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span> <span data-ttu-id="cd15f-128">Vuelva a `Microsoft.WindowsAzure.ConfigurationManager` hacerlo con el fin de obtener el espacio de nombres Microsoft. Azure.</span><span class="sxs-lookup"><span data-stu-id="cd15f-128">Do it again for `Microsoft.WindowsAzure.ConfigurationManager` in order to get the Microsoft.Azure namespace.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="cd15f-129">Agregar declaraciones de espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="cd15f-129">Add namespace declarations</span></span>

<span data-ttu-id="cd15f-130">Agregue las siguientes `open` instrucciones a la parte superior `tables.fsx` del archivo:</span><span class="sxs-lookup"><span data-stu-id="cd15f-130">Add the following `open` statements to the top of the `tables.fsx` file:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L1-L5)]

### <a name="get-your-azure-storage-connection-string"></a><span data-ttu-id="cd15f-131">Obtener la cadena de conexión de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="cd15f-131">Get your Azure Storage connection string</span></span>

<span data-ttu-id="cd15f-132">Si se va a conectar a Azure Storage Table service, necesitará la cadena de conexión para este tutorial.</span><span class="sxs-lookup"><span data-stu-id="cd15f-132">If you're connecting to Azure Storage Table service, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="cd15f-133">Puede copiar la cadena de conexión desde el Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="cd15f-133">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="cd15f-134">Para obtener más información sobre las cadenas de conexión, consulte Configuración de las [cadenas de conexión de almacenamiento](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="cd15f-134">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

### <a name="get-your-azure-cosmos-db-connection-string"></a><span data-ttu-id="cd15f-135">Obtener la cadena de conexión de Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="cd15f-135">Get your Azure Cosmos DB connection string</span></span>

<span data-ttu-id="cd15f-136">Si se va a conectar a Azure Cosmos DB, necesitará la cadena de conexión para este tutorial.</span><span class="sxs-lookup"><span data-stu-id="cd15f-136">If you're connecting to Azure Cosmos DB, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="cd15f-137">Puede copiar la cadena de conexión desde el Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="cd15f-137">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="cd15f-138">En el Azure portal, en la cuenta de Cosmos dB, vaya a **configuración** > **cadena de conexión**y haga clic en el botón **copiar** para copiar la cadena de conexión principal.</span><span class="sxs-lookup"><span data-stu-id="cd15f-138">In the Azure portal, in your Cosmos DB account, go to **Settings** > **Connection String**, and click the **Copy** button to copy your Primary Connection String.</span></span> 

<span data-ttu-id="cd15f-139">En el tutorial, escriba la cadena de conexión en el script, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cd15f-139">For the tutorial, enter your connection string in your script, like the following example:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L11-L11)]

<span data-ttu-id="cd15f-140">Sin embargo, esto **no se recomienda** para los proyectos reales.</span><span class="sxs-lookup"><span data-stu-id="cd15f-140">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="cd15f-141">La clave de la cuenta de almacenamiento es similar a la contraseña raíz de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="cd15f-141">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="cd15f-142">Siempre debe proteger la clave de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="cd15f-142">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="cd15f-143">Evite distribuirla a otros usuarios, codificarla de forma rígida o guardarla en un archivo de texto sin formato al que puedan acceder otras personas.</span><span class="sxs-lookup"><span data-stu-id="cd15f-143">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="cd15f-144">Puede volver a generar la clave mediante Azure portal si cree que puede estar en peligro.</span><span class="sxs-lookup"><span data-stu-id="cd15f-144">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="cd15f-145">En el caso de las aplicaciones reales, la mejor manera de mantener la cadena de conexión de almacenamiento se encuentra en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="cd15f-145">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="cd15f-146">Para capturar la cadena de conexión de un archivo de configuración, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cd15f-146">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L13-L15)]

<span data-ttu-id="cd15f-147">El uso de Azure Configuration Manager es opcional.</span><span class="sxs-lookup"><span data-stu-id="cd15f-147">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="cd15f-148">También puede usar una API, como el tipo de `ConfigurationManager` .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cd15f-148">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="cd15f-149">Analizar la cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="cd15f-149">Parse the connection string</span></span>

<span data-ttu-id="cd15f-150">Para analizar la cadena de conexión, use:</span><span class="sxs-lookup"><span data-stu-id="cd15f-150">To parse the connection string, use:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L21-L22)]

<span data-ttu-id="cd15f-151">Esto devuelve un `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="cd15f-151">This returns a `CloudStorageAccount`.</span></span>

### <a name="create-the-table-service-client"></a><span data-ttu-id="cd15f-152">Creación del cliente de Table service</span><span class="sxs-lookup"><span data-stu-id="cd15f-152">Create the Table service client</span></span>

<span data-ttu-id="cd15f-153">La `CloudTableClient` clase permite recuperar tablas y entidades en el almacenamiento de tablas.</span><span class="sxs-lookup"><span data-stu-id="cd15f-153">The `CloudTableClient` class enables you to retrieve tables and entities in Table storage.</span></span> <span data-ttu-id="cd15f-154">Esta es una forma de crear el cliente del servicio:</span><span class="sxs-lookup"><span data-stu-id="cd15f-154">Here's one way to create the service client:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L28-L29)]

<span data-ttu-id="cd15f-155">Ahora está listo para escribir código que lee datos de y escribe datos en el almacenamiento de tablas.</span><span class="sxs-lookup"><span data-stu-id="cd15f-155">Now you are ready to write code that reads data from and writes data to Table storage.</span></span>

### <a name="create-a-table"></a><span data-ttu-id="cd15f-156">Creación de una tabla</span><span class="sxs-lookup"><span data-stu-id="cd15f-156">Create a table</span></span>

<span data-ttu-id="cd15f-157">En este ejemplo se muestra cómo crear una tabla si aún no existe:</span><span class="sxs-lookup"><span data-stu-id="cd15f-157">This example shows how to create a table if it does not already exist:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L35-L39)]

### <a name="add-an-entity-to-a-table"></a><span data-ttu-id="cd15f-158">Agregar una entidad a una tabla</span><span class="sxs-lookup"><span data-stu-id="cd15f-158">Add an entity to a table</span></span>

<span data-ttu-id="cd15f-159">Una entidad debe tener un tipo que herede de `TableEntity`.</span><span class="sxs-lookup"><span data-stu-id="cd15f-159">An entity has to have a type that inherits from `TableEntity`.</span></span> <span data-ttu-id="cd15f-160">Puede extender `TableEntity` de la forma que desee, pero el tipo *debe* tener un constructor sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="cd15f-160">You can extend `TableEntity` in any way you like, but your type *must* have a parameter-less constructor.</span></span> <span data-ttu-id="cd15f-161">Solo las propiedades que tienen `get` y `set` se almacenan en la tabla de Azure.</span><span class="sxs-lookup"><span data-stu-id="cd15f-161">Only properties that have both `get` and `set` are stored in your Azure Table.</span></span>

<span data-ttu-id="cd15f-162">La clave de partición y de fila de una entidad identifica de forma única la entidad en la tabla.</span><span class="sxs-lookup"><span data-stu-id="cd15f-162">An entity's partition and row key uniquely identify the entity in the table.</span></span> <span data-ttu-id="cd15f-163">Las entidades con la misma clave de partición se pueden consultar más rápidamente que las que tienen claves de partición diferentes, pero el uso de claves de partición diversas permite una mayor escalabilidad de las operaciones paralelas.</span><span class="sxs-lookup"><span data-stu-id="cd15f-163">Entities with the same partition key can be queried faster than those with different partition keys, but using diverse partition keys allows for greater scalability of parallel operations.</span></span>

<span data-ttu-id="cd15f-164">A continuación se muestra un ejemplo `Customer` de que `lastName` usa como clave de partición y `firstName` como clave de fila.</span><span class="sxs-lookup"><span data-stu-id="cd15f-164">Here's an example of a `Customer` that uses the `lastName` as the partition key and the `firstName` as the row key.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L45-L52)]

<span data-ttu-id="cd15f-165">Ahora, `Customer` agregue a la tabla.</span><span class="sxs-lookup"><span data-stu-id="cd15f-165">Now add `Customer` to the table.</span></span> <span data-ttu-id="cd15f-166">Para ello, cree un `TableOperation` objeto que se ejecute en la tabla.</span><span class="sxs-lookup"><span data-stu-id="cd15f-166">To do so, create a `TableOperation` that executes on the table.</span></span> <span data-ttu-id="cd15f-167">En este caso, se crea una `Insert` operación.</span><span class="sxs-lookup"><span data-stu-id="cd15f-167">In this case, you create an `Insert` operation.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L54-L55)]

### <a name="insert-a-batch-of-entities"></a><span data-ttu-id="cd15f-168">Insertar un lote de entidades</span><span class="sxs-lookup"><span data-stu-id="cd15f-168">Insert a batch of entities</span></span>

<span data-ttu-id="cd15f-169">Puede insertar un lote de entidades en una tabla mediante una sola operación de escritura.</span><span class="sxs-lookup"><span data-stu-id="cd15f-169">You can insert a batch of entities into a table using a single write operation.</span></span> <span data-ttu-id="cd15f-170">Las operaciones por lotes permiten combinar operaciones en una sola ejecución, pero tienen algunas restricciones:</span><span class="sxs-lookup"><span data-stu-id="cd15f-170">Batch operations allow you to combine operations into a single execution, but they have some restrictions:</span></span>

- <span data-ttu-id="cd15f-171">Puede realizar actualizaciones, eliminaciones e inserciones en la misma operación por lotes.</span><span class="sxs-lookup"><span data-stu-id="cd15f-171">You can perform updates, deletes, and inserts in the same batch operation.</span></span>
- <span data-ttu-id="cd15f-172">Una operación por lotes puede incluir hasta 100 entidades.</span><span class="sxs-lookup"><span data-stu-id="cd15f-172">A batch operation can include up to 100 entities.</span></span>
- <span data-ttu-id="cd15f-173">Todas las entidades de una operación por lotes deben tener la misma clave de partición.</span><span class="sxs-lookup"><span data-stu-id="cd15f-173">All entities in a batch operation must have the same partition key.</span></span>
- <span data-ttu-id="cd15f-174">Aunque es posible realizar una consulta en una operación por lotes, debe ser la única operación del lote.</span><span class="sxs-lookup"><span data-stu-id="cd15f-174">While it is possible to perform a query in a batch operation, it must be the only operation in the batch.</span></span>

<span data-ttu-id="cd15f-175">Este es un código que combina dos inserciones en una operación por lotes:</span><span class="sxs-lookup"><span data-stu-id="cd15f-175">Here's some code that combines two inserts into a batch operation:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L62-L71)]

### <a name="retrieve-all-entities-in-a-partition"></a><span data-ttu-id="cd15f-176">Recuperar todas las entidades de una partición</span><span class="sxs-lookup"><span data-stu-id="cd15f-176">Retrieve all entities in a partition</span></span>

<span data-ttu-id="cd15f-177">Para consultar una tabla de todas las entidades de una partición, use `TableQuery` un objeto.</span><span class="sxs-lookup"><span data-stu-id="cd15f-177">To query a table for all entities in a partition, use a `TableQuery` object.</span></span> <span data-ttu-id="cd15f-178">Aquí, se filtran las entidades en las que "Smith" es la clave de partición.</span><span class="sxs-lookup"><span data-stu-id="cd15f-178">Here, you filter for entities where "Smith" is the partition key.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L77-L82)]

<span data-ttu-id="cd15f-179">Ahora imprime los resultados:</span><span class="sxs-lookup"><span data-stu-id="cd15f-179">You now print the results:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L84-L85)]

### <a name="retrieve-a-range-of-entities-in-a-partition"></a><span data-ttu-id="cd15f-180">Recuperar un intervalo de entidades de una partición</span><span class="sxs-lookup"><span data-stu-id="cd15f-180">Retrieve a range of entities in a partition</span></span>

<span data-ttu-id="cd15f-181">Si no desea consultar todas las entidades de una partición, puede especificar un intervalo combinando el filtro de clave de partición con un filtro de clave de fila.</span><span class="sxs-lookup"><span data-stu-id="cd15f-181">If you don't want to query all the entities in a partition, you can specify a range by combining the partition key filter with a row key filter.</span></span> <span data-ttu-id="cd15f-182">En este caso, se usan dos filtros para obtener todas las entidades de la partición "Smith" en las que la clave de fila (nombre de pila) empieza por una letra anterior a "M" en el alfabeto.</span><span class="sxs-lookup"><span data-stu-id="cd15f-182">Here, you use two filters to get all entities in the "Smith" partition where the row key (first name) starts with a letter earlier than "M" in the alphabet.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L91-L100)]

<span data-ttu-id="cd15f-183">Ahora imprime los resultados:</span><span class="sxs-lookup"><span data-stu-id="cd15f-183">You now print the results:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L102-L103)]

### <a name="retrieve-a-single-entity"></a><span data-ttu-id="cd15f-184">Recuperación de una sola entidad</span><span class="sxs-lookup"><span data-stu-id="cd15f-184">Retrieve a single entity</span></span>

<span data-ttu-id="cd15f-185">Puede escribir una consulta para recuperar una única entidad específica.</span><span class="sxs-lookup"><span data-stu-id="cd15f-185">You can write a query to retrieve a single, specific entity.</span></span> <span data-ttu-id="cd15f-186">Aquí, se usa `TableOperation` para especificar el cliente "Ben Smith".</span><span class="sxs-lookup"><span data-stu-id="cd15f-186">Here, you use a `TableOperation` to specify the customer "Ben Smith".</span></span> <span data-ttu-id="cd15f-187">En lugar de una colección, se obtiene una `Customer`.</span><span class="sxs-lookup"><span data-stu-id="cd15f-187">Instead of a collection, you get back a `Customer`.</span></span> <span data-ttu-id="cd15f-188">La forma más rápida de recuperar una sola entidad de la Table service es especificar la clave de partición y la clave de fila en una consulta.</span><span class="sxs-lookup"><span data-stu-id="cd15f-188">Specifying both the partition key and the row key in a query is the fastest way to retrieve a single entity from the Table service.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L109-L111)]

<span data-ttu-id="cd15f-189">Ahora imprime los resultados:</span><span class="sxs-lookup"><span data-stu-id="cd15f-189">You now print the results:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L113-L115)]

### <a name="replace-an-entity"></a><span data-ttu-id="cd15f-190">Reemplazar una entidad</span><span class="sxs-lookup"><span data-stu-id="cd15f-190">Replace an entity</span></span>

<span data-ttu-id="cd15f-191">Para actualizar una entidad, recupere el Table Service, modifique el objeto entidad y, a continuación, guarde los cambios de nuevo en el Table Service `Replace` mediante una operación.</span><span class="sxs-lookup"><span data-stu-id="cd15f-191">To update an entity, retrieve it from the Table service, modify the entity object, and then save the changes back to the Table service using a `Replace` operation.</span></span> <span data-ttu-id="cd15f-192">Esto hace que la entidad se reemplace por completo en el servidor, a menos que la entidad del servidor haya cambiado desde que se recuperó, en cuyo caso se produce un error en la operación.</span><span class="sxs-lookup"><span data-stu-id="cd15f-192">This causes the entity to be fully replaced on the server, unless the entity on the server has changed since it was retrieved, in which case the operation fails.</span></span> <span data-ttu-id="cd15f-193">Este error se debe a evitar que la aplicación sobrescriba los cambios de otros orígenes accidentalmente.</span><span class="sxs-lookup"><span data-stu-id="cd15f-193">This failure is to prevent your application from inadvertently overwriting changes from other sources.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L121-L128)]

### <a name="insert-or-replace-an-entity"></a><span data-ttu-id="cd15f-194">Inserción o reemplazo de una entidad</span><span class="sxs-lookup"><span data-stu-id="cd15f-194">Insert-or-replace an entity</span></span>

<span data-ttu-id="cd15f-195">A veces, no se sabe si existe una entidad en la tabla.</span><span class="sxs-lookup"><span data-stu-id="cd15f-195">Sometimes, you don't know whether an entity exists in the table.</span></span> <span data-ttu-id="cd15f-196">Y, si es así, los valores actuales almacenados en él ya no son necesarios.</span><span class="sxs-lookup"><span data-stu-id="cd15f-196">And if it does, the current values stored in it are no longer needed.</span></span> <span data-ttu-id="cd15f-197">Puede usar `InsertOrReplace` para crear la entidad o reemplazarla si existe, independientemente de su estado.</span><span class="sxs-lookup"><span data-stu-id="cd15f-197">You can use `InsertOrReplace` to create the entity, or replace it if it exists, regardless of its state.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L134-L141)]

### <a name="query-a-subset-of-entity-properties"></a><span data-ttu-id="cd15f-198">Consultar un subconjunto de propiedades de entidad</span><span class="sxs-lookup"><span data-stu-id="cd15f-198">Query a subset of entity properties</span></span>

<span data-ttu-id="cd15f-199">Una consulta de tabla puede recuperar solo algunas propiedades de una entidad en lugar de todas ellas.</span><span class="sxs-lookup"><span data-stu-id="cd15f-199">A table query can retrieve just a few properties from an entity instead of all of them.</span></span> <span data-ttu-id="cd15f-200">Esta técnica, denominada proyección, puede mejorar el rendimiento de las consultas, especialmente en el caso de entidades de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="cd15f-200">This technique, called projection, can improve query performance, especially for large entities.</span></span> <span data-ttu-id="cd15f-201">En este caso, solo se devuelven `EntityResolver`direcciones de correo electrónico mediante `DynamicTableEntity` y.</span><span class="sxs-lookup"><span data-stu-id="cd15f-201">Here, you return only email addresses using `DynamicTableEntity` and `EntityResolver`.</span></span> <span data-ttu-id="cd15f-202">Tenga en cuenta que no se admite la proyección en el emulador de almacenamiento local, por lo que este código solo se ejecuta cuando se usa una cuenta en el Table service.</span><span class="sxs-lookup"><span data-stu-id="cd15f-202">Note that projection is not supported on the local storage emulator, so this code runs only when you're using an account on the Table service.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L147-L158)]

### <a name="retrieve-entities-in-pages-asynchronously"></a><span data-ttu-id="cd15f-203">Recuperar entidades en páginas de forma asincrónica</span><span class="sxs-lookup"><span data-stu-id="cd15f-203">Retrieve entities in pages asynchronously</span></span>

<span data-ttu-id="cd15f-204">Si está leyendo un gran número de entidades y desea procesarlas a medida que se recuperan en lugar de esperar a que se devuelvan todas, puede usar una consulta segmentada.</span><span class="sxs-lookup"><span data-stu-id="cd15f-204">If you are reading a large number of entities, and you want to process them as they are retrieved rather than waiting for them all to return, you can use a segmented query.</span></span> <span data-ttu-id="cd15f-205">Aquí se devuelven los resultados en páginas mediante un flujo de trabajo asincrónico para que la ejecución no se bloquee mientras se espera a que se devuelva un conjunto grande de resultados.</span><span class="sxs-lookup"><span data-stu-id="cd15f-205">Here, you return results in pages by using an async workflow so that execution is not blocked while you're waiting for a large set of results to return.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L163-L178)]

<span data-ttu-id="cd15f-206">Ahora ejecuta este cálculo de forma sincrónica:</span><span class="sxs-lookup"><span data-stu-id="cd15f-206">You now execute this computation synchronously:</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L180-L180)]

### <a name="delete-an-entity"></a><span data-ttu-id="cd15f-207">Eliminar una entidad</span><span class="sxs-lookup"><span data-stu-id="cd15f-207">Delete an entity</span></span>

<span data-ttu-id="cd15f-208">Puede eliminar una entidad después de recuperarla.</span><span class="sxs-lookup"><span data-stu-id="cd15f-208">You can delete an entity after you have retrieved it.</span></span> <span data-ttu-id="cd15f-209">Al igual que con la actualización de una entidad, se produce un error si la entidad ha cambiado desde que se recuperó.</span><span class="sxs-lookup"><span data-stu-id="cd15f-209">As with updating an entity, this fails if the entity has changed since you retrieved it.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L186-L187)]

### <a name="delete-a-table"></a><span data-ttu-id="cd15f-210">Eliminar una tabla</span><span class="sxs-lookup"><span data-stu-id="cd15f-210">Delete a table</span></span>

<span data-ttu-id="cd15f-211">Puede eliminar una tabla de una cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="cd15f-211">You can delete a table from a storage account.</span></span> <span data-ttu-id="cd15f-212">Una tabla que se ha eliminado no podrá volver a crearse durante un período de tiempo después de la eliminación.</span><span class="sxs-lookup"><span data-stu-id="cd15f-212">A table that has been deleted will be unavailable to be re-created for a period of time following the deletion.</span></span>

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L193-L193)]

## <a name="next-steps"></a><span data-ttu-id="cd15f-213">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="cd15f-213">Next steps</span></span>

<span data-ttu-id="cd15f-214">Ahora que ha aprendido los aspectos básicos del almacenamiento de tablas, siga estos vínculos para obtener más información acerca de las tareas de almacenamiento más complejas y el Table API de Azure Cosmos DB.</span><span class="sxs-lookup"><span data-stu-id="cd15f-214">Now that you've learned the basics of Table storage, follow these links to learn about more complex storage tasks and the Azure Cosmos DB Table API.</span></span>

- [<span data-ttu-id="cd15f-215">Introducción a Azure Cosmos DB Table API</span><span class="sxs-lookup"><span data-stu-id="cd15f-215">Introduction to Azure Cosmos DB Table API</span></span>](https://docs.microsoft.com/azure/cosmos-db/table-introduction)
- [<span data-ttu-id="cd15f-216">Referencia de la biblioteca de cliente de almacenamiento para .NET</span><span class="sxs-lookup"><span data-stu-id="cd15f-216">Storage Client Library for .NET reference</span></span>](https://docs.microsoft.com/dotnet/api/overview/azure/storage?view=azure-dotnet)
- [<span data-ttu-id="cd15f-217">Azure Storage proveedor de tipos</span><span class="sxs-lookup"><span data-stu-id="cd15f-217">Azure Storage Type Provider</span></span>](https://fsprojects.github.io/AzureStorageTypeProvider/)
- [<span data-ttu-id="cd15f-218">Blog del equipo de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="cd15f-218">Azure Storage Team Blog</span></span>](https://blogs.msdn.com/b/windowsazurestorage/)
- [<span data-ttu-id="cd15f-219">Configurar cadenas de conexión</span><span class="sxs-lookup"><span data-stu-id="cd15f-219">Configuring Connection Strings</span></span>](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="cd15f-220">Introducción con Azure Table Storage en .NET</span><span class="sxs-lookup"><span data-stu-id="cd15f-220">Getting Started with Azure Table Storage in .NET</span></span>](https://azure.microsoft.com/resources/samples/storage-table-dotnet-getting-started/)
