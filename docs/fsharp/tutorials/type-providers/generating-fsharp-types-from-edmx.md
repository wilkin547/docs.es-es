---
title: 'Tutorial: Generar tipos en F# a partir de un archivo de esquema EDMX (F#)'
description: "Obtenga información acerca de cómo crear tipos de F # para los datos representados por Entity Data Model (EDM) en F # 3.0, donde se especifica el esquema en un archivo .edmx."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 81adb2eb-625f-4ad8-aeaa-8f672a6d79a2
ms.openlocfilehash: 5c59911f5f880493080ef1838bc015045ce4336a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-generating-f-types-from-an-edmx-schema-file"></a>Tutorial: Generar tipos en F# a partir de un archivo de esquema EDMX

> [!NOTE]
Esta guía se escribió para F # 3.0 y se actualizará.  Vea [FSharp.Data](http://fsharp.github.io/FSharp.Data/) para obtener información sobre los proveedores de tipos multiplataforma actualizados.

> [!NOTE]
Los vínculos de referencia de API le llevará a MSDN.  La referencia de API de docs.microsoft.com no está completa.

En este tutorial sobre F# 3.0 se muestra cómo crear tipos para los datos representados por el Entity Data Model (EDM), cuyo esquema se especifica en un archivo .edmx. En el tutorial también se muestra cómo usar el proveedor de tipo EdmxFile. Antes de comenzar, considere si un proveedor de tipo SqlEntityConnection sería una opción más adecuada. El proveedor de tipo SqlEntityConnection funciona mejor en escenarios en los que se tiene una base de datos activa a la que se puede conectar en la fase de desarrollo del proyecto y cuando no es ningún problema especificar la cadena de conexión en tiempo de compilación. Sin embargo, este proveedor de tipo también está limitado por el hecho de que no expone tanta funcionalidad de base de datos como el proveedor EdmxFile. Además, si no se tiene una conexión de base de datos activa para un proyecto de base de datos que usa Entity Data Model, se puede utilizar el archivo .edmx para codificar en la base de datos. Cuando se usa el proveedor de tipo EdmxFile, el compilador de F# ejecuta EdmGen.exe para generar los tipos que proporciona.

En este tutorial se muestran las tareas siguientes, que se deben realizar en el orden presentado a continuación para finalizarlo correctamente:


- Crear un archivo EDMX
<br />

- Crear el proyecto
<br />

- Buscar o crear la cadena de conexión de Entity Data Model
<br />

- Configurar el proveedor de tipos
<br />

- Consultar los datos
<br />

- Llamar a un procedimiento almacenado
<br />


## <a name="prerequisites"></a>Requisitos previos

## <a name="creating-an-edmx-file"></a>Crear un archivo EDMX
Si ya tiene un archivo EDMX, puede omitir este paso.


#### <a name="to-create-an-edmx-file"></a>Para crear un archivo EDMX

