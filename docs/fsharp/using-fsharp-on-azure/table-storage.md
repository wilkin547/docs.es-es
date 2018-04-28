---
title: 'Introducción al almacenamiento de tabla de Azure con F #'
description: Almacenar datos estructurados en la nube con el almacenamiento de tabla de Azure o base de datos de Azure Cosmos.
author: sylvanc
ms.author: phcart
ms.date: 03/26/2018
ms.topic: conceptual
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 50721ca44bbae5c52984b08a30bc87507fbf063d
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="get-started-with-azure-table-storage-and-the-azure-cosmos-db-table-api-using-f"></a><span data-ttu-id="62af6-103">Introducción a almacenamiento de tabla de Azure y la API de tabla de base de datos de Azure Cosmos con F #</span><span class="sxs-lookup"><span data-stu-id="62af6-103">Get started with Azure Table storage and the Azure Cosmos DB Table API using F#</span></span> # 

<span data-ttu-id="62af6-104">El almacenamiento de tabla es un servicio que almacena datos estructurados de NoSQL en la nube.</span><span class="sxs-lookup"><span data-stu-id="62af6-104">Azure Table storage is a service that stores structured NoSQL data in the cloud.</span></span> <span data-ttu-id="62af6-105">Almacenamiento de tabla es un almacén de clave/atributo con un diseño schemaless.</span><span class="sxs-lookup"><span data-stu-id="62af6-105">Table storage is a key/attribute store with a schemaless design.</span></span> <span data-ttu-id="62af6-106">Dado que el almacenamiento de tabla es schemaless, es fácil adaptar los datos como las necesidades de su evolucionar de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="62af6-106">Because Table storage is schemaless, it's easy to adapt your data as the needs of your application evolve.</span></span> <span data-ttu-id="62af6-107">Acceso a los datos es rápido y rentable para todos los tipos de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="62af6-107">Access to data is fast and cost-effective for all kinds of applications.</span></span> <span data-ttu-id="62af6-108">Almacenamiento de tabla suele ser significativamente menor costo que SQL tradicional para similar volúmenes de datos.</span><span class="sxs-lookup"><span data-stu-id="62af6-108">Table storage is typically significantly lower in cost than traditional SQL for similar volumes of data.</span></span>

<span data-ttu-id="62af6-109">Puede usar el almacenamiento de tabla para almacenar conjuntos de datos flexible, como datos de usuario para aplicaciones web, libretas de direcciones, información del dispositivo y cualquier otro tipo de metadatos que necesite el servicio.</span><span class="sxs-lookup"><span data-stu-id="62af6-109">You can use Table storage to store flexible datasets, such as user data for web applications, address books, device information, and any other type of metadata that your service requires.</span></span> <span data-ttu-id="62af6-110">Puede almacenar cualquier número de entidades en una tabla y una cuenta de almacenamiento puede contener cualquier número de tablas, hasta el límite de capacidad de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="62af6-110">You can store any number of entities in a table, and a storage account may contain any number of tables, up to the capacity limit of the storage account.</span></span>

<span data-ttu-id="62af6-111">Base de datos de Azure Cosmos proporciona la API de tabla para las aplicaciones escritas para el almacenamiento de tabla de Azure y que requieren capacidades premium como:</span><span class="sxs-lookup"><span data-stu-id="62af6-111">Azure Cosmos DB provides the Table API for applications that are written for Azure Table storage and that require premium capabilities such as:</span></span>

- <span data-ttu-id="62af6-112">Distribución global llave en mano.</span><span class="sxs-lookup"><span data-stu-id="62af6-112">Turnkey global distribution.</span></span>
- <span data-ttu-id="62af6-113">Rendimiento dedicado en todo el mundo.</span><span class="sxs-lookup"><span data-stu-id="62af6-113">Dedicated throughput worldwide.</span></span>
- <span data-ttu-id="62af6-114">Latencias de milisegundos de un solo dígito en el percentil 99.</span><span class="sxs-lookup"><span data-stu-id="62af6-114">Single-digit millisecond latencies at the 99th percentile.</span></span>
- <span data-ttu-id="62af6-115">Garantiza la alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="62af6-115">Guaranteed high availability.</span></span>
- <span data-ttu-id="62af6-116">Secundario la indexación automática.</span><span class="sxs-lookup"><span data-stu-id="62af6-116">Automatic secondary indexing.</span></span>

