---
title: Empezar a trabajar con Azure Table storageF#
description: Store datos estructurados en la nube con Azure Table storage o Azure Cosmos DB.
author: sylvanc
ms.date: 03/26/2018
ms.openlocfilehash: 2b74a33023065ea809c2d7eb6202b1a254018422
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56966013"
---
# <a name="get-started-with-azure-table-storage-and-the-azure-cosmos-db-table-api-using-f"></a>Introducción a Azure Table storage y Azure Cosmos DB Table API con F\#

Azure Table storage es un servicio que almacena datos NoSQL estructurados en la nube. Table storage es un almacén de claves/atributos con un diseño sin esquema. Dado que el almacenamiento de tabla no tiene esquema, es fácil adaptar los datos como el evolucionan necesidades de la aplicación. Acceso a datos es rápido y rentable para todos los tipos de aplicaciones. Almacenamiento de tabla suele ser significativamente menor costo que SQL tradicional para volúmenes de datos similares.

Puede usar el almacenamiento de tablas para almacenar conjuntos de datos flexibles, como datos de usuario para aplicaciones web, libretas de direcciones, información del dispositivo y cualquier otro tipo de metadatos que necesita el servicio. Puede almacenar cualquier número de entidades en una tabla y una cuenta de almacenamiento puede contener cualquier número de tablas, hasta el límite de capacidad de la cuenta de almacenamiento.

Azure Cosmos DB proporciona la API de tabla para las aplicaciones escritas para Azure Table storage y que necesitan funcionalidades premium como:

- Distribución global llave en mano.
- Rendimiento dedicado en todo el mundo.
- Latencias de milisegundos en el percentil 99.
- Alta disponibilidad garantizada.
- Indexación secundaria automática.

Las aplicaciones escritas para Azure Table storage pueden migrar a Azure Cosmos DB mediante la API Table sin realizar ningún cambio en el código y aprovechar las ventajas de las funcionalidades premium. Table API tiene SDK de cliente disponibles para. NET, Java, Python y Node.js.

Para obtener más información, consulte [Introducción a Azure Cosmos DB Table API](https://docs.microsoft.com/azure/cosmos-db/table-introduction).

## <a name="about-this-tutorial"></a>Acerca de este tutorial

Este tutorial muestra cómo escribir F# código para realizar algunas tareas comunes con Azure Table storage o Azure Cosmos DB Table API, incluida la creación y eliminación de una tabla e Insertar, actualizar, eliminar y consultar datos de tabla.

## <a name="prerequisites"></a>Requisitos previos

Para usar esta guía, primero debe [crear una cuenta de almacenamiento de Azure](/azure/storage/storage-create-storage-account) o [cuenta de Azure Cosmos DB](https://azure.microsoft.com/try/cosmosdb/).


## <a name="create-an-f-script-and-start-f-interactive"></a>Crear un F# Script e iniciar F# interactivo

Los ejemplos de este artículo pueden usarse en cualquiera un F# aplicación o un F# secuencia de comandos. Para crear un F# de script, cree un archivo con el `.fsx` extensión, por ejemplo `tables.fsx`, en su F# entorno de desarrollo.

A continuación, use un [Administrador de paquetes](package-management.md) como [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) para instalar el `WindowsAzure.Storage` paquete y referencia `WindowsAzure.Storage.dll` en el script mediante un `#r`directiva. Hacerlo nuevamente por `Microsoft.WindowsAzure.ConfigurationManager` con el fin de obtener el espacio de nombres Microsoft.Azure.

### <a name="add-namespace-declarations"></a>Agregue las declaraciones de espacio de nombres

Agregue el siguiente `open` instrucciones a la parte superior de la `tables.fsx` archivo:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L1-L5)]

### <a name="get-your-azure-storage-connection-string"></a>Obtener la cadena de conexión de Azure Storage

Si se conecta a Azure Storage Table service, necesitará la cadena de conexión para este tutorial. Puede copiar la cadena de conexión desde el portal de Azure. Para obtener más información acerca de las cadenas de conexión, consulte [configurar cadenas de conexión de almacenamiento](/azure/storage/storage-configure-connection-string).

### <a name="get-your-azure-cosmos-db-connection-string"></a>Obtener la cadena de conexión de Azure Cosmos DB

