---
title: Introducción a Azure Table Storage mediante F#
description: Almacene datos estructurados en la nube mediante Azure Table Storage o Azure Cosmos DB.
author: sylvanc
ms.date: 03/26/2018
ms.openlocfilehash: 30ffd5f099dbb8efbf57104a2ade6c26304b7cee
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395206"
---
# <a name="get-started-with-azure-table-storage-and-the-azure-cosmos-db-table-api-using-f"></a>Introducción a Azure Table Storage y el Azure Cosmos DB Table API mediante F @ no__t-0

Azure Table Storage es un servicio que almacena datos de NoSQL estructurados en la nube. Table Storage es un almacén de claves y atributos con un diseño sin esquema. Dado que el almacenamiento de tabla no tiene esquemas, es fácil adaptar los datos a medida que evolucionen las necesidades de la aplicación. El acceso a los datos es rápido y rentable para todos los tipos de aplicaciones. Normalmente, el almacenamiento de tablas es significativamente menor que el de SQL tradicional para volúmenes de datos similares.

Puede usar Table Storage para almacenar conjuntos de datos flexibles, como datos de usuario para aplicaciones Web, libretas de direcciones, información de dispositivos y cualquier otro tipo de metadatos que requiera el servicio. Puede almacenar cualquier número de entidades en una tabla y una cuenta de almacenamiento puede contener cualquier número de tablas, hasta el límite de capacidad de la cuenta de almacenamiento.

Azure Cosmos DB proporciona el Table API para las aplicaciones escritas para Azure Table Storage y que necesitan funcionalidades Premium como:

- Distribución global llave en mano.
- Rendimiento dedicado en todo el mundo.
- Latencias de milisegundos de un solo dígito en el percentil valores percentil.
- Alta disponibilidad garantizada.
- Indexación secundaria automática.

Las aplicaciones escritas para Azure Table Storage pueden migrar a Azure Cosmos DB mediante el Table API sin necesidad de realizar ningún cambio en el código y aprovechar las ventajas de las funcionalidades Premium. El Table API tiene SDK de cliente disponibles para .NET, Java, Python y node. js.

Para obtener más información, vea [Introducción a la Table API de Azure Cosmos dB](https://docs.microsoft.com/azure/cosmos-db/table-introduction).

## <a name="about-this-tutorial"></a>Acerca de este tutorial

En este tutorial se muestra cómo F# escribir código para realizar algunas tareas comunes con el almacenamiento de tablas de Azure o el Table API Azure Cosmos dB, lo que incluye crear y eliminar una tabla e insertar, actualizar, eliminar y consultar datos de tabla.

## <a name="prerequisites"></a>Requisitos previos

Para usar esta guía, primero debe [crear una cuenta de almacenamiento de Azure o una](/azure/storage/storage-create-storage-account) cuenta de [Azure Cosmos dB](https://azure.microsoft.com/try/cosmosdb/).

## <a name="create-an-f-script-and-start-f-interactive"></a>Creación de F# un script e F# Inicio interactivo

Los ejemplos de este artículo se pueden usar en una F# aplicación o en un F# script. Para crear un F# script, cree un archivo con la extensión `.fsx`, por ejemplo `tables.fsx`, en el F# entorno de desarrollo.

A continuación, use un [Administrador de paquetes](package-management.md) como [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) para instalar el paquete `WindowsAzure.Storage` y haga referencia a `WindowsAzure.Storage.dll` en el script mediante una directiva `#r`. Vuelva a hacerlo para `Microsoft.WindowsAzure.ConfigurationManager` con el fin de obtener el espacio de nombres Microsoft. Azure.

### <a name="add-namespace-declarations"></a>Agregar declaraciones de espacio de nombres

Agregue las siguientes instrucciones `open` al principio del archivo `tables.fsx`:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L1-L5)]

### <a name="get-your-azure-storage-connection-string"></a>Obtener la cadena de conexión de Azure Storage

Si se va a conectar a Azure Storage Table service, necesitará la cadena de conexión para este tutorial. Puede copiar la cadena de conexión desde el Azure Portal. Para obtener más información sobre las cadenas de conexión, consulte Configuración de las [cadenas de conexión de almacenamiento](/azure/storage/storage-configure-connection-string).

