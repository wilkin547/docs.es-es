---
title: Cadenas de conexión en el Entity Framework ADO.NET
description: Obtenga información sobre las cadenas de conexión en el Entity Framework, que contienen información para conectarse al proveedor de datos ADO.NET y acerca de los archivos de asignación y de modelo.
ms.date: 10/15/2018
ms.assetid: 78d516bc-c99f-4865-8ff1-d856bc1a01c0
ms.openlocfilehash: 2ae25f5881c033a84d65f5b0b4ed14b4866dbcb3
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286875"
---
# <a name="connection-strings-in-the-adonet-entity-framework"></a>Cadenas de conexión en el Entity Framework ADO.NET

Una cadena de conexión contiene información de inicialización que se transfiere como un parámetro desde un proveedor de datos a un origen de datos. La sintaxis depende del proveedor de datos y la cadena de conexión se analiza mientras se intenta abrir una conexión. Las cadenas de conexión que usa Entity Framework contienen la información que se emplea para conectar con el proveedor de datos ADO.NET subyacente que Entity Framework admite. También contienen información sobre los archivos del modelo y de asignación necesarios.

El proveedor de EntityClient utiliza la cadena de conexión al obtener acceso a los metadatos del modelo y de asignación y al conectar con el origen de datos. Se puede obtener acceso a la cadena de conexión o establecerse a través de la propiedad <xref:System.Data.EntityClient.EntityConnection.ConnectionString%2A> de <xref:System.Data.EntityClient.EntityConnection>. La clase <xref:System.Data.EntityClient.EntityConnectionStringBuilder> se puede utilizar para construir mediante programación los parámetros de la cadena de conexión o tener acceso a ellos. Para obtener más información, vea [Cómo: compilar una cadena de conexión de EntityConnection](how-to-build-an-entityconnection-connection-string.md).

Las [herramientas de Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100)) generan una cadena de conexión que se almacena en el archivo de configuración de la aplicación. <xref:System.Data.Objects.ObjectContext> recupera esta información de conexión automáticamente al crear consultas de objetos. Se puede tener acceso al elemento  <xref:System.Data.EntityClient.EntityConnection> que usa una instancia de <xref:System.Data.Objects.ObjectContext> desde la propiedad <xref:System.Data.Objects.ObjectContext.Connection%2A>. Para obtener más información, consulte [Administración de conexiones y transacciones](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896325(v=vs.100)).

## <a name="connection-string-syntax"></a>Sintaxis de cadenas de conexión

Para obtener información sobre la sintaxis general de las cadenas de conexión, vea [Sintaxis de cadena de conexión | Cadenas de conexión en ADO.NET](../connection-strings.md#connection-string-syntax).

## <a name="connection-string-parameters"></a>Parámetros de la cadena de conexión

En la tabla siguiente se muestran los nombres válidos para los valores de palabra clave en la propiedad <xref:System.Data.EntityClient.EntityConnection.ConnectionString%2A>.

|Palabra clave|Descripción|
|-------------|-----------------|
|`Provider`|Se requiere si no se especifica la palabra clave `Name`. El nombre del proveedor, que se usa para recuperar el objeto <xref:System.Data.Common.DbProviderFactory> para el proveedor subyacente. Este valor es constante.<br /><br /> Cuando la palabra clave `Name` no se incluye en una cadena de conexión de Entity, se requiere un valor no vacío para la palabra clave `Provider`. Esta palabra clave y la palabra clave `Name` se excluyen mutuamente.|
|`Provider Connection String`|Opcional. Especifica la cadena de conexión específica del proveedor que se pasa al origen de datos subyacente. Esta cadena de conexión contiene pares de palabra clave y valor válidos para el proveedor de datos. Un valor de `Provider Connection String` no válido provocará un error en tiempo de ejecución cuando sea evaluado por el origen de datos.<br /><br /> Esta palabra clave y la palabra clave `Name` se excluyen mutuamente.<br /><br /> Asegúrese de omitir el valor de acuerdo con la sintaxis general de las [cadenas de conexión de ADO.net](../connection-strings.md). Considere, por ejemplo, la siguiente cadena de conexión: `Server=serverName; User ID = userID` . Debe ser un carácter de escape porque contiene un punto y coma. Como no contiene comillas dobles, se pueden usar para el escape:<br /><br /> `Provider Connection String ="Server=serverName; User ID = userID";`|
|`Metadata`|Se requiere si no se especifica la palabra clave `Name`. Una lista delimitada por barras verticales de los directorios, archivos y localizadores de recursos en que se ha de buscar información de asignación y metadatos. A continuación se muestra un ejemplo:<br /><br /> `Metadata=`<br /><br /> `c:\model &#124; c:\model\sql\mapping.msl;`<br /><br /> Los espacios en blanco a cada lado del separador de barra vertical se pasan por alto.<br /><br /> Esta palabra clave y la palabra clave `Name` se excluyen mutuamente.|
|`Name`|La aplicación puede especificar, si se desea, el nombre de conexión en un archivo de configuración de la aplicación que proporcione los valores de cadena de conexión con pares palabra clave-valor necesarios. En este caso, no es posible suministrarlos directamente en la cadena de conexión. La palabra clave `Name` no se permite en un archivo de configuración.<br /><br /> Cuando la palabra clave `Name` no se incluye en la cadena de conexión, se requiere un valor no vacío para la palabra clave Provider.<br /><br /> Esta palabra clave y todas las demás palabras clave de cadena de conexión se excluyen mutuamente.|

El siguiente es un ejemplo de una cadena de conexión para el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) almacenado en el archivo de configuración de la aplicación:

## <a name="model-and-mapping-file-locations"></a>Ubicaciones de los archivos del modelo y de asignación

El parámetro `Metadata` contiene una lista de ubicaciones en las que el proveedor `EntityClient` busca los archivos del modelo y de asignación. Los archivos del modelo y de asignación se suelen implementar en el mismo directorio que el archivo ejecutable de la aplicación. Estos archivos también se pueden implementar en una ubicación concreta o incluirse como un recurso incrustado en la aplicación.

Los recursos incrustados se especifican como sigue:

`Metadata=res://<assemblyFullName>/<resourceName>`

Las opciones siguientes están disponibles para definir la ubicación de un recurso incrustado:

|Opción|Descripción|
|-|-|
|`assemblyFullName`|Nombre completo de un ensamblado con el recurso incrustado. El nombre incluye el nombre sencillo, nombre de la versión, referencia cultural admitida y clave pública, como se indica a continuación:<br /><br /> `ResourceLib, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null`<br /><br /> Los recursos se pueden incrustar en cualquier ensamblado al que la aplicación pueda tener acceso.<br /><br /> Si especifica un carácter comodín ( \* ) para `assemblyFullName` , el tiempo de ejecución de Entity Framework buscará los recursos en las siguientes ubicaciones, en este orden:<br /><br /> 1. el ensamblado que realiza la llamada.<br />2. los ensamblados a los que se hace referencia.<br />3. los ensamblados del directorio bin de una aplicación.<br /><br /> Si los archivos no están en ninguna de estas ubicaciones, se lanzará una excepción. **Nota:**  Cuando se usa el carácter comodín (*), el Entity Framework tiene que buscar en todos los ensamblados los recursos con el nombre correcto. Para mejorar el rendimiento, especifique el nombre de ensamblado en lugar del carácter comodín.|
|`resourceName`|Nombre del recurso incluido, como AdventureWorksModel. CSDL. Los servicios de metadatos sólo buscarán los archivos o recursos con una de las extensiones siguientes: .csdl, .ssdl o .msl. Si no se especifica `resourceName`, se cargarán todos los recursos de metadatos. Los recursos deberían tener nombres únicos dentro de un ensamblado. Si varios archivos con el mismo nombre se definen en directorios diferentes en el ensamblado, la información de `resourceName` debe incluir la estructura de carpetas antes del nombre del recurso, por ejemplo nombreDeCarpeta.nombreDeArchivo.csdl.<br /><br /> `resourceName` no se requiere al especificar un carácter comodín (*) para `assemblyFullName`.|

> [!NOTE]
> Para mejorar el rendimiento, incruste los recursos en el ensamblado que realiza la llamada, excepto en escenarios sin web donde no haya ninguna referencia a los archivos de metadatos y asignaciones subyacentes en el ensamblado que realiza la llamada.

En el ejemplo siguiente se cargan todos los archivos del modelo y de asignación en el ensamblado que realiza la llamada, ensamblados a los que se hace referencia y otros ensamblados en el directorio bin de una aplicación.

```csharp
Metadata=res://*/
```

El ejemplo siguiente carga el archivo model.csdl del ensamblado AdventureWorks y carga los archivos model.ssdl y model.msl desde el directorio predeterminado de la aplicación en ejecución.