Si se conecta a Azure Cosmos DB, necesitará la cadena de conexión para este tutorial. Puede copiar la cadena de conexión desde el portal de Azure. En el portal de Azure, en la cuenta de Cosmos DB, vaya a **configuración** > **cadena de conexión**y haga clic en el **copia** botón para copiar la conexión principal Cadena. 

Para este tutorial, escriba la cadena de conexión en el script, similar al ejemplo siguiente:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L11-L11)]

Sin embargo, esto es **no recomienda** proyectos reales. La clave de cuenta de almacenamiento es similar a la contraseña raíz de la cuenta de almacenamiento. Siempre debe proteger la clave de cuenta de almacenamiento. Evite distribuirla a otros usuarios, codificarla de forma o guardarlo en un archivo de texto sin formato que sea accesible a otros usuarios. Puede volver a generar la clave mediante Azure Portal si cree que puede verse comprometida.

Las aplicaciones para el real, la mejor manera de mantener la cadena de conexión de almacenamiento está en un archivo de configuración. Para capturar la cadena de conexión de un archivo de configuración, puede hacer esto:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L13-L15)]

Con el Administrador de configuración de Azure es opcional. También puede usar una API como .NET Framework `ConfigurationManager` tipo.

### <a name="parse-the-connection-string"></a>Analizar la cadena de conexión

Para analizar la cadena de conexión, use:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L21-L22)]

Esto devuelve un `CloudStorageAccount`.

### <a name="create-the-table-service-client"></a>Crear al cliente de Table service

La `CloudTableClient` clase le permite recuperar tablas y entidades en Table storage. Aquí es una forma de crear al cliente del servicio:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L28-L29)]

Ahora está listo para escribir código que lee y escribe datos en almacenamiento de tabla.

### <a name="create-a-table"></a>Creación de una tabla

En este ejemplo se muestra cómo crear una tabla si aún no existe:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L35-L39)]

### <a name="add-an-entity-to-a-table"></a>Agregar una entidad a una tabla

Una entidad debe tener un tipo que hereda de `TableEntity`. Puede extender `TableEntity` en como desee, pero su tipo *debe* tiene un constructor sin parámetros. Solo las propiedades que tienen ambos `get` y `set` se almacenan en la tabla de Azure.

Partición de una entidad y la clave de fila identifican inequívocamente en la tabla. Las entidades con la misma clave de partición pueden consultarse más rápidamente que aquellas con diferentes claves de partición, pero el uso de claves de partición diversas permite una mayor escalabilidad de las operaciones en paralelo.

Este es un ejemplo de un `Customer` que usa el `lastName` como clave de partición y el `firstName` como clave de fila.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L45-L52)]

Ahora agregue `Customer` a la tabla. Para ello, cree un `TableOperation` que se ejecuta en la tabla. En este caso, creará un `Insert` operación.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L54-L55)]

### <a name="insert-a-batch-of-entities"></a>Insertar un lote de entidades

Puede insertar un lote de entidades en una tabla mediante una sola operación de escritura. Operaciones por lotes le permiten combinar operaciones en una sola ejecución, pero tienen algunas restricciones:

- Puede realizar actualizaciones, eliminaciones e inserciones en la misma operación por lotes.
- Una operación por lotes puede incluir hasta 100 entidades.
- Todas las entidades de una operación por lotes deben tener la misma clave de partición.
- Aunque es posible realizar una consulta en una operación por lotes, debe ser la única operación del lote.

Este es un código que combina dos inserciones en una operación por lotes:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L62-L71)]

### <a name="retrieve-all-entities-in-a-partition"></a>Recuperar todas las entidades de una partición

Para consultar una tabla para todas las entidades de una partición, use un `TableQuery` objeto. En este caso, se filtran las entidades que "Smith" es la clave de partición.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L77-L82)]

Ahora imprima los resultados:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L84-L85)]


### <a name="retrieve-a-range-of-entities-in-a-partition"></a>Recuperar un intervalo de entidades de una partición

Si no desea consultar todas las entidades en una partición, puede especificar un intervalo combinando el filtro de clave de partición con un filtro de clave de fila. Aquí, se usa dos filtros para obtener todas las entidades en la partición "Smith" donde la clave de fila (nombre de pila) empieza por una letra anterior a "M" en el alfabeto.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L91-L100)]