### <a name="get-your-azure-cosmos-db-connection-string"></a>Obtener la cadena de conexión de Azure Cosmos DB

Si se va a conectar a Azure Cosmos DB, necesitará la cadena de conexión para este tutorial. Puede copiar la cadena de conexión desde el Azure Portal. En el Azure Portal, en la cuenta de Cosmos DB, vaya a **configuración** > **cadena de conexión**y haga clic en el botón **copiar** para copiar la cadena de conexión principal. 

En el tutorial, escriba la cadena de conexión en el script, como en el ejemplo siguiente:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L11-L11)]

Sin embargo, esto **no se recomienda** para los proyectos reales. La clave de la cuenta de almacenamiento es similar a la contraseña raíz de la cuenta de almacenamiento. Siempre debe proteger la clave de la cuenta de almacenamiento. Evite distribuirla a otros usuarios, codificarla de forma rígida o guardarla en un archivo de texto sin formato al que puedan acceder otras personas. Puede volver a generar la clave mediante Azure portal si cree que puede estar en peligro.

En el caso de las aplicaciones reales, la mejor manera de mantener la cadena de conexión de almacenamiento se encuentra en un archivo de configuración. Para capturar la cadena de conexión de un archivo de configuración, puede hacer lo siguiente:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L13-L15)]

El uso de Azure Configuration Manager es opcional. También puede usar una API, como el tipo `ConfigurationManager` del .NET Framework.

### <a name="parse-the-connection-string"></a>Analizar la cadena de conexión

Para analizar la cadena de conexión, use:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L21-L22)]

Esto devuelve un `CloudStorageAccount`.

### <a name="create-the-table-service-client"></a>Creación del cliente de Table service

La clase `CloudTableClient` permite recuperar tablas y entidades en el almacenamiento de tablas. Esta es una forma de crear el cliente del servicio:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L28-L29)]

Ahora está listo para escribir código que lee datos de y escribe datos en el almacenamiento de tablas.

### <a name="create-a-table"></a>Crear una tabla

En este ejemplo se muestra cómo crear una tabla si aún no existe:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L35-L39)]

### <a name="add-an-entity-to-a-table"></a>Agregar una entidad a una tabla

Una entidad debe tener un tipo que herede de `TableEntity`. Puede extender `TableEntity` de la forma que desee, pero el tipo *debe* tener un constructor sin parámetros. Solo las propiedades que tienen `get` y `set` se almacenan en la tabla de Azure.

La clave de partición y de fila de una entidad identifica de forma única la entidad en la tabla. Las entidades con la misma clave de partición se pueden consultar más rápidamente que las que tienen claves de partición diferentes, pero el uso de claves de partición diversas permite una mayor escalabilidad de las operaciones paralelas.

A continuación se muestra un ejemplo de un `Customer` que usa el `lastName` como clave de partición y `firstName` como clave de fila.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L45-L52)]

Ahora, agregue `Customer` a la tabla. Para ello, cree un `TableOperation` que se ejecute en la tabla. En este caso, se crea una operación `Insert`.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L54-L55)]

### <a name="insert-a-batch-of-entities"></a>Insertar un lote de entidades

Puede insertar un lote de entidades en una tabla mediante una sola operación de escritura. Las operaciones por lotes permiten combinar operaciones en una sola ejecución, pero tienen algunas restricciones:

- Puede realizar actualizaciones, eliminaciones e inserciones en la misma operación por lotes.
- Una operación por lotes puede incluir hasta 100 entidades.
- Todas las entidades de una operación por lotes deben tener la misma clave de partición.
- Aunque es posible realizar una consulta en una operación por lotes, debe ser la única operación del lote.

Este es un código que combina dos inserciones en una operación por lotes:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L62-L71)]

### <a name="retrieve-all-entities-in-a-partition"></a>Recuperar todas las entidades de una partición

Para consultar una tabla de todas las entidades de una partición, use un objeto `TableQuery`. Aquí, se filtran las entidades en las que "Smith" es la clave de partición.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L77-L82)]

Ahora imprime los resultados:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L84-L85)]

### <a name="retrieve-a-range-of-entities-in-a-partition"></a>Recuperar un intervalo de entidades de una partición