<span data-ttu-id="62af6-117">Las aplicaciones escritas para el almacenamiento de tabla de Azure pueden migrar a base de datos de Azure Cosmos mediante la API de tabla sin realizar ningún cambio en el código y aprovechar las capacidades premium.</span><span class="sxs-lookup"><span data-stu-id="62af6-117">Applications written for Azure Table storage can migrate to Azure Cosmos DB by using the Table API with no code changes and take advantage of premium capabilities.</span></span> <span data-ttu-id="62af6-118">La API de tabla tiene el SDK de cliente disponible para. NET, Java, Python y Node.js.</span><span class="sxs-lookup"><span data-stu-id="62af6-118">The Table API has client SDKs available for .NET, Java, Python, and Node.js.</span></span>

<span data-ttu-id="62af6-119">Para obtener más información, consulte [Introducción a la API de tabla de base de datos de Azure Cosmos](https://docs.microsoft.com/azure/cosmos-db/table-introduction).</span><span class="sxs-lookup"><span data-stu-id="62af6-119">For more information, see [Introduction to Azure Cosmos DB Table API](https://docs.microsoft.com/azure/cosmos-db/table-introduction).</span></span>

## <a name="about-this-tutorial"></a><span data-ttu-id="62af6-120">Acerca de este tutorial</span><span class="sxs-lookup"><span data-stu-id="62af6-120">About this tutorial</span></span>

<span data-ttu-id="62af6-121">Este tutorial muestra cómo escribir código de F # para realizar algunas tareas comunes utilizando la API de tabla de Azure Cosmos DB, incluida la creación y eliminar una tabla e Insertar, actualizar, eliminar y consultar datos de la tabla o de almacenamiento de tabla de Azure.</span><span class="sxs-lookup"><span data-stu-id="62af6-121">This tutorial shows how to write F# code to do some common tasks using Azure Table storage or the Azure Cosmos DB Table API, including creating and deleting a table and inserting, updating, deleting, and querying table data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="62af6-122">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="62af6-122">Prerequisites</span></span>

<span data-ttu-id="62af6-123">Para utilizar esta guía, primero debe [crear una cuenta de almacenamiento de Azure](/azure/storage/storage-create-storage-account) o [cuenta de base de datos de Azure Cosmos](https://azure.microsoft.com/try/cosmosdb/).</span><span class="sxs-lookup"><span data-stu-id="62af6-123">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account) or [Azure Cosmos DB account](https://azure.microsoft.com/try/cosmosdb/).</span></span>


## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="62af6-124">Crear un Script de F # y el inicio de F # Interactive</span><span class="sxs-lookup"><span data-stu-id="62af6-124">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="62af6-125">Los ejemplos de este artículo pueden usarse en una aplicación de F # o un script de F #.</span><span class="sxs-lookup"><span data-stu-id="62af6-125">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="62af6-126">Para crear un script de F #, cree un archivo con el `.fsx` extensión, por ejemplo `tables.fsx`, en el entorno de desarrollo de F #.</span><span class="sxs-lookup"><span data-stu-id="62af6-126">To create an F# script, create a file with the `.fsx` extension, for example `tables.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="62af6-127">A continuación, use un [el Administrador de paquetes](package-management.md) como [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) para instalar el `WindowsAzure.Storage` paquete y referencia `WindowsAzure.Storage.dll` en el script mediante un `#r`directiva.</span><span class="sxs-lookup"><span data-stu-id="62af6-127">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span> <span data-ttu-id="62af6-128">Hacerlo nuevo para `Microsoft.WindowsAzure.ConfigurationManager` con el fin de obtener el espacio de nombres Microsoft.Azure.</span><span class="sxs-lookup"><span data-stu-id="62af6-128">Do it again for `Microsoft.WindowsAzure.ConfigurationManager` in order to get the Microsoft.Azure namespace.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="62af6-129">Agregue las declaraciones de espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="62af6-129">Add namespace declarations</span></span>

<span data-ttu-id="62af6-130">Agregue el siguiente `open` instrucciones a la parte superior de la `tables.fsx` archivo:</span><span class="sxs-lookup"><span data-stu-id="62af6-130">Add the following `open` statements to the top of the `tables.fsx` file:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L1-L5)]

