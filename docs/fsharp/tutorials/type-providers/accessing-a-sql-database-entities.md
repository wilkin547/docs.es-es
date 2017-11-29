---
title: 'Tutorial: Obtener acceso a una base de datos SQL mediante proveedores de tipo y entidades (F#)'
description: "Obtenga información acerca de cómo obtener acceso a datos con tipo para una base de datos SQL basado en ADO.NET Entity Data Model en F # 3.0."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: dc82a932-5401-4d19-9fb3-92c50d8db514
ms.openlocfilehash: 770d405921758eeb7e8d7ea98b95c29c99631475
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-accessing-a-sql-database-by-using-type-providers-and-entities"></a>Tutorial: Obtener acceso a una base de datos SQL mediante proveedores de tipo y entidades

> [!NOTE]
Esta guía se escribió para F # 3.0 y se actualizará.  Vea [FSharp.Data](http://fsharp.github.io/FSharp.Data/) para obtener información sobre los proveedores de tipos multiplataforma actualizados.

> [!NOTE]
Los vínculos de referencia de API le llevará a MSDN.  La referencia de API de docs.microsoft.com no está completa.

Este tutorial sobre F# 3.0 muestra cómo obtener acceso a los datos con tipo para una base de datos SQL basándose en el Entity Data Model de ADO.NET. En el tutorial se muestra cómo configurar el proveedor de tipo de F# `SqlEntityConnection` para usarlo con una base de datos SQL, cómo escribir consultas en los datos, cómo llamar a procedimientos almacenados en la base de datos y cómo usar algunos de los tipos y métodos de ADO.NET Entity Framework para actualizar la base de datos.

Este tutorial muestra las tareas siguientes, que se deben realizar en el orden presentado a continuación para finalizarlo correctamente:


- Crear la base de datos School
<br />

- Crear y configurar un proyecto de F#
<br />

- Configurar el proveedor de tipos y conectarse al Entity Data Model
<br />

- Consulta la base de datos
<br />

- Actualizar la base de datos
<br />


## <a name="prerequisites"></a>Requisitos previos
Para completar estos pasos, se debe tener acceso a un servidor que ejecute SQL Server donde se pueda crear una base de datos.

## <a name="create-the-school-database"></a>Crear la base de datos School
Se puede crear la base de datos School en cualquier servidor que ejecute SQL Server en el que tenga acceso administrativo o se puede usar LocalDB.


#### <a name="to-create-the-school-database"></a>Para crear la base de datos School

1. En **Explorador de servidores**, abra el menú contextual para el **las conexiones de datos** nodo y, a continuación, elija **Agregar conexión**.
<br />  El **Agregar conexión** aparece el cuadro de diálogo.
<br />