Si no desea consultar todas las entidades de una partición, puede especificar un intervalo combinando el filtro de clave de partición con un filtro de clave de fila. En este caso, se usan dos filtros para obtener todas las entidades de la partición "Smith" en las que la clave de fila (nombre de pila) empieza por una letra anterior a "M" en el alfabeto.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L91-L100)]

Ahora imprime los resultados:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L102-L103)]

### <a name="retrieve-a-single-entity"></a>Recuperación de una sola entidad

Puede escribir una consulta para recuperar una única entidad específica. Aquí se usa un `TableOperation` para especificar el cliente "Ben Smith". En lugar de una colección, obtiene una `Customer`. La forma más rápida de recuperar una sola entidad de la Table service es especificar la clave de partición y la clave de fila en una consulta.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L109-L111)]

Ahora imprime los resultados:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L113-L115)]

### <a name="replace-an-entity"></a>Reemplazar una entidad

Para actualizar una entidad, recupere el Table service, modifique el objeto entidad y, a continuación, guarde los cambios de nuevo en el Table service mediante una operación `Replace`. Esto hace que la entidad se reemplace por completo en el servidor, a menos que la entidad del servidor haya cambiado desde que se recuperó, en cuyo caso se produce un error en la operación. Este error se debe a evitar que la aplicación sobrescriba los cambios de otros orígenes accidentalmente.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L121-L128)]

### <a name="insert-or-replace-an-entity"></a>Inserción o reemplazo de una entidad

A veces, no se sabe si existe una entidad en la tabla. Y, si es así, los valores actuales almacenados en él ya no son necesarios. Puede usar `InsertOrReplace` para crear la entidad o reemplazarla si existe, independientemente de su estado.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L134-L141)]

### <a name="query-a-subset-of-entity-properties"></a>Consultar un subconjunto de propiedades de entidad

Una consulta de tabla puede recuperar solo algunas propiedades de una entidad en lugar de todas ellas. Esta técnica, denominada proyección, puede mejorar el rendimiento de las consultas, especialmente en el caso de entidades de gran tamaño. En este caso, solo se devuelven direcciones de correo electrónico con `DynamicTableEntity` y `EntityResolver`. Tenga en cuenta que no se admite la proyección en el emulador de almacenamiento local, por lo que este código solo se ejecuta cuando se usa una cuenta en el Table service.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L147-L158)]

### <a name="retrieve-entities-in-pages-asynchronously"></a>Recuperar entidades en páginas de forma asincrónica

Si está leyendo un gran número de entidades y desea procesarlas a medida que se recuperan en lugar de esperar a que se devuelvan todas, puede usar una consulta segmentada. Aquí se devuelven los resultados en páginas mediante un flujo de trabajo asincrónico para que la ejecución no se bloquee mientras se espera a que se devuelva un conjunto grande de resultados.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L163-L178)]

Ahora ejecuta este cálculo de forma sincrónica:

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L180-L180)]

### <a name="delete-an-entity"></a>Eliminar una entidad

Puede eliminar una entidad después de recuperarla. Al igual que con la actualización de una entidad, se produce un error si la entidad ha cambiado desde que se recuperó.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L186-L187)]

### <a name="delete-a-table"></a>Eliminar una tabla

Puede eliminar una tabla de una cuenta de almacenamiento. Una tabla que se ha eliminado no podrá volver a crearse durante un período de tiempo después de la eliminación.

[!code-fsharp[TableStorage](~/samples/snippets/fsharp/azure/table-storage.fsx#L193-L193)]

## <a name="next-steps"></a>Pasos siguientes

Ahora que ha aprendido los aspectos básicos del almacenamiento de tablas, siga estos vínculos para obtener más información acerca de las tareas de almacenamiento más complejas y el Table API de Azure Cosmos DB.

- [Introducción a Azure Cosmos DB Table API](https://docs.microsoft.com/azure/cosmos-db/table-introduction)
- [Referencia de la biblioteca de cliente de almacenamiento para .NET](https://docs.microsoft.com/dotnet/api/overview/azure/storage)
- [Azure Storage proveedor de tipos](https://fsprojects.github.io/AzureStorageTypeProvider/)
- [Blog del equipo de Azure Storage](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [Configurar cadenas de conexión](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)