```csharp
Metadata=res://AdventureWorks, 1.0.0.0, neutral, a14f3033def15840/model.csdl|model.ssdl|model.msl
```

En el ejemplo siguiente se cargan los tres recursos especificados del ensamblado concreto.

```csharp
Metadata=res://AdventureWorks, 1.0.0.0, neutral, a14f3033def15840/model.csdl|
res://AdventureWorks, 1.0.0.0, neutral, a14f3033def15840/model.ssdl|
res://AdventureWorks, 1.0.0.0, neutral, a14f3033def15840/model.msl
```

En el ejemplo siguiente se cargan todos los recursos incrustados con las extensiones .csdl, .msl y .ssdl del ensamblado.

```csharp
Metadata=res://AdventureWorks, 1.0.0.0, neutral, a14f3033def15840/
```

En el ejemplo siguiente se cargan todos los recursos de la ruta de acceso relativa al archivo más "datadir\metadata \\ " desde la ubicación de ensamblado cargada.

```csharp
Metadata=datadir\metadata\
```

En el ejemplo siguiente se cargan todos los recursos en la ruta de acceso del archivo relativa desde la ubicación de ensamblado cargada.

```csharp
Metadata=.\
```

## <a name="support-for-the-124datadirectory124-substitution-string-and-the-web-application-root-operator-"></a>Compatibilidad con la cadena de sustitución &#124;&#124; de DataDirectory y el operador raíz de la aplicación web (~)

`DataDirectory`y el operador ~ se utilizan en <xref:System.Data.EntityClient.EntityConnection.ConnectionString%2A> como parte de las `Metadata` `Provider Connection String` palabras clave y. El elemento <xref:System.Data.EntityClient.EntityConnection> reenvía `DataDirectory` y el operador ~ a <xref:System.Data.Metadata.Edm.MetadataWorkspace> y al proveedor de almacenamiento, respectivamente.

|Término|Descripción|
|----------|-----------------|
|`&#124;DataDirectory&#124;`|Se resuelve como una ruta de acceso relativa a archivos de metadatos y una asignación. Se trata del valor que se establece a través del método `AppDomain.SetData("DataDirectory", objValue)`. La `DataDirectory` cadena de sustitución debe estar rodeada por los caracteres de barra vertical y no puede haber ningún espacio en blanco entre su nombre y los caracteres de barra vertical. El nombre de `DataDirectory` no distingue entre mayúsculas y minúsculas.<br /><br /> Si un directorio físico denominado "DataDirectory" tiene que pasarse como miembro de la lista de rutas de acceso de metadatos, agregue espacios en blanco a uno de los dos lados del nombre o a ambos. Por ejemplo: `Metadata="DataDirectory1 &#124; DataDirectory &#124; DataDirectory2"`. Una aplicación ASP.NET resuelve &#124;&#124; de DataDirectory en la \<application root> carpeta "/App_Data".|
|~|Se resuelve como la raíz de la aplicación web. El carácter ~ en una posición inicial siempre se interpreta como el operador raíz de la aplicación web (~), aunque podría representar un subdirectorio local válido. Para hacer referencia a este tipo de subdirectorio local, el usuario debería pasar `./~` explícitamente.|

`DataDirectory` y el operador ~ solo se deberían especificar al principio de una ruta de acceso; no se resuelven en ninguna otra posición. Entity Framework intentará resolver `~/data`, pero tratará `/data/~` como una ruta de acceso física.

Una ruta de acceso que comience con  `DataDirectory` o con el operador ~ no se puede resolver como una ruta de acceso física fuera de la rama de `DataDirectory` y el operador ~. Por ejemplo, las rutas de acceso siguientes se resolverán: `~`, `~/data`, `~/bin/Model/SqlServer`. Las rutas de acceso siguientes no se resolverán: `~/..`, `~/../other`.

`DataDirectory` y el operador ~ se puede extender para incluir los subdirectorios, de la forma siguiente: `|DataDirectory|\Model`, `~/bin/Model`

La resolución de la cadena de sustitución `DataDirectory` y el operador ~ no es recursiva. Por ejemplo, cuando `DataDirectory` incluye el carácter `~`, se lanza una excepción. De esta forma se evita una recursividad infinita.

## <a name="see-also"></a>Consulte también

- [Trabajar con proveedores de datos](working-with-data-providers.md)
- [Consideraciones de implementación](deployment-considerations.md)
- [Administrar conexiones y transacciones](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896325(v=vs.100))
- [Cadenas de conexión](../connection-strings.md)