### <a name="get-your-azure-storage-connection-string"></a><span data-ttu-id="62af6-131">Obtener la cadena de conexión de almacenamiento de Azure</span><span class="sxs-lookup"><span data-stu-id="62af6-131">Get your Azure Storage connection string</span></span>

<span data-ttu-id="62af6-132">Si se está conectando al servicio de la tabla de almacenamiento de Azure, necesitará la cadena de conexión para este tutorial.</span><span class="sxs-lookup"><span data-stu-id="62af6-132">If you're connecting to Azure Storage Table service, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="62af6-133">Puede copiar la cadena de conexión desde el portal de Azure.</span><span class="sxs-lookup"><span data-stu-id="62af6-133">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="62af6-134">Para obtener más información acerca de las cadenas de conexión, vea [configurar cadenas de conexión de almacenamiento](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="62af6-134">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

### <a name="get-your-azure-cosmos-db-connection-string"></a><span data-ttu-id="62af6-135">Obtener la cadena de conexión de base de datos de Azure Cosmos</span><span class="sxs-lookup"><span data-stu-id="62af6-135">Get your Azure Cosmos DB connection string</span></span>

<span data-ttu-id="62af6-136">Si se está conectando a la base de datos de Azure Cosmos, necesitará la cadena de conexión para este tutorial.</span><span class="sxs-lookup"><span data-stu-id="62af6-136">If you're connecting to Azure Cosmos DB, you'll need your connection string for this tutorial.</span></span> <span data-ttu-id="62af6-137">Puede copiar la cadena de conexión desde el portal de Azure.</span><span class="sxs-lookup"><span data-stu-id="62af6-137">You can copy your connection string from the Azure portal.</span></span> <span data-ttu-id="62af6-138">En el portal de Azure, en la cuenta de base de datos de Cosmos, vaya a **configuración** > **cadena de conexión**y haga clic en el **copia** botón para copiar la conexión principal Cadena.</span><span class="sxs-lookup"><span data-stu-id="62af6-138">In the Azure portal, in your Cosmos DB account, go to **Settings** > **Connection String**, and click the **Copy** button to copy your Primary Connection String.</span></span> 

<span data-ttu-id="62af6-139">En el tutorial, escriba la cadena de conexión en el script, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="62af6-139">For the tutorial, enter your connection string in your script, like the following example:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L11-L11)]

<span data-ttu-id="62af6-140">Sin embargo, esto es **no recomienda** proyectos de una manera real.</span><span class="sxs-lookup"><span data-stu-id="62af6-140">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="62af6-141">La clave de cuenta de almacenamiento es similar a la contraseña raíz para la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="62af6-141">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="62af6-142">Tenga siempre cuidado proteger la clave de cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="62af6-142">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="62af6-143">Evitar la distribución a otros usuarios, codificar de forma rígida, o guardarlo en un archivo de texto sin formato sea accesible a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="62af6-143">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="62af6-144">Puede volver a generar la clave mediante el Portal de Azure si cree que se han comprometido.</span><span class="sxs-lookup"><span data-stu-id="62af6-144">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="62af6-145">Las aplicaciones de una manera real, la mejor manera de mantener la cadena de conexión de almacenamiento está en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="62af6-145">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="62af6-146">Para capturar la cadena de conexión de un archivo de configuración, puede hacer esto:</span><span class="sxs-lookup"><span data-stu-id="62af6-146">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L13-L15)]