- Si ya no tiene un archivo EDMX, puede seguir las instrucciones que aparecen al final de este tutorial en el paso [configurar el Entity Data Model](generating-fsharp-types-from-edmx.md#configuring-the-entity-data-model).
<br />

## <a name="creating-the-project"></a>Crear el proyecto
En este paso, se creará un proyecto y se agregarán las referencias adecuadas al mismo para usar el proveedor de tipo EDMX.


#### <a name="to-create-and-set-up-an-f-project"></a>Para crear y configurar un proyecto de F#

1. Cierre el proyecto anterior, cree otro proyecto y denomínelo SchoolEDM.
<br />

2. En **el Explorador de soluciones**, abra el menú contextual para **referencias**y, a continuación, elija **Agregar referencia**.
<br />

3. En el **ensamblados** área, elija la **Framework** nodo.
<br />

4. En la lista de ensamblados disponibles, elija la **System.Data.Entity** y **System.Data.Linq** ensamblados y, a continuación, elija la **agregar** botón para agregar referencias a estas ensamblados al proyecto.
<br />

5. En el **ensamblados** área, seleccione la **extensiones** nodo.
<br />

6. En la lista de extensiones disponibles, agregue una referencia al ensamblado FSharp.Data.TypeProviders.
<br />

7. Agregue el código siguiente para abrir los espacios de nombres adecuados.
<br />

```fsharp
open System.Data.Linq
open System.Data.Entity
open Microsoft.FSharp.Data.TypeProviders
```

## <a name="finding-or-creating-the-connection-string-for-the-entity-data-model"></a>Buscar o crear la cadena de conexión para Entity Data Model
La cadena de conexión de Entity Data Model (cadena de conexión EDMX) incluye no solo la cadena de conexión para el proveedor de base de datos, sino también información adicional. Por ejemplo, la cadena de conexión EDMX para una base de datos de SQL Server simple se asemeja al código siguiente.

```fsharp
let edmConnectionString = "metadata=res://*/;provider=System.Data.SqlClient;Provider Connection String='Server=SERVER\Instance;Initial Catalog=DatabaseName;Integrated Security=SSPI;'"
```

Para obtener más información acerca de las cadenas de conexión EDMX, consulte [las cadenas de conexión](https://msdn.microsoft.com/library/ms254494.aspx).


#### <a name="to-find-or-create-the-connection-string-for-the-entity-data-model"></a>Para buscar o crear la cadena de conexión para el Entity Data Model

1. Las cadenas de conexión EDMX pueden ser difíciles de generar manualmente, por lo que se puede ahorrar tiempo si se generan mediante programación. Si conoce la cadena de conexión EDMX, puede omitir este paso y simplemente usar dicha cadena en el paso siguiente. En caso contrario, use el código que aparece a continuación para generar la cadena de conexión EDMX a partir de una cadena de conexión de base de datos que usted mismo proporcione.
<br />

```fsharp
open System
open System.Data
open System.Data.SqlClient
open System.Data.EntityClient
open System.Data.Metadata.Edm

let getEDMConnection(dbConnectionString) =
  let dbConnection = new SqlConnection(dbConnectionString)
  let resourceArray = [| "res://*/" |]
  let assemblyList = [| System.Reflection.Assembly.GetCallingAssembly() |]
  let metaData = MetadataWorkspace(resourceArray, assemblyList)
  new EntityConnection(metaData, dbConnection)
```

## <a name="configuring-the-type-provider"></a>Configurar el proveedor de tipo
En este paso se creará y configurará el proveedor de tipo con la cadena de conexión EDMX y se generarán los tipos para el esquema que se define en el archivo .edmx.


#### <a name="to-configure-the-type-provider-and-generate-types"></a>Para configurar el proveedor de tipo y generar tipos

1. Copie el archivo .edmx generado en el primer paso de este tutorial en la carpeta del proyecto.
<br />

2. Abra el menú contextual para el nodo del proyecto en el proyecto de F #, elija **Agregar elemento existente**y, a continuación, elija el archivo .edmx para agregarlo al proyecto.
<br />

3. Escriba el siguiente código para activar el proveedor de tipo del archivo .edmx. Reemplace *Server*\*instancia * con el nombre del servidor que ejecuta SQL Server y el nombre de la instancia y utilizar el nombre del archivo .edmx desde el primer paso en este tutorial.
<br />

```fsharp
type edmx = EdmxFile<"Model1.edmx", ResolutionFolder = @"<path-tofolder-that-containsyour.edmx-file>">

use edmConnection =
  getEDMConnection("Data Source=SERVER\instance;Initial Catalog=School;Integrated Security=true;")
use context = new edmx.SchoolModel.SchoolEntities(edmConnection)
```

## <a name="querying-the-data"></a>Consultar los datos
En este paso, se usan las expresiones de consulta de F# para consultar la base de datos.


#### <a name="to-query-the-data"></a>Para consultar los datos

- Escriba el código siguiente para consultar los datos en el Entity Data Model.
<br />

```fsharp
query { 
  for course in context.Courses do
  select course 
} |> Seq.iter (fun course -> printfn "%s" course.Title)

query { 
  for person in context.Person do
  select person 
} |> Seq.iter (fun person -> printfn "%s %s" person.FirstName person.LastName)

// Add a where clause to filter results
query { 
  for course in context.Courses do
  where (course.DepartmentID = 1)
  select course
} |> Seq.iter (fun course -> printfn "%s" course.Title)

// Join two tables
query { 
  for course in context.Courses do
  join dept in context.Departments on (course.DepartmentID = dept.DepartmentID)
  select (course, dept.Name) 
} |> Seq.iter (fun (course, deptName) -> printfn "%s %s" course.Title deptName)
```

## <a name="calling-a-stored-procedure"></a>Llamar a un procedimiento almacenado
Se puede llamar a los procedimientos almacenados mediante el proveedor de tipos EDMX. En el siguiente procedimiento, la base de datos School contiene un procedimiento almacenado, **UpdatePerson**, que actualiza un registro, dados los nuevos valores para las columnas. Este procedimiento almacenado se puede usar porque se expone como método en el tipo DataContext.


#### <a name="to-call-a-stored-procedure"></a>Para llamar a un procedimiento almacenado

- Agregue el código siguiente para actualizar los registros:
<br />

```fsharp
// Call a stored procedure.
let nullable value = new System.Nullable<_>(value)

// Assume now that you must correct someone's hire date.
// Throw an exception if more than one matching person is found.
let changeHireDate(lastName, firstName, hireDate) =

  query { 
    for person in context.People do
    where (person.LastName = lastName &&
           person.FirstName = firstName)
    exactlyOne 
  } |> (fun person ->
            context.UpdatePerson(nullable person.PersonID, person.LastName, person.FirstName, nullable hireDate, person.EnrollmentDate))

changeHireDate("Abercrombie", "Kim", DateTime.Parse("1/12/1998"))
|> printfn "Result: %d"
```

Si la acción se realiza correctamente, el resultado es 1. Tenga en cuenta que **exactlyOne** se utiliza en la expresión de consulta para asegurarse de que solo un resultado se devuelve; en caso contrario, se produce una excepción. Además, para trabajar más fácilmente con valores que aceptan valores NULL, puede utilizar los más sencillos **que aceptan valores NULL** función que se define en este código para crear un valor que aceptan valores NULL fuera de un valor normal.

<br />

## <a name="configuring-the-entity-data-model"></a>Configurar el Entity Data Model
Solo debe completar este procedimiento si desea aprender a generar un Entity Data Model completo a partir de una base de datos y no tiene una base de datos para probar.


#### <a name="to-configure-the-entity-data-model"></a>Para configurar el Entity Data Model

1. En la barra de menús, elija **SQL**, **Editor de Transact-SQL**, **nueva consulta** para crear una base de datos. Si se le solicita, especifique el servidor de bases de datos y la instancia.
<br />

2. Copie y pegue el contenido de la secuencia de comandos de base de datos que crea la base de datos de estudiantes, como se describe en el [documentación de Entity Framework](http://msdn.microsoft.com/data/JJ614587.aspx) en el Centro para desarrolladores de datos.
<br />

3. Ejecute el script SQL eligiendo el botón de barra de herramientas con el símbolo del triángulo o las teclas Ctrl + Q.
<br />

4. En **Explorador de servidores**, abra el menú contextual para **las conexiones de datos**, elija **Agregar conexión**y, a continuación, escriba el nombre del servidor de base de datos, el nombre de la instancia y la base de datos School.
<br />

5. Crear un proyecto de aplicación de consola de Visual Basic o C#, abra el menú contextual, elija **Agregar nuevo elemento**y, a continuación, elija **ADO.NET Entity Data Model**.
<br />  Se abre el Asistente para Entity Data Model. Mediante este asistente, se puede elegir cómo crear un Entity Data Model.
<br />

6. En **Elegir contenido del modelo**, seleccione la **generar desde la base de datos** casilla de verificación.
<br />

7. En la página siguiente, elija la base de datos School que acaba de crear como conexión de datos.
<br />  Debe ser similar esta conexión  **&lt;servername&gt;.&lt; nombreDeInstancia&gt;. School.dbo**.
<br />

8. Copie la cadena de conexión de la entidad en el Portapapeles, ya que puede ser importante más adelante.
<br />

9. Asegúrese de que la casilla de verificación para guardar la cadena de conexión de entidad para el **App.Config** archivo está seleccionada y tome nota del valor de cadena en el cuadro de texto, que le ayudarán a encontrar la cadena de conexión más adelante, si es necesario.
<br />

10. En la página siguiente, elija **tablas** y **procedimientos almacenados y funciones**.
<br />  Al elegir estos nodos de nivel superior, se eligen todas las tablas, procedimientos almacenados y funciones. También se pueden seleccionar individualmente, si se desea.
<br />

11. Asegúrese de que las casillas del resto de valores estén activadas.
<br />  La primera **poner en plural o en singular los nombres de objeto generados** casilla de verificación indica si se debe cambiar formas de singular a plural para hacer coincidir las convenciones de nomenclatura de objetos que representan tablas de base de datos. El **incluir columnas de clave externa en el modelo** casilla de verificación determina si se debe incluir los campos para los que el propósito es combinarse con otros campos en los tipos de objeto que se generan para el esquema de base de datos. La tercera casilla indica si se deben incluir las funciones y los procedimientos almacenados en el modelo.
<br />

12. Seleccione el **finalizar** botón para generar un archivo .edmx que contenga un Entity Data Model que se basa en la base de datos School.
<br />  Un archivo, **Model1.edmx**, se agrega al proyecto, y aparece un diagrama de base de datos.
<br />

13. En la barra de menús, elija **vista**, **otras ventanas**, **Examinador de modelos de datos de entidad** para ver todos los detalles del modelo o **detalles de la asignación de entidad de datos modelo**  para abrir una ventana que muestra cómo se asigna el modelo de objetos generado en tablas de base de datos y columnas.
<br />


## <a name="next-steps"></a>Pasos siguientes
Explorar otras consultas examinando los operadores de consulta disponibles como se muestra en [expresiones de consulta](../../language-reference/query-expressions.md).


## <a name="see-also"></a>Vea también
[Proveedores de tipos](index.md)

[Proveedor de tipos EdmxFile](https://msdn.microsoft.com/visualfsharpdocs/conceptual/edmxfile-type-provider-%5bfsharp%5d)

[Tutorial: Acceso a una base de datos SQL mediante proveedores de tipo y entidades](accessing-a-sql-database-entities.md)

[Entity Framework](http://msdn.microsoft.com/data/ef)

[información general de archivo .edmx](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)

[Generador de EDM &#40; EdmGen.exe &#41;](https://msdn.microsoft.com/library/bb387165)

