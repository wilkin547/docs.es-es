---
title: "Introducción al almacenamiento de tabla de Azure con F #"
description: "Almacenar datos estructurados en la nube con almacenamiento de tabla de Azure, un almacén de datos NoSQL."
keywords: "Visual f #, f #, funcional de programación,. NET, .NET Core, Azure"
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 9e5d6cea-a98c-461e-a5cc-75f1d154eafd
ms.openlocfilehash: bf833a96809768011f26df35332ab2372ced2aaf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="get-started-with-azure-table-storage-using-f"></a><span data-ttu-id="12ed4-104">Introducción al almacenamiento de tabla de Azure con F #</span><span class="sxs-lookup"><span data-stu-id="12ed4-104">Get started with Azure Table storage using F#</span></span> #

<span data-ttu-id="12ed4-105">El almacenamiento de tabla es un servicio que almacena datos estructurados de NoSQL en la nube.</span><span class="sxs-lookup"><span data-stu-id="12ed4-105">Azure Table storage is a service that stores structured NoSQL data in the cloud.</span></span> <span data-ttu-id="12ed4-106">Almacenamiento de tabla es un almacén de clave/atributo con un diseño schemaless.</span><span class="sxs-lookup"><span data-stu-id="12ed4-106">Table storage is a key/attribute store with a schemaless design.</span></span> <span data-ttu-id="12ed4-107">Dado que el almacenamiento de tabla es schemaless, es fácil adaptar los datos como las necesidades de su evolucionar de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="12ed4-107">Because Table storage is schemaless, it's easy to adapt your data as the needs of your application evolve.</span></span> <span data-ttu-id="12ed4-108">Acceso a los datos es rápido y rentable para todos los tipos de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="12ed4-108">Access to data is fast and cost-effective for all kinds of applications.</span></span> <span data-ttu-id="12ed4-109">Almacenamiento de tabla suele ser significativamente menor costo que SQL tradicional para similar volúmenes de datos.</span><span class="sxs-lookup"><span data-stu-id="12ed4-109">Table storage is typically significantly lower in cost than traditional SQL for similar volumes of data.</span></span>

<span data-ttu-id="12ed4-110">Puede usar el almacenamiento de tabla para almacenar conjuntos de datos flexible, como datos de usuario para aplicaciones web, libretas de direcciones, información del dispositivo y cualquier otro tipo de metadatos que necesite el servicio.</span><span class="sxs-lookup"><span data-stu-id="12ed4-110">You can use Table storage to store flexible datasets, such as user data for web applications, address books, device information, and any other type of metadata that your service requires.</span></span> <span data-ttu-id="12ed4-111">Puede almacenar cualquier número de entidades en una tabla y una cuenta de almacenamiento puede contener cualquier número de tablas, hasta el límite de capacidad de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="12ed4-111">You can store any number of entities in a table, and a storage account may contain any number of tables, up to the capacity limit of the storage account.</span></span>

### <a name="about-this-tutorial"></a><span data-ttu-id="12ed4-112">Acerca de este tutorial</span><span class="sxs-lookup"><span data-stu-id="12ed4-112">About this tutorial</span></span>

<span data-ttu-id="12ed4-113">Este tutorial muestra cómo escribir código de F # para realizar algunas tareas comunes mediante almacenamiento de tabla de Azure, incluida la creación y eliminar una tabla e Insertar, actualizar, eliminar y consultar datos de la tabla.</span><span class="sxs-lookup"><span data-stu-id="12ed4-113">This tutorial shows how to write F# code to do some common tasks using Azure Table storage, including creating and deleting a table and inserting, updating, deleting, and querying table data.</span></span>

<span data-ttu-id="12ed4-114">Para obtener información conceptual del almacenamiento de tabla, vea [la Guía de .NET para el almacenamiento de tabla](/azure/storage/storage-dotnet-how-to-use-tables)</span><span class="sxs-lookup"><span data-stu-id="12ed4-114">For a conceptual overview of table storage, please see [the .NET guide for table storage](/azure/storage/storage-dotnet-how-to-use-tables)</span></span>