Ahora imprima los resultados:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L102-L103)]

### <a name="retrieve-a-single-entity"></a>Recuperar una sola entidad

Puede escribir una consulta para recuperar una sola entidad concreta. Aquí, se usa un `TableOperation` para especificar el cliente "Ben Smith". En lugar de una colección, obtendrá un `Customer`. Especificar la clave de partición y la clave de fila en una consulta es la manera más rápida de recuperar una sola entidad de Table service.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L109-L111)]

Ahora imprima los resultados:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L113-L115)]


### <a name="replace-an-entity"></a>Reemplazar una entidad

Para actualizar una entidad, recupérela de Table service, modifique su objeto y, a continuación, guarde los cambios a Table service utilizando un `Replace` operación. Esto hace que la entidad se reemplace por completo en el servidor, a menos que la entidad en el servidor ha cambiado desde que se recuperó, en cuyo caso se produce un error en la operación. Este error es impedir que la aplicación sobrescriba accidentalmente los cambios de otros orígenes.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L121-L128)]

### <a name="insert-or-replace-an-entity"></a>Insertar o reemplazar una entidad

En ocasiones no sabe si existe una entidad en la tabla. Y si es así, ya no son necesarios los valores actuales almacenados en él. Puede usar `InsertOrReplace` para crear la entidad, o reemplácelo si existe, independientemente de su estado.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L134-L141)]

### <a name="query-a-subset-of-entity-properties"></a>Consultar un subconjunto de las propiedades de entidad

Una consulta de tabla puede recuperar una serie de propiedades de una entidad en lugar de todos ellos. Esta técnica, denominada proyección, puede mejorar el rendimiento, especialmente para las entidades de gran tamaño. En este caso, devuelve sólo correo electrónico direcciones con `DynamicTableEntity` y `EntityResolver`. Tenga en cuenta que proyección no se admite en el emulador de almacenamiento local, por lo que este código se ejecuta solo cuando está usando una cuenta en Table service.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L147-L158)]

### <a name="retrieve-entities-in-pages-asynchronously"></a>Recuperar las entidades en las páginas de forma asincrónica

Si está leyendo un gran número de entidades, y desea procesarlas a medida que se recuperan en lugar de esperar todos a devolver, puede usar una consulta segmentada. A continuación, devolver resultados en páginas mediante el uso de un flujo de trabajo asincrónico para que la ejecución no se bloquea mientras espera para un amplio conjunto de resultados que se va a devolver.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L163-L178)]

Ahora ejecute sincrónicamente este cálculo:

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L180-L180)]

### <a name="delete-an-entity"></a>Eliminar una entidad

Puede eliminar una entidad una vez que haya recuperado. Al igual que con la actualización de una entidad, esto se produce un error si la entidad ha cambiado desde que se recuperó.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L186-L187)]

### <a name="delete-a-table"></a>Eliminar una tabla

Puede eliminar una tabla de una cuenta de almacenamiento. Una tabla que se ha eliminado no estará disponible para volver a crearse durante un período de tiempo tras la eliminación.

[!code-fsharp[TableStorage](../../../samples/snippets/fsharp/azure/table-storage.fsx#L193-L193)]

## <a name="next-steps"></a>Pasos siguientes

Ahora que ha aprendido los conceptos básicos del almacenamiento de tablas, siga estos vínculos para obtener información sobre tareas de almacenamiento más complejas y Azure Cosmos DB Table API.

- [Introducción a Azure Cosmos DB Table API](https://docs.microsoft.com/azure/cosmos-db/table-introduction)
- [Biblioteca de cliente de almacenamiento para la referencia de .NET](https://docs.microsoft.com/dotnet/api/overview/azure/storage?view=azure-dotnet)
- [Proveedor de tipos de almacenamiento de Azure](https://fsprojects.github.io/AzureStorageTypeProvider/)
- [Blog del equipo de almacenamiento de Azure](https://blogs.msdn.com/b/windowsazurestorage/)
- [Configurar cadenas de conexión](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)
- [Introducción a Azure Table Storage en .NET](https://azure.microsoft.com/resources/samples/storage-table-dotnet-getting-started/)