2. En el **nombre del servidor** cuadro, especifique el nombre de una instancia de SQL Server a la que tenga acceso administrativo o especificar (localdb\v11.0) si no tiene acceso a un servidor.
<br />  LocalDB de SQL Server Express proporciona un servidor de bases de datos ligero para el desarrollo y las pruebas en el equipo. Para obtener más información acerca de LocalDB, vea [Tutorial: crear un archivo de base de datos Local en Visual Studio](https://msdn.microsoft.com/library/ms233763.aspx).
<br />  Se crea un nuevo nodo en **Explorador de servidores** en **las conexiones de datos**.
<br />

3. Abra el menú contextual para el nuevo nodo de conexión y, a continuación, elija **nueva consulta**.
<br />

4. Abra [crear la base de datos de ejemplo School](http://go.microsoft.com/fwlink/?LinkID=237278) en el sitio Web de Microsoft y, a continuación, copiar y pegar el script de base de datos que crea la base de datos de estudiante en la ventana del editor.
<br />


## <a name="BKMK_CreateConfigFSProj"> </a>

## <a name="create-and-configure-an-f-project"></a>Crear y configurar un proyecto de F#
En este paso, se crea un proyecto y se configura para usar un proveedor de tipo.


#### <a name="to-create-and-configure-an-f-project"></a>Para crear y configurar un proyecto de F#

1. Cierre el proyecto anterior, cree otro proyecto y asígnele el nombre **SchoolEDM**.
<br />

2. En **el Explorador de soluciones**, abra el menú contextual para **referencias**y, a continuación, elija **Agregar referencia**.
<br />

3. Elija la **Framework** nodo y, a continuación, en la **Framework** elija **System.Data**, **System.Data.Entity**y **System.Data.Linq**.
<br />

4. Elija la **extensiones** nodo, agregue una referencia a la [FSharp.Data.TypeProviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3) ensamblado y, a continuación, elija la **Aceptar** botón para descartar el cuadro de diálogo.
<br />

5. Agregue el código siguiente para definir un módulo interno y abrir los espacios de nombres adecuados. El proveedor de tipos solo puede insertar tipos en un espacio de nombres privado o interno.
<br />

```fsharp
module internal SchoolEDM

open System.Data.Linq
open System.Data.Entity
open Microsoft.FSharp.Data.TypeProviders
```

6. Para ejecutar el código de este tutorial de forma interactiva como una secuencia de comandos en lugar de como programa compilado, abra el menú contextual del nodo de proyecto, elija **Agregar nuevo elemento**, agregue un archivo de script de F # y, a continuación, agregue el código de cada paso al script. Para cargar las referencias de ensamblado, agregue las líneas siguientes.
<br />

```fsharp
#r "System.Data.Entity.dll"
#r "FSharp.Data.TypeProviders.dll"
#r "System.Data.Linq.dll"
```

7. Resalte cada bloque de código al agregarlo y presione las teclas Alt + Intro para ejecutarlo en F# interactivo.
<br />

## <a name="configure-the-type-provider-and-connect-to-the-entity-data-model"></a>Configurar el proveedor de tipo y conectarse al Entity Data Model
En este paso, se configura un proveedor de tipo con una conexión de datos y se obtiene un contexto de datos que permite trabajar con los datos.


#### <a name="to-configure-the-type-provider-and-connect-to-the-entity-data-model"></a>Para configurar el proveedor de tipo y conectarse al Entity Data Model

1. Escriba el código siguiente para configurar el proveedor de tipo `SqlEntityConnection` que genera tipos de F# basados en el Entity Data Model creado previamente. En lugar de la cadena de conexión de EDMX completa, use solo la cadena de conexión de SQL.
<br />

```fsharp
type private EntityConnection = SqlEntityConnection<ConnectionString="Server=SERVER\InstanceName;Initial Catalog=School;Integrated Security=SSPI;MultipleActiveResultSets=true",Pluralize = true>
```

  Esta acción configura un proveedor de tipo con la conexión de base de datos que se ha creado anteriormente. La propiedad `MultipleActiveResultSets` es necesaria cuando se usa ADO.NET Entity Framework porque permite que varios comandos se ejecuten de forma asincrónica en la base de datos en una conexión, lo que puede producirse con frecuencia en el código de ADO.NET Entity Framework. Para obtener más información, consulte [Conjuntos de resultados activos múltiples (MARS)](/sql/relational-databases/native-client/features/using-multiple-active-result-sets-mars).
<br />

2. Obtenga el contexto de datos, que es un objeto que contiene las tablas de base de datos como propiedades y los procedimientos almacenados y funciones de base de datos como métodos.
<br />

```fsharp
let context = EntityConnection.GetDataContext()
```

## <a name="querying-the-database"></a>Consultar la base de datos
En este paso, se usan las expresiones de consulta de F# para ejecutar varias consultas en la base de datos.


#### <a name="to-query-the-data"></a>Para consultar los datos

- Escriba el código siguiente para consultar los datos del Entity Data Model. Tenga en cuenta el efecto de Pluralize = true, que cambia Course a Courses y Person a People en la tabla de base de datos.
<br />

```fsharp
query { 
  for course in context.Courses do
  select course
} |> Seq.iter (fun course -> printfn "%s" course.Title)

query { 
  for person in context.People do
  select person 
} |> Seq.iter (fun person -> printfn "%s %s" person.FirstName person.LastName)

// Add a where clause to filter results.
query {
  for course in context.Courses do
  where (course.DepartmentID = 1)
  select course
} |> Seq.iter (fun course -> printfn "%s" course.Title)

// Join two tables.
query { 
  for course in context.Courses do
  join dept in context.Departments on (course.DepartmentID = dept.DepartmentID)
  select (course, dept.Name) 
} |> Seq.iter (fun (course, deptName) -> printfn "%s %s" course.Title deptName)
```

## <a name="updating-the-database"></a>Actualizar la base de datos
Para actualizar la base de datos, se usan las clases y los métodos de Entity Framework. Se pueden usar dos tipos de contexto de datos con el proveedor de tipo SQLEntityConnection. En primer lugar, `ServiceTypes.SimpleDataContextTypes.EntityContainer` es el contexto de datos simplificado, que incluye solamente las propiedades proporcionadas que representan tablas y columnas de bases de datos. En segundo lugar, el contexto de datos completo es una instancia de la clase `System.Data.Objects.ObjectContext`de Entity Framework, que contiene el método `System.Data.Objects.ObjectContext.AddObject(System.String,System.Object)` para agregar filas a la base de datos. Entity Framework reconoce las tablas y las relaciones entre ellas, por lo que refuerza la coherencia de la base de datos.


#### <a name="to-update-the-database"></a>Para actualizar la base de datos

1. Agregue el código siguiente al programa. En este ejemplo, se agregan dos objetos con una relación entre ellos y se agrega un instructor y una asignación de oficina. La tabla `OfficeAssignments` contiene la columna `InstructorID`, que hace referencia a la columna `PersonID` de la tabla `Person`.
<br />

```fsharp
// The full data context
let fullContext = context.DataContext

// A helper function.
let nullable value = new System.Nullable<_>(value)

let addInstructor(lastName, firstName, hireDate, office) =
  let hireDate = DateTime.Parse(hireDate)
  let newPerson = new EntityConnection.ServiceTypes.Person(LastName = lastName,
                                                           FirstName = firstName,
                                                           HireDate = nullable hireDate)
  fullContext.AddObject("People", newPerson)

  let newOffice = new EntityConnection.ServiceTypes.OfficeAssignment(Location = office)

  fullContext.AddObject("OfficeAssignments", newOffice)
  fullContext.CommandTimeout <- nullable 1000
  fullContext.SaveChanges() |> printfn "Saved changes: %d object(s) modified."

addInstructor("Parker", "Darren", "1/1/1998", "41/3720")
```

Nada cambia en la base de datos hasta que se llame a `System.Data.Objects.ObjectContext.SaveChanges`.
<br />

2. Ahora, restaure la base de datos a su estado anterior eliminando los objetos que agregó.
<br />

```fsharp
let deleteInstructor(lastName, firstName) =
  query {
    for person in context.People do
    where (person.FirstName = firstName &&
           person.LastName = lastName)
    select person
  } |> Seq.iter (fun person->
                    query {
                      for officeAssignment in context.OfficeAssignments do
                      where (officeAssignment.Person.PersonID = person.PersonID)
                      select officeAssignment
                    } |> Seq.iter (fun officeAssignment -> fullContext.DeleteObject(officeAssignment))

                    fullContext.DeleteObject(person))

  // The call to SaveChanges should be outside of any iteration on the queries.
  fullContext.SaveChanges() |> printfn "Saved changed: %d object(s) modified."

deleteInstructor("Parker", "Darren")
```

>[!WARNING] 
Cuando se usa una expresión de consulta, debe recordar que la consulta está sujeta a la evaluación diferida. Por tanto, la base de datos sigue abierta para lectura durante cualquier evaluación encadenada, por ejemplo en los bloques de expresiones lambda después de cada expresión de consulta. Cualquier operación de base de datos que use una transacción implícita o explícitamente debe aparecer después de que las operaciones de lectura se hayan completado.


## <a name="next-steps"></a>Pasos siguientes
Explore otras opciones de consulta revisando los operadores de consulta disponibles en [expresiones de consulta](../../language-reference/query-expressions.md)y también de revisar la [ADO.NET Entity Framework](https://msdn.microsoft.com/library/bb399572) para comprender qué funcionalidad está disponible para usted cuando Utilice este proveedor de tipo.


## <a name="see-also"></a>Vea también
[Proveedores de tipos](index.md)

[Proveedor de tipos SqlEntityConnection](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqlentityconnection-type-provider-%5bfsharp%5d)

[Tutorial: Generar tipos de F # en un archivo de esquema EDMX](generating-fsharp-types-from-edmx.md)

[ADO.NET Entity Framework](https://msdn.microsoft.com/library/bb399572)

[información general de archivo .edmx](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)

[Generador de EDM &#40; EdmGen.exe &#41;](https://msdn.microsoft.com/library/bb387165)