## <a name="prerequisites"></a><span data-ttu-id="12ed4-115">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="12ed4-115">Prerequisites</span></span>

<span data-ttu-id="12ed4-116">Para utilizar esta guía, primero debe [crear una cuenta de almacenamiento de Azure](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="12ed4-116">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="12ed4-117">También necesitará la clave de acceso de almacenamiento para esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="12ed4-117">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="12ed4-118">Crear un Script de F # y el inicio de F # Interactive</span><span class="sxs-lookup"><span data-stu-id="12ed4-118">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="12ed4-119">Los ejemplos de este artículo pueden usarse en una aplicación de F # o un script de F #.</span><span class="sxs-lookup"><span data-stu-id="12ed4-119">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="12ed4-120">Para crear un script de F #, cree un archivo con el `.fsx` extensión, por ejemplo `tables.fsx`, en el entorno de desarrollo de F #.</span><span class="sxs-lookup"><span data-stu-id="12ed4-120">To create an F# script, create a file with the `.fsx` extension, for example `tables.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="12ed4-121">A continuación, use un [el Administrador de paquetes](package-management.md) como [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) para instalar el `WindowsAzure.Storage` paquete y referencia `WindowsAzure.Storage.dll` en el script mediante un `#r`directiva.</span><span class="sxs-lookup"><span data-stu-id="12ed4-121">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span> <span data-ttu-id="12ed4-122">Hacer nuevo para 'Microsoft.WindowsAzure.ConfigurationManager' con el fin de obtener el espacio de nombres Microsoft.Azure.</span><span class="sxs-lookup"><span data-stu-id="12ed4-122">Do it again for \`Microsoft.WindowsAzure.ConfigurationManager' in order to get the Microsoft.Azure namespace.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="12ed4-123">Agregue las declaraciones de espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="12ed4-123">Add namespace declarations</span></span>

<span data-ttu-id="12ed4-124">Agregue el siguiente `open` instrucciones a la parte superior de la `tables.fsx` archivo:</span><span class="sxs-lookup"><span data-stu-id="12ed4-124">Add the following `open` statements to the top of the `tables.fsx` file:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="12ed4-125">Obtener la cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="12ed4-125">Get your connection string</span></span>

<span data-ttu-id="12ed4-126">Necesitará una cadena de conexión de almacenamiento de Azure para este tutorial.</span><span class="sxs-lookup"><span data-stu-id="12ed4-126">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="12ed4-127">Para obtener más información acerca de las cadenas de conexión, vea [configurar cadenas de conexión de almacenamiento](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="12ed4-127">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="12ed4-128">Para el tutorial, especificará la cadena de conexión en el script, similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="12ed4-128">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L11-L11)]

<span data-ttu-id="12ed4-129">Sin embargo, esto es **no recomienda** proyectos de una manera real.</span><span class="sxs-lookup"><span data-stu-id="12ed4-129">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="12ed4-130">La clave de cuenta de almacenamiento es similar a la contraseña raíz para la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="12ed4-130">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="12ed4-131">Tenga siempre cuidado proteger la clave de cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="12ed4-131">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="12ed4-132">Evitar la distribución a otros usuarios, codificar de forma rígida, o guardarlo en un archivo de texto sin formato sea accesible a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="12ed4-132">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="12ed4-133">Puede volver a generar la clave mediante el Portal de Azure si cree que se han comprometido.</span><span class="sxs-lookup"><span data-stu-id="12ed4-133">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="12ed4-134">Las aplicaciones de una manera real, la mejor manera de mantener la cadena de conexión de almacenamiento está en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="12ed4-134">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="12ed4-135">Para capturar la cadena de conexión de un archivo de configuración, puede hacer esto:</span><span class="sxs-lookup"><span data-stu-id="12ed4-135">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L13-L15)]

