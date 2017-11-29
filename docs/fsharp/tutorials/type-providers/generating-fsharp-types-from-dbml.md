---
title: 'Tutorial: Generar tipos en F# a partir de un archivo DBML (F#)'
description: "Obtenga información acerca de cómo crear tipos de F # para los datos de una base de datos en F # 3.0 cuando tenga información de esquema codificado en un archivo. dbml."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 6fbb6ccc-248f-4226-95e9-f6f99541dbe4
ms.openlocfilehash: 50e0a2bb6378c82b5c6425589da8a982b5fc496a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-generating-f-types-from-a-dbml-file"></a>Tutorial: Generar tipos en F# a partir de un archivo DBML

> [!NOTE]
Esta guía se escribió para F # 3.0 y se actualizará.  Vea [FSharp.Data](http://fsharp.github.io/FSharp.Data/) para obtener información sobre los proveedores de tipos multiplataforma actualizados.

> [!NOTE]
Los vínculos de referencia de API le llevará a MSDN.  La referencia de API de docs.microsoft.com no está completa.

En este tutorial sobre F # 3.0 se describe cómo crear tipos de datos desde una base de datos cuando se dispone de información de esquema codificado en un archivo. dbml. LINQ to SQL utiliza este formato de archivo para representar el esquema de base de datos. Puede generar un archivo LINQ to SQL esquema en Visual Studio mediante el Diseñador relacional de objetos (Object Relational). Para obtener más información, consulte [Object Relational Designer Overview](https://msdn.microsoft.com/library/bb384511.aspx) y [generación de código en LINQ to SQL](https://msdn.microsoft.com/library/bb386976).

El proveedor de tipo de lenguaje de marcado de base de datos (DBML) permite escribir código que utiliza tipos basados en un esquema de base de datos sin necesidad de especificar una cadena de conexión estática en tiempo de compilación. Que puede ser útil si necesita permitir la posibilidad de que la aplicación final va a usar una base de datos diferente, unas credenciales distintas o una cadena de conexión diferente que aquel que se utiliza para desarrollar la aplicación. Si tiene una conexión directa de la base de datos que puede usar en tiempo de compilación y se trata de la misma base de datos y las credenciales que finalmente utilizará en la aplicación integrada, también puede usar el proveedor de tipos SQLDataConnection. Para obtener más información, consulte [Tutorial: obtener acceso a una base de datos SQL mediante proveedores de tipo](accessing-a-sql-database.md).

En este tutorial se muestran las tareas siguientes. Se debe completar en el orden para el tutorial sea correcta:


- Crear un archivo .dbml
<br />

- Crear y configurar un proyecto de F #
<br />

- Configurar el proveedor de tipos y generar los tipos
<br />

- Consultar la base de datos
<br />


## <a name="prerequisites"></a>Requisitos previos

## <a name="creating-a-dbml-file"></a>Crear un archivo .dbml
Si no tiene que ejecutar pruebas en una base de datos, crear una siguiendo las instrucciones que aparecen en la parte inferior de [Tutorial: obtener acceso a una base de datos SQL mediante proveedores de tipo](accessing-a-sql-database.md). Si sigue estas instrucciones, creará una base de datos denominada MyDatabase que contiene algunas tablas simples y procedimientos almacenados en SQL Server.

Si ya tiene un archivo .dbml, puede ir a la sección, **crear y establecer seguridad de un proyecto de F #**. En caso contrario, puede crear un archivo .dbml que proporciona una base de datos SQL existente y mediante el uso de la línea de comandos, herramienta SqlMetal.exe.


#### <a name="to-create-a-dbml-file-by-using-sqlmetalexe"></a>Para crear un archivo .dbml mediante SqlMetal.exe

1. Abra un **símbolo**.
<br />

2. Asegúrese de que tiene acceso a SqlMetal.exe escribiendo `SqlMetal.exe /?` en el símbolo del sistema. SqlMetal.exe normalmente se instala en el **Microsoft SDKs** carpeta **archivos de programa** o **archivos de programa (x86)**.
<br />

3. Ejecute SqlMetal.exe con las siguientes opciones de línea de comandos. Sustituir una ruta de acceso adecuada en lugar de `c:\destpath` para crear el archivo .dbml e insertar los valores adecuados para el servidor de base de datos, nombre de instancia y el nombre de base de datos.
<br />

```
  SqlMetal.exe /sprocs /dbml:C:\destpath\MyDatabase.dbml /server:SERVER\INSTANCE /database:MyDatabase
```

>[!NOTE]
Si SqlMetal.exe tiene problemas para crear el archivo debido a problemas de permisos, cambie el directorio actual a una carpeta que tenga acceso de escritura a.