<span data-ttu-id="62af6-147">Con el Administrador de configuración de Azure es opcional.</span><span class="sxs-lookup"><span data-stu-id="62af6-147">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="62af6-148">También puede utilizar una API como .NET Framework `ConfigurationManager` tipo.</span><span class="sxs-lookup"><span data-stu-id="62af6-148">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="62af6-149">Analizar la cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="62af6-149">Parse the connection string</span></span>

<span data-ttu-id="62af6-150">Para analizar la cadena de conexión, use:</span><span class="sxs-lookup"><span data-stu-id="62af6-150">To parse the connection string, use:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L21-L22)]

<span data-ttu-id="62af6-151">Esto devuelve un `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="62af6-151">This returns a `CloudStorageAccount`.</span></span>

### <a name="create-the-table-service-client"></a><span data-ttu-id="62af6-152">Crear al cliente del servicio tabla</span><span class="sxs-lookup"><span data-stu-id="62af6-152">Create the Table service client</span></span>

<span data-ttu-id="62af6-153">La `CloudTableClient` clase le permite recuperar tablas y entidades en el almacenamiento de tabla.</span><span class="sxs-lookup"><span data-stu-id="62af6-153">The `CloudTableClient` class enables you to retrieve tables and entities in Table storage.</span></span> <span data-ttu-id="62af6-154">Aquí es una manera de crear al cliente del servicio:</span><span class="sxs-lookup"><span data-stu-id="62af6-154">Here's one way to create the service client:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L28-L29)]

<span data-ttu-id="62af6-155">Ahora está listo para escribir código que lee datos de y escribe datos en el almacenamiento de tabla.</span><span class="sxs-lookup"><span data-stu-id="62af6-155">Now you are ready to write code that reads data from and writes data to Table storage.</span></span>

### <a name="create-a-table"></a><span data-ttu-id="62af6-156">Creación de una tabla</span><span class="sxs-lookup"><span data-stu-id="62af6-156">Create a table</span></span>

<span data-ttu-id="62af6-157">En este ejemplo se muestra cómo crear una tabla si aún no existe:</span><span class="sxs-lookup"><span data-stu-id="62af6-157">This example shows how to create a table if it does not already exist:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L35-L39)]

### <a name="add-an-entity-to-a-table"></a><span data-ttu-id="62af6-158">Agregar una entidad a una tabla</span><span class="sxs-lookup"><span data-stu-id="62af6-158">Add an entity to a table</span></span>

<span data-ttu-id="62af6-159">Una entidad debe tener un tipo que hereda de `TableEntity`.</span><span class="sxs-lookup"><span data-stu-id="62af6-159">An entity has to have a type that inherits from `TableEntity`.</span></span> <span data-ttu-id="62af6-160">Puede extender `TableEntity` en como desee, pero su tipo *debe* tiene un constructor sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="62af6-160">You can extend `TableEntity` in any way you like, but your type *must* have a parameter-less constructor.</span></span> <span data-ttu-id="62af6-161">Solo las propiedades que tienen ambos `get` y `set` se almacenan en la tabla de Azure.</span><span class="sxs-lookup"><span data-stu-id="62af6-161">Only properties that have both `get` and `set` are stored in your Azure Table.</span></span>

<span data-ttu-id="62af6-162">Partición de una entidad y la clave de fila identifican la entidad en la tabla.</span><span class="sxs-lookup"><span data-stu-id="62af6-162">An entity's partition and row key uniquely identify the entity in the table.</span></span> <span data-ttu-id="62af6-163">Entidades con la misma clave de partición se pueden consultar más rápido que aquellos con las claves de partición diferente, pero el uso de las claves de partición diversos permite para una mayor escalabilidad de operaciones en paralelo.</span><span class="sxs-lookup"><span data-stu-id="62af6-163">Entities with the same partition key can be queried faster than those with different partition keys, but using diverse partition keys allows for greater scalability of parallel operations.</span></span>

<span data-ttu-id="62af6-164">Este es un ejemplo de un `Customer` que usa el `lastName` como la clave de partición y el `firstName` como la clave de fila.</span><span class="sxs-lookup"><span data-stu-id="62af6-164">Here's an example of a `Customer` that uses the `lastName` as the partition key and the `firstName` as the row key.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L45-L52)]

<span data-ttu-id="62af6-165">Ahora, agregue `Customer` a la tabla.</span><span class="sxs-lookup"><span data-stu-id="62af6-165">Now add `Customer` to the table.</span></span> <span data-ttu-id="62af6-166">Para ello, cree un `TableOperation` que se ejecuta en la tabla.</span><span class="sxs-lookup"><span data-stu-id="62af6-166">To do so, create a `TableOperation` that executes on the table.</span></span> <span data-ttu-id="62af6-167">En este caso, cree un `Insert` operación.</span><span class="sxs-lookup"><span data-stu-id="62af6-167">In this case, you create an `Insert` operation.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L54-L55)]

### <a name="insert-a-batch-of-entities"></a><span data-ttu-id="62af6-168">Insertar un lote de entidades</span><span class="sxs-lookup"><span data-stu-id="62af6-168">Insert a batch of entities</span></span>

<span data-ttu-id="62af6-169">Puede insertar un lote de entidades en una tabla con una sola operación de escritura.</span><span class="sxs-lookup"><span data-stu-id="62af6-169">You can insert a batch of entities into a table using a single write operation.</span></span> <span data-ttu-id="62af6-170">Operaciones por lotes permiten combinar las operaciones en una sola ejecución, pero tienen algunas restricciones:</span><span class="sxs-lookup"><span data-stu-id="62af6-170">Batch operations allow you to combine operations into a single execution, but they have some restrictions:</span></span>

- <span data-ttu-id="62af6-171">Puede realizar actualizaciones, elimina y se inserta en la misma operación por lotes.</span><span class="sxs-lookup"><span data-stu-id="62af6-171">You can perform updates, deletes, and inserts in the same batch operation.</span></span>
- <span data-ttu-id="62af6-172">Una operación por lotes puede incluir hasta 100 entidades.</span><span class="sxs-lookup"><span data-stu-id="62af6-172">A batch operation can include up to 100 entities.</span></span>
- <span data-ttu-id="62af6-173">Todas las entidades de una operación por lotes deben tener la misma clave de partición.</span><span class="sxs-lookup"><span data-stu-id="62af6-173">All entities in a batch operation must have the same partition key.</span></span>
- <span data-ttu-id="62af6-174">Aunque es posible realizar una consulta en una operación por lotes, debe ser la única operación en el lote.</span><span class="sxs-lookup"><span data-stu-id="62af6-174">While it is possible to perform a query in a batch operation, it must be the only operation in the batch.</span></span>

<span data-ttu-id="62af6-175">Este es un código que combina dos inserciones en una operación por lotes:</span><span class="sxs-lookup"><span data-stu-id="62af6-175">Here's some code that combines two inserts into a batch operation:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L62-L71)]

### <a name="retrieve-all-entities-in-a-partition"></a><span data-ttu-id="62af6-176">Recuperar todas las entidades de una partición</span><span class="sxs-lookup"><span data-stu-id="62af6-176">Retrieve all entities in a partition</span></span>

<span data-ttu-id="62af6-177">Para consultar una tabla para todas las entidades de una partición, use un `TableQuery` objeto.</span><span class="sxs-lookup"><span data-stu-id="62af6-177">To query a table for all entities in a partition, use a `TableQuery` object.</span></span> <span data-ttu-id="62af6-178">En este caso, se filtran las entidades donde "Smith" es la clave de partición.</span><span class="sxs-lookup"><span data-stu-id="62af6-178">Here, you filter for entities where "Smith" is the partition key.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L77-L82)]

<span data-ttu-id="62af6-179">Ahora imprimir los resultados:</span><span class="sxs-lookup"><span data-stu-id="62af6-179">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L84-L85)]


### <a name="retrieve-a-range-of-entities-in-a-partition"></a><span data-ttu-id="62af6-180">Recuperar un intervalo de entidades en una partición</span><span class="sxs-lookup"><span data-stu-id="62af6-180">Retrieve a range of entities in a partition</span></span>

<span data-ttu-id="62af6-181">Si no desea consultar todas las entidades en una partición, puede especificar un intervalo combinando el filtro de clave de partición con un filtro de clave de fila.</span><span class="sxs-lookup"><span data-stu-id="62af6-181">If you don't want to query all the entities in a partition, you can specify a range by combining the partition key filter with a row key filter.</span></span> <span data-ttu-id="62af6-182">Aquí, se usa dos filtros para obtener todas las entidades de la partición "Smith" en la clave de fila (nombre) comienza con una letra anterior a "M" en el alfabeto.</span><span class="sxs-lookup"><span data-stu-id="62af6-182">Here, you use two filters to get all entities in the "Smith" partition where the row key (first name) starts with a letter earlier than "M" in the alphabet.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L91-L100)]

<span data-ttu-id="62af6-183">Ahora imprimir los resultados:</span><span class="sxs-lookup"><span data-stu-id="62af6-183">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L102-L103)]

### <a name="retrieve-a-single-entity"></a><span data-ttu-id="62af6-184">Recuperar una sola entidad</span><span class="sxs-lookup"><span data-stu-id="62af6-184">Retrieve a single entity</span></span>

<span data-ttu-id="62af6-185">Puede escribir una consulta para recuperar una entidad única, específica.</span><span class="sxs-lookup"><span data-stu-id="62af6-185">You can write a query to retrieve a single, specific entity.</span></span> <span data-ttu-id="62af6-186">A continuación, use un `TableOperation` para especificar el cliente "Ben Smith".</span><span class="sxs-lookup"><span data-stu-id="62af6-186">Here, you use a `TableOperation` to specify the customer "Ben Smith".</span></span> <span data-ttu-id="62af6-187">En lugar de una colección, se recibe un `Customer`.</span><span class="sxs-lookup"><span data-stu-id="62af6-187">Instead of a collection, you get back a `Customer`.</span></span> <span data-ttu-id="62af6-188">Especificar la clave de partición y la clave de fila en una consulta es la manera más rápida de recuperar una entidad única desde el servicio de la tabla.</span><span class="sxs-lookup"><span data-stu-id="62af6-188">Specifying both the partition key and the row key in a query is the fastest way to retrieve a single entity from the Table service.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L109-L111)]

<span data-ttu-id="62af6-189">Ahora imprimir los resultados:</span><span class="sxs-lookup"><span data-stu-id="62af6-189">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L113-L115)]


### <a name="replace-an-entity"></a><span data-ttu-id="62af6-190">Reemplazar una entidad</span><span class="sxs-lookup"><span data-stu-id="62af6-190">Replace an entity</span></span>

<span data-ttu-id="62af6-191">Para actualizar una entidad, recuperar desde el servicio tabla, modificar el objeto de entidad y, a continuación, guarde los cambios a la tabla de servicio mediante un `Replace` operación.</span><span class="sxs-lookup"><span data-stu-id="62af6-191">To update an entity, retrieve it from the Table service, modify the entity object, and then save the changes back to the Table service using a `Replace` operation.</span></span> <span data-ttu-id="62af6-192">Esto hace que la entidad que se va a reemplazar completamente en el servidor, a menos que la entidad en el servidor ha cambiado desde que se recuperó, en cuyo caso se produce un error en la operación.</span><span class="sxs-lookup"><span data-stu-id="62af6-192">This causes the entity to be fully replaced on the server, unless the entity on the server has changed since it was retrieved, in which case the operation fails.</span></span> <span data-ttu-id="62af6-193">Este error es evitar que la aplicación se ha sobrescrito accidentalmente cambios de otros orígenes.</span><span class="sxs-lookup"><span data-stu-id="62af6-193">This failure is to prevent your application from inadvertently overwriting changes from other sources.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L121-L128)]

### <a name="insert-or-replace-an-entity"></a><span data-ttu-id="62af6-194">Insertar o reemplazar una entidad</span><span class="sxs-lookup"><span data-stu-id="62af6-194">Insert-or-replace an entity</span></span>

<span data-ttu-id="62af6-195">A veces, no sabe si existe una entidad en la tabla.</span><span class="sxs-lookup"><span data-stu-id="62af6-195">Sometimes, you don't know whether an entity exists in the table.</span></span> <span data-ttu-id="62af6-196">Y si lo hace, ya no son necesarios los valores actuales almacenados en ella.</span><span class="sxs-lookup"><span data-stu-id="62af6-196">And if it does, the current values stored in it are no longer needed.</span></span> <span data-ttu-id="62af6-197">Puede usar `InsertOrReplace` para crear la entidad o cámbielo si existe, independientemente de su estado.</span><span class="sxs-lookup"><span data-stu-id="62af6-197">You can use `InsertOrReplace` to create the entity, or replace it if it exists, regardless of its state.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L134-L141)]

### <a name="query-a-subset-of-entity-properties"></a><span data-ttu-id="62af6-198">Consultar un subconjunto de propiedades de entidad</span><span class="sxs-lookup"><span data-stu-id="62af6-198">Query a subset of entity properties</span></span>

<span data-ttu-id="62af6-199">Una consulta de tabla puede recuperar solo unas pocas propiedades de una entidad en lugar de todos ellos.</span><span class="sxs-lookup"><span data-stu-id="62af6-199">A table query can retrieve just a few properties from an entity instead of all of them.</span></span> <span data-ttu-id="62af6-200">Esta técnica, denominada proyección, puede mejorar el rendimiento, especialmente para entidades de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="62af6-200">This technique, called projection, can improve query performance, especially for large entities.</span></span> <span data-ttu-id="62af6-201">En este caso, se devuelven solo correo electrónico aborda el uso de `DynamicTableEntity` y `EntityResolver`.</span><span class="sxs-lookup"><span data-stu-id="62af6-201">Here, you return only email addresses using `DynamicTableEntity` and `EntityResolver`.</span></span> <span data-ttu-id="62af6-202">Tenga en cuenta que no se admite proyección en el emulador de almacenamiento local, por lo que este código se ejecuta sólo cuando se usa una cuenta en el servicio de la tabla.</span><span class="sxs-lookup"><span data-stu-id="62af6-202">Note that projection is not supported on the local storage emulator, so this code runs only when you're using an account on the Table service.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L147-L158)]

### <a name="retrieve-entities-in-pages-asynchronously"></a><span data-ttu-id="62af6-203">Recuperar entidades en las páginas de forma asincrónica</span><span class="sxs-lookup"><span data-stu-id="62af6-203">Retrieve entities in pages asynchronously</span></span>

<span data-ttu-id="62af6-204">Si está leyendo un gran número de entidades y desea procesarlas a medida que se recuperan en lugar de esperar a todos los que devuelven, puede utilizar una consulta segmentada.</span><span class="sxs-lookup"><span data-stu-id="62af6-204">If you are reading a large number of entities, and you want to process them as they are retrieved rather than waiting for them all to return, you can use a segmented query.</span></span> <span data-ttu-id="62af6-205">En este caso, se devuelven resultados en páginas mediante el uso de un flujo de trabajo asincrónico para que no la ejecución se bloquea mientras espera para un gran conjunto de resultados para devolver.</span><span class="sxs-lookup"><span data-stu-id="62af6-205">Here, you return results in pages by using an async workflow so that execution is not blocked while you're waiting for a large set of results to return.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L163-L178)]

<span data-ttu-id="62af6-206">Ahora ejecute sincrónicamente este cálculo:</span><span class="sxs-lookup"><span data-stu-id="62af6-206">You now execute this computation synchronously:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L180-L180)]

### <a name="delete-an-entity"></a><span data-ttu-id="62af6-207">Eliminar una entidad</span><span class="sxs-lookup"><span data-stu-id="62af6-207">Delete an entity</span></span>

<span data-ttu-id="62af6-208">Puede eliminar una entidad después de que se han recuperado.</span><span class="sxs-lookup"><span data-stu-id="62af6-208">You can delete an entity after you have retrieved it.</span></span> <span data-ttu-id="62af6-209">Al igual que con la actualización de una entidad, esto se produce un error si la entidad ha cambiado desde que recuperó.</span><span class="sxs-lookup"><span data-stu-id="62af6-209">As with updating an entity, this fails if the entity has changed since you retrieved it.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L186-L187)]

### <a name="delete-a-table"></a><span data-ttu-id="62af6-210">Eliminar una tabla</span><span class="sxs-lookup"><span data-stu-id="62af6-210">Delete a table</span></span>

<span data-ttu-id="62af6-211">Puede eliminar una tabla de una cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="62af6-211">You can delete a table from a storage account.</span></span> <span data-ttu-id="62af6-212">Una tabla que se ha eliminado no estará disponible para volver a crearse durante un período de tiempo tras la eliminación.</span><span class="sxs-lookup"><span data-stu-id="62af6-212">A table that has been deleted will be unavailable to be re-created for a period of time following the deletion.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L193-L193)]

## <a name="next-steps"></a><span data-ttu-id="62af6-213">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="62af6-213">Next steps</span></span>

<span data-ttu-id="62af6-214">Ahora que conoce los fundamentos del almacenamiento de tabla, siga estos vínculos para obtener información acerca de las tareas más complejas de almacenamiento y la API de tabla de base de datos de Azure Cosmos.</span><span class="sxs-lookup"><span data-stu-id="62af6-214">Now that you've learned the basics of Table storage, follow these links to learn about more complex storage tasks and the Azure Cosmos DB Table API.</span></span>

- [<span data-ttu-id="62af6-215">Introducción a la API de la tabla de base de datos de Azure Cosmos</span><span class="sxs-lookup"><span data-stu-id="62af6-215">Introduction to Azure Cosmos DB Table API</span></span>](https://docs.microsoft.com/azure/cosmos-db/table-introduction)
- [<span data-ttu-id="62af6-216">Biblioteca de cliente de almacenamiento para la referencia de .NET</span><span class="sxs-lookup"><span data-stu-id="62af6-216">Storage Client Library for .NET reference</span></span>](https://docs.microsoft.com/dotnet/api/overview/azure/storage?view=azure-dotnet)
- [<span data-ttu-id="62af6-217">Proveedor de tipos de almacenamiento de Azure</span><span class="sxs-lookup"><span data-stu-id="62af6-217">Azure Storage Type Provider</span></span>](http://fsprojects.github.io/AzureStorageTypeProvider/)
- [<span data-ttu-id="62af6-218">Blog del equipo de almacenamiento de Azure</span><span class="sxs-lookup"><span data-stu-id="62af6-218">Azure Storage Team Blog</span></span>](http://blogs.msdn.com/b/windowsazurestorage/)
- [<span data-ttu-id="62af6-219">Configurar cadenas de conexión</span><span class="sxs-lookup"><span data-stu-id="62af6-219">Configuring Connection Strings</span></span>](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="62af6-220">Introducción a almacenamiento de tabla de Azure en .NET</span><span class="sxs-lookup"><span data-stu-id="62af6-220">Getting Started with Azure Table Storage in .NET</span></span>](https://azure.microsoft.com/resources/samples/storage-table-dotnet-getting-started/)