<span data-ttu-id="12ed4-136">Con el Administrador de configuración de Azure es opcional.</span><span class="sxs-lookup"><span data-stu-id="12ed4-136">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="12ed4-137">También puede utilizar una API como .NET Framework `ConfigurationManager` tipo.</span><span class="sxs-lookup"><span data-stu-id="12ed4-137">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="12ed4-138">Analizar la cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="12ed4-138">Parse the connection string</span></span>

<span data-ttu-id="12ed4-139">Para analizar la cadena de conexión, use:</span><span class="sxs-lookup"><span data-stu-id="12ed4-139">To parse the connection string, use:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L21-L22)]

<span data-ttu-id="12ed4-140">Esto devolverá una `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="12ed4-140">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-table-service-client"></a><span data-ttu-id="12ed4-141">Crear al cliente del servicio tabla</span><span class="sxs-lookup"><span data-stu-id="12ed4-141">Create the Table service client</span></span>

<span data-ttu-id="12ed4-142">La `CloudTableClient` clase le permite recuperar las tablas y las entidades almacenadas en almacenamiento de tabla.</span><span class="sxs-lookup"><span data-stu-id="12ed4-142">The `CloudTableClient` class enables you to retrieve tables and entities stored in Table storage.</span></span> <span data-ttu-id="12ed4-143">Aquí es una manera de crear al cliente del servicio:</span><span class="sxs-lookup"><span data-stu-id="12ed4-143">Here's one way to create the service client:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L28-L29)]

<span data-ttu-id="12ed4-144">Ahora está listo para escribir código que lee datos de y escribe datos en el almacenamiento de tabla.</span><span class="sxs-lookup"><span data-stu-id="12ed4-144">Now you are ready to write code that reads data from and writes data to Table storage.</span></span>

## <a name="create-a-table"></a><span data-ttu-id="12ed4-145">Crear una tabla</span><span class="sxs-lookup"><span data-stu-id="12ed4-145">Create a table</span></span>

<span data-ttu-id="12ed4-146">En este ejemplo se muestra cómo crear una tabla si aún no existe:</span><span class="sxs-lookup"><span data-stu-id="12ed4-146">This example shows how to create a table if it does not already exist:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L35-L39)]

## <a name="add-an-entity-to-a-table"></a><span data-ttu-id="12ed4-147">Agregar una entidad a una tabla</span><span class="sxs-lookup"><span data-stu-id="12ed4-147">Add an entity to a table</span></span>

<span data-ttu-id="12ed4-148">Una entidad debe tener un tipo que hereda de `TableEntity`.</span><span class="sxs-lookup"><span data-stu-id="12ed4-148">An entity has to have a type that inherits from `TableEntity`.</span></span> <span data-ttu-id="12ed4-149">Puede extender `TableEntity` en como desee, pero su tipo *debe* tiene un constructor sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="12ed4-149">You can extend `TableEntity` in any way you like, but your type *must* have a parameter-less constructor.</span></span> <span data-ttu-id="12ed4-150">Solo las propiedades que tienen ambos `get` y `set` se almacenará en la tabla de Azure.</span><span class="sxs-lookup"><span data-stu-id="12ed4-150">Only properties that have both `get` and `set` will be stored in your Azure Table.</span></span>

<span data-ttu-id="12ed4-151">Partición de una entidad y la clave de fila identifican la entidad en la tabla.</span><span class="sxs-lookup"><span data-stu-id="12ed4-151">An entity's partition and row key uniquely identify the entity in the table.</span></span> <span data-ttu-id="12ed4-152">Entidades con la misma clave de partición se pueden consultar más rápido que aquellos con las claves de partición diferente, pero el uso de las claves de partición diversos permite para una mayor escalabilidad de operaciones en paralelo.</span><span class="sxs-lookup"><span data-stu-id="12ed4-152">Entities with the same partition key can be queried faster than those with different partition keys, but using diverse partition keys allows for greater scalability of parallel operations.</span></span>

<span data-ttu-id="12ed4-153">Este es un ejemplo de un `Customer` que usa el `lastName` como la clave de partición y el `firstName` como la clave de fila.</span><span class="sxs-lookup"><span data-stu-id="12ed4-153">Here's an example of a `Customer` that uses the `lastName` as the partition key and the `firstName` as the row key.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L45-L52)]

<span data-ttu-id="12ed4-154">Ahora vamos a agregar nuestro `Customer` a la tabla.</span><span class="sxs-lookup"><span data-stu-id="12ed4-154">Now we'll add our `Customer` to the table.</span></span> <span data-ttu-id="12ed4-155">Para ello, se crea un `TableOperation` que se ejecutará en la tabla.</span><span class="sxs-lookup"><span data-stu-id="12ed4-155">To do so, you create a `TableOperation` that will execute on the table.</span></span> <span data-ttu-id="12ed4-156">En este caso, cree un `Insert` operación.</span><span class="sxs-lookup"><span data-stu-id="12ed4-156">In this case, you create an `Insert` operation.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L54-L55)]

## <a name="insert-a-batch-of-entities"></a><span data-ttu-id="12ed4-157">Insertar un lote de entidades</span><span class="sxs-lookup"><span data-stu-id="12ed4-157">Insert a batch of entities</span></span>

<span data-ttu-id="12ed4-158">Puede insertar un lote de entidades en una tabla con una sola operación de escritura.</span><span class="sxs-lookup"><span data-stu-id="12ed4-158">You can insert a batch of entities into a table using a single write operation.</span></span> <span data-ttu-id="12ed4-159">Operaciones por lotes permiten combinar las operaciones en una sola ejecución, pero tienen algunas restricciones:</span><span class="sxs-lookup"><span data-stu-id="12ed4-159">Batch operations allow you to combine operations into a single execution, but they have some restrictions:</span></span>

- <span data-ttu-id="12ed4-160">Puede realizar actualizaciones, elimina y se inserta en la misma operación por lotes.</span><span class="sxs-lookup"><span data-stu-id="12ed4-160">You can perform updates, deletes, and inserts in the same batch operation.</span></span>
- <span data-ttu-id="12ed4-161">Una operación por lotes puede incluir hasta 100 entidades.</span><span class="sxs-lookup"><span data-stu-id="12ed4-161">A batch operation can include up to 100 entities.</span></span>
- <span data-ttu-id="12ed4-162">Todas las entidades de una operación por lotes deben tener la misma clave de partición.</span><span class="sxs-lookup"><span data-stu-id="12ed4-162">All entities in a batch operation must have the same partition key.</span></span>
- <span data-ttu-id="12ed4-163">Aunque es posible realizar una consulta en una operación por lotes, debe ser la única operación en el lote.</span><span class="sxs-lookup"><span data-stu-id="12ed4-163">While it is possible to perform a query in a batch operation, it must be the only operation in the batch.</span></span>

<span data-ttu-id="12ed4-164">Este es un código que combina dos inserciones en una operación por lotes:</span><span class="sxs-lookup"><span data-stu-id="12ed4-164">Here's some code that combines two inserts into a batch operation:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L62-L71)]

## <a name="retrieve-all-entities-in-a-partition"></a><span data-ttu-id="12ed4-165">Recuperar todas las entidades de una partición</span><span class="sxs-lookup"><span data-stu-id="12ed4-165">Retrieve all entities in a partition</span></span>

<span data-ttu-id="12ed4-166">Para consultar una tabla para todas las entidades de una partición, use un `TableQuery` objeto.</span><span class="sxs-lookup"><span data-stu-id="12ed4-166">To query a table for all entities in a partition, use a `TableQuery` object.</span></span> <span data-ttu-id="12ed4-167">En este caso, se filtran las entidades donde "Buster" es la clave de partición.</span><span class="sxs-lookup"><span data-stu-id="12ed4-167">Here, you filter for entities where "Buster" is the partition key.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L77-L80)]

<span data-ttu-id="12ed4-168">Ahora imprimir los resultados:</span><span class="sxs-lookup"><span data-stu-id="12ed4-168">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L84-L85)]


## <a name="retrieve-a-range-of-entities-in-a-partition"></a><span data-ttu-id="12ed4-169">Recuperar un intervalo de entidades en una partición</span><span class="sxs-lookup"><span data-stu-id="12ed4-169">Retrieve a range of entities in a partition</span></span>

<span data-ttu-id="12ed4-170">Si no desea consultar todas las entidades en una partición, puede especificar un intervalo combinando el filtro de clave de partición con un filtro de clave de fila.</span><span class="sxs-lookup"><span data-stu-id="12ed4-170">If you don't want to query all the entities in a partition, you can specify a range by combining the partition key filter with a row key filter.</span></span> <span data-ttu-id="12ed4-171">Aquí, se usa dos filtros para obtener todas las entidades de la partición "Buster" en la clave de fila (nombre) comienza con una letra anterior a "M" en el alfabeto.</span><span class="sxs-lookup"><span data-stu-id="12ed4-171">Here, you use two filters to get all entities in the "Buster" partition where the row key (first name) starts with a letter earlier than "M" in the alphabet.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L91-L100)]

<span data-ttu-id="12ed4-172">Ahora imprimir los resultados:</span><span class="sxs-lookup"><span data-stu-id="12ed4-172">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L102-L103)]

## <a name="retrieve-a-single-entity"></a><span data-ttu-id="12ed4-173">Recuperar una sola entidad</span><span class="sxs-lookup"><span data-stu-id="12ed4-173">Retrieve a single entity</span></span>

<span data-ttu-id="12ed4-174">Puede escribir una consulta para recuperar una entidad única, específica.</span><span class="sxs-lookup"><span data-stu-id="12ed4-174">You can write a query to retrieve a single, specific entity.</span></span> <span data-ttu-id="12ed4-175">A continuación, use un `TableOperation` para especificar el cliente "Larry Buster".</span><span class="sxs-lookup"><span data-stu-id="12ed4-175">Here, you use a `TableOperation` to specify the customer "Larry Buster".</span></span> <span data-ttu-id="12ed4-176">En lugar de una colección, se recibe un `Customer`.</span><span class="sxs-lookup"><span data-stu-id="12ed4-176">Instead of a collection, you get back a `Customer`.</span></span> <span data-ttu-id="12ed4-177">Especificar la clave de partición y la clave de fila en una consulta es la manera más rápida de recuperar una entidad única desde el servicio de la tabla.</span><span class="sxs-lookup"><span data-stu-id="12ed4-177">Specifying both the partition key and the row key in a query is the fastest way to retrieve a single entity from the Table service.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L109-L111)]

<span data-ttu-id="12ed4-178">Ahora imprimir los resultados:</span><span class="sxs-lookup"><span data-stu-id="12ed4-178">You now print the results:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L113-L115)]


## <a name="replace-an-entity"></a><span data-ttu-id="12ed4-179">Reemplazar una entidad</span><span class="sxs-lookup"><span data-stu-id="12ed4-179">Replace an entity</span></span>

<span data-ttu-id="12ed4-180">Para actualizar una entidad, recuperar desde el servicio tabla, modificar el objeto de entidad y, a continuación, guarde los cambios a la tabla de servicio mediante un `Replace` operación.</span><span class="sxs-lookup"><span data-stu-id="12ed4-180">To update an entity, retrieve it from the Table service, modify the entity object, and then save the changes back to the Table service using a `Replace` operation.</span></span> <span data-ttu-id="12ed4-181">Esto hace que la entidad que se va a reemplazar completamente en el servidor, a menos que la entidad en el servidor ha cambiado desde que se recuperó, en cuyo caso se producirá un error de la operación.</span><span class="sxs-lookup"><span data-stu-id="12ed4-181">This causes the entity to be fully replaced on the server, unless the entity on the server has changed since it was retrieved, in which case the operation will fail.</span></span> <span data-ttu-id="12ed4-182">Este error es evitar que la aplicación se ha sobrescrito accidentalmente cambios de otros orígenes.</span><span class="sxs-lookup"><span data-stu-id="12ed4-182">This failure is to prevent your application from inadvertently overwriting changes from other sources.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L121-L128)]

## <a name="insert-or-replace-an-entity"></a><span data-ttu-id="12ed4-183">Insertar o reemplazar una entidad</span><span class="sxs-lookup"><span data-stu-id="12ed4-183">Insert-or-replace an entity</span></span>

<span data-ttu-id="12ed4-184">A veces, no sabe si la entidad existe en la tabla o no.</span><span class="sxs-lookup"><span data-stu-id="12ed4-184">Sometimes, you don't know if the entity exists in the table or not.</span></span> <span data-ttu-id="12ed4-185">Y si lo hace, ya no son necesarios los valores actuales almacenados en ella.</span><span class="sxs-lookup"><span data-stu-id="12ed4-185">And if it does, the current values stored in it are no longer needed.</span></span> <span data-ttu-id="12ed4-186">Puede usar `InsertOrReplace` para crear la entidad o cámbielo si existe, independientemente de su estado.</span><span class="sxs-lookup"><span data-stu-id="12ed4-186">You can use `InsertOrReplace` to create the entity, or replace it if it exists, regardless of its state.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L134-L140)]

## <a name="query-a-subset-of-entity-properties"></a><span data-ttu-id="12ed4-187">Consultar un subconjunto de propiedades de entidad</span><span class="sxs-lookup"><span data-stu-id="12ed4-187">Query a subset of entity properties</span></span>

<span data-ttu-id="12ed4-188">Una consulta de tabla puede recuperar solo unas pocas propiedades de una entidad en lugar de todos ellos.</span><span class="sxs-lookup"><span data-stu-id="12ed4-188">A table query can retrieve just a few properties from an entity instead of all of them.</span></span> <span data-ttu-id="12ed4-189">Esta técnica, denominada proyección, puede mejorar el rendimiento, especialmente para entidades de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="12ed4-189">This technique, called projection, can improve query performance, especially for large entities.</span></span> <span data-ttu-id="12ed4-190">En este caso, se devuelven solo correo electrónico aborda el uso de `DynamicTableEntity` y `EntityResolver`.</span><span class="sxs-lookup"><span data-stu-id="12ed4-190">Here, you return only email addresses using `DynamicTableEntity` and `EntityResolver`.</span></span> <span data-ttu-id="12ed4-191">Tenga en cuenta que no se admite proyección en el emulador de almacenamiento local, por lo que este código se ejecuta sólo cuando se usa una cuenta en el servicio de la tabla.</span><span class="sxs-lookup"><span data-stu-id="12ed4-191">Note that projection is not supported on the local storage emulator, so this code runs only when you're using an account on the Table service.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L146-L157)]

## <a name="retrieve-entities-in-pages-asynchronously"></a><span data-ttu-id="12ed4-192">Recuperar entidades en las páginas de forma asincrónica</span><span class="sxs-lookup"><span data-stu-id="12ed4-192">Retrieve entities in pages asynchronously</span></span>

<span data-ttu-id="12ed4-193">Si está leyendo un gran número de entidades y desea procesarlas a medida que se recuperan en lugar de esperar a todos los que devuelven, puede utilizar una consulta segmentada.</span><span class="sxs-lookup"><span data-stu-id="12ed4-193">If you are reading a large number of entities, and you want to process them as they are retrieved rather than waiting for them all to return, you can use a segmented query.</span></span> <span data-ttu-id="12ed4-194">En este caso, se devuelven resultados en páginas mediante el uso de un flujo de trabajo asincrónico para que no la ejecución se bloquea mientras espera para un gran conjunto de resultados para devolver.</span><span class="sxs-lookup"><span data-stu-id="12ed4-194">Here, you return results in pages by using an async workflow so that execution is not blocked while you're waiting for a large set of results to return.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L163-L177)]

<span data-ttu-id="12ed4-195">Ahora ejecute sincrónicamente este cálculo:</span><span class="sxs-lookup"><span data-stu-id="12ed4-195">You now execute this computation synchronously:</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L179-L179)]

## <a name="delete-an-entity"></a><span data-ttu-id="12ed4-196">Eliminar una entidad</span><span class="sxs-lookup"><span data-stu-id="12ed4-196">Delete an entity</span></span>

<span data-ttu-id="12ed4-197">Puede eliminar una entidad después de que se han recuperado.</span><span class="sxs-lookup"><span data-stu-id="12ed4-197">You can delete an entity after you have retrieved it.</span></span> <span data-ttu-id="12ed4-198">Al igual que con la actualización de una entidad, se producirá un error si la entidad ha cambiado desde que recuperó.</span><span class="sxs-lookup"><span data-stu-id="12ed4-198">As with updating an entity, this will fail if the entity has changed since you retrieved it.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L185-L186)]

## <a name="delete-a-table"></a><span data-ttu-id="12ed4-199">Eliminar una tabla</span><span class="sxs-lookup"><span data-stu-id="12ed4-199">Delete a table</span></span>

<span data-ttu-id="12ed4-200">Puede eliminar una tabla de una cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="12ed4-200">You can delete a table from a storage account.</span></span> <span data-ttu-id="12ed4-201">Una tabla que se ha eliminado no estará disponible para volver a crearse durante un período de tiempo tras la eliminación.</span><span class="sxs-lookup"><span data-stu-id="12ed4-201">A table that has been deleted will be unavailable to be re-created for a period of time following the deletion.</span></span>

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L192-L192)]

## <a name="next-steps"></a><span data-ttu-id="12ed4-202">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="12ed4-202">Next steps</span></span>

<span data-ttu-id="12ed4-203">Ahora que conoce los fundamentos del almacenamiento de tabla, siga estos vínculos para obtener información acerca de las tareas más complejas de almacenamiento:</span><span class="sxs-lookup"><span data-stu-id="12ed4-203">Now that you've learned the basics of Table storage, follow these links to learn about more complex storage tasks:</span></span>

- [<span data-ttu-id="12ed4-204">Biblioteca de cliente de almacenamiento para la referencia de .NET</span><span class="sxs-lookup"><span data-stu-id="12ed4-204">Storage Client Library for .NET reference</span></span>](http://go.microsoft.com/fwlink/?LinkID=390731&clcid=0x409)
- [<span data-ttu-id="12ed4-205">Proveedor de tipos de almacenamiento de Azure</span><span class="sxs-lookup"><span data-stu-id="12ed4-205">Azure Storage Type Provider</span></span>](http://fsprojects.github.io/AzureStorageTypeProvider/)
- [<span data-ttu-id="12ed4-206">Blog del equipo de almacenamiento de Azure</span><span class="sxs-lookup"><span data-stu-id="12ed4-206">Azure Storage Team Blog</span></span>](http://blogs.msdn.com/b/windowsazurestorage/)
- [<span data-ttu-id="12ed4-207">Configurar cadenas de conexión</span><span class="sxs-lookup"><span data-stu-id="12ed4-207">Configuring Connection Strings</span></span>](http://msdn.microsoft.com/library/azure/ee758697.aspx)
- [<span data-ttu-id="12ed4-208">Introducción a almacenamiento de tabla de Azure en .NET</span><span class="sxs-lookup"><span data-stu-id="12ed4-208">Getting Started with Azure Table Storage in .NET</span></span>](https://azure.microsoft.com/documentation/samples/storage-table-dotnet-getting-started/)