4. También puede mirar las demás opciones de línea de comandos disponibles. Por ejemplo, hay opciones que puede usar si desea que las vistas y las funciones SQL incluidas en los tipos generados. Para obtener más información, vea [SqlMetal.exe &#40; Herramienta de generación de código &#41; ](https://msdn.microsoft.com/library/bb386987).
<br />


## <a name="creating-and-setting-up-an-f-project"></a>Crear y configurar un proyecto de F #
En este paso, cree un proyecto y agregue las referencias adecuadas para usar el proveedor de tipo DBML.


#### <a name="to-create-and-set-up-an-f-project"></a>Para crear y configurar un proyecto de F#

1. Agregar un nuevo proyecto de aplicación de consola de F # a la solución.
<br />

2. En **el Explorador de soluciones**, abra el menú contextual para **referencias**y, a continuación, elija **Agregar referencia**.
<br />

3. En el **ensamblados** área, elija la **Framework** nodo y, a continuación, en la lista de ensamblados disponibles, elija la **System.Data** y **System.Data.Linq**  ensamblados.
<br />

4. En el **ensamblados** área, elija **extensiones**y, a continuación, en la lista de ensamblados disponibles, elija **FSharp.Data.TypeProviders**.
<br />

5. Elija la **Aceptar** botón para agregar referencias a estos ensamblados al proyecto.
<br />

6. (Opcional). Copie el archivo .dbml que creó en el paso anterior y pegue el archivo en la carpeta principal para el proyecto. Esta carpeta contiene los archivos de código y el archivo de proyecto (.fsproj). En la barra de menús, elija **proyecto**, **Agregar elemento existente**y, a continuación, especifique el archivo .dbml para agregarlo al proyecto. Si completa estos pasos, puede omitir el parámetro static ResolutionFolder en el paso siguiente.
<br />

## <a name="configuring-the-type-provider"></a>Configurar el proveedor de tipo
En esta sección, crear un proveedor de tipos y generar tipos a partir del esquema que se describe en el archivo .dbml.


#### <a name="to-configure-the-type-provider-and-generate-the-types"></a>Para configurar el proveedor de tipos y generar los tipos

- Agregue código que se abre la **TypeProviders** espacio de nombres y crea una instancia del proveedor de tipos para el archivo .dbml que desea utilizar. Si agrega el archivo .dbml a su proyecto, puede omitir el parámetro static ResolutionFolder.
<br />

```fsharp
open Microsoft.FSharp.Data.TypeProviders


type dbml = DbmlFile<"MyDatabase.dbml", ResolutionFolder = @"<path-to-folder-that-contains-.dbml-file>">

// This connection string can be specified at run time.
let connectionString = "Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;"
let dataContext = new dbml.Mydatabase(connectionString)
```

El tipo DataContext proporciona acceso a todos los tipos generados y hereda de `System.Data.Linq.DataContext`. El proveedor de tipos DbmlFile tiene varios parámetros estáticos que se pueden establecer. Por ejemplo, puede usar un nombre diferente para el tipo DataContext especificando `DataContext=MyDataContext`. En ese caso, el código es similar al siguiente:
<br />

```fsharp
open Microsoft.FSharp.Data.TypeProviders


type dbml = DbmlFile<"MyDatabase.dbml", ContextTypeName = "MyDataContext">

// This connection string can be specified at run time.
let connectionString = "Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;"
let db = new dbml.MyDataContext(connectionString)
```

## <a name="querying-the-database"></a>Consultar la base de datos
En esta sección, usa expresiones de consulta de F # para consultar la base de datos.


#### <a name="to-query-the-data"></a>Para consultar los datos

- Agregue código para consultar la base de datos.
<br />

```fsharp
  query {
    for row in db.Table1 do
    where (row.TestData1 > 2)
    select row
  } |> Seq.iter (fun row -> printfn "%d %s" row.TestData1 row.Name)
```

## <a name="next-steps"></a>Pasos siguientes
Puede continuar para utilizan otras expresiones de consulta, o realizar una conexión de base de datos desde el contexto de datos y realizar las operaciones normales de datos ADO.NET. Para conocer más pasos, vea las secciones después de "Consulta los datos" en [Tutorial: obtener acceso a una base de datos SQL mediante proveedores de tipo](accessing-a-sql-database.md).


## <a name="see-also"></a>Vea también
[Proveedor de tipos DbmlFile](https://msdn.microsoft.com/visualfsharpdocs/conceptual/dbmlfile-type-provider-%5bfsharp%5d)

[Proveedores de tipos](index.md)

[Tutorial: Acceso a una base de datos SQL mediante proveedores de tipos](accessing-a-sql-database.md)

[SqlMetal.exe &#40; Herramienta de generación de código &#41;](https://msdn.microsoft.com/library/bb386987)

[Expresiones de consulta](../../language-reference/query-expressions.md)
