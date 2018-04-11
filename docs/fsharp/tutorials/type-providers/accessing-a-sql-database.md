---
title: 'Tutorial: Obtener acceso a una base de datos SQL mediante proveedores de tipo (F#)'
description: "Obtenga información acerca de cómo usar el proveedor de tipos SqlDataConnection (LINQ to SQL) en F # 3.0 para generar tipos para una base de datos SQL cuando se dispone de una conexión de base de datos activa."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 1c413eb0-16a5-4c1a-9a4e-ad6877e645d6
ms.openlocfilehash: dbc5d889fb7883b4327180fdf34accf45bf519e7
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
---
# <a name="walkthrough-accessing-a-sql-database-by-using-type-providers"></a>Tutorial: Acceder a una base de datos SQL mediante proveedores de tipos

> [!NOTE]
Esta guía se escribió para F # 3.0 y se actualizará.  Vea [FSharp.Data](https://fsharp.github.io/FSharp.Data/) para obtener información sobre los proveedores de tipos multiplataforma actualizados.

> [!NOTE]
Los vínculos de referencia de API le llevará a MSDN.  La referencia de API de docs.microsoft.com no está completa.

En este tutorial se explica cómo usar el proveedor de tipos SqlDataConnection (LINQ to SQL) que está disponible en F # 3.0 para generar tipos de datos en una base de datos SQL cuando tenga una conexión activa a una base de datos. Si no tiene una conexión activa a una base de datos, pero tiene una LINQ al archivo de esquema SQL (archivo DBML), consulte [Tutorial: generar tipos en F # desde un archivo DBML](generating-fsharp-types-from-dbml.md).

En este tutorial se muestran las tareas siguientes. Estas tareas se deben realizar en el orden para el tutorial sea correcta:


- Preparar una base de datos de prueba

- Crear el proyecto

- Cómo configurar un proveedor de tipos

- Consultar los datos

- Trabajar con campos que aceptan valores null

- Llamar a un procedimiento almacenado

- Actualizar la base de datos

- Ejecutar código de Transact-SQL

- Utilizando el contexto de datos completa

- Eliminar datos

- Crear una base de datos de prueba (según sea necesario)

## <a name="preparing-a-test-database"></a>Preparar una base de datos de prueba
En un servidor que ejecuta SQL Server, cree una base de datos con fines de prueba. Puede usar la base de datos crear secuencia de comandos en la parte inferior de esta página en la sección [crear una base de datos de prueba](#creating-a-test-database) hacerlo.


#### <a name="to-prepare-a-test-database"></a>Para preparar una base de datos de prueba

Para ejecutar el Script de creación de MyDatabase, abra el **vista** menú y, a continuación, elija **Explorador de objetos de SQL Server** o elija la tecla Ctrl +\, claves CTRL+s. En **Explorador de objetos de SQL Server** ventana, abra el menú contextual de la instancia adecuada, elija **nueva consulta**, copie el script en la parte inferior de esta página y, a continuación, pegue la secuencia de comandos en el editor. Para ejecutar el script SQL, elija el icono de la barra de herramientas con el símbolo del triángulo o elija las teclas Ctrl + Q. Para obtener más información acerca de **Explorador de objetos de SQL Server**, consulte [desarrollo de base de datos conectadas](https://msdn.microsoft.com/library/hh272679(VS.103).aspx).


## <a name="creating-the-project"></a>Crear el proyecto
A continuación, cree un proyecto de aplicación de F #.


#### <a name="to-create-and-set-up-the-project"></a>Para crear y configurar el proyecto

1. Cree un nuevo proyecto de aplicación de F #.

2. Agregue referencias a [FSharp.Data.TypeProviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3), así como `System.Data`, y `System.Data.Linq`.

3. Abra los espacios de nombres adecuado mediante la adición de las siguientes líneas de código a la parte superior de su archivo de código de F # Program.fs.

  ```fsharp
open System
open System.Data
open System.Data.Linq
open Microsoft.FSharp.Data.TypeProviders
open Microsoft.FSharp.Linq
```

4. Al igual que con la mayoría de F # programas, puede ejecutar el código de este tutorial como un programa compilado, o puede ejecutar de forma interactiva como una secuencia de comandos. Si prefiere utilizar secuencias de comandos, abra el menú contextual para el nodo del proyecto, seleccione **Agregar nuevo elemento**, agregue un archivo de script de F # y agregue el código de cada paso en la secuencia de comandos. Debe agregar las líneas siguientes en la parte superior del archivo para cargar las referencias de ensamblado.

  ```fsharp
#r "System.Data.dll"
#r "FSharp.Data.TypeProviders.dll"
#r "System.Data.Linq.dll"
```

  A continuación, puede seleccionar cada bloque de código como agregarlo y presione ALT+ENTRAR para ejecutarlo en F # Interactive.

## <a name="setting-up-a-type-provider"></a>Cómo configurar un proveedor de tipos
En este paso, creará un proveedor de tipos para el esquema de base de datos.


#### <a name="to-set-up-the-type-provider-from-a-direct-database-connection"></a>Para configurar el proveedor de tipo de una conexión directa de la base de datos

Hay dos líneas críticas de código que necesita para crear los tipos que puede usar para consultar una base de datos SQL mediante el proveedor de tipos. En primer lugar, crear una instancia del proveedor de tipo. Para ello, cree aspecto una abreviatura de tipo para una `SqlDataConnection` con un parámetro genérico estático. `SqlDataConnection` es un proveedor de tipo SQL y no debe confundirse con `SqlConnection` tipo que es utilizado en la programación de ADO.NET. Si tiene una base de datos que desea conectarse a y tiene una cadena de conexión, utilice el siguiente código para invocar el proveedor de tipos. Sustituya su propia cadena de conexión para el ejemplo de cadena dada. Por ejemplo, si el servidor es MYSERVER y la instancia de base de datos es la instancia, el nombre de la base de datos es MyDatabase y desea utilizar la autenticación de Windows para tener acceso a la base de datos y, a continuación, la cadena de conexión sería como dada en el siguiente código de ejemplo.

```fsharp
type dbSchema = SqlDataConnection<"Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;">
let db = dbSchema.GetDataContext()

// Enable the logging of database activity to the console.
db.DataContext.Log <- System.Console.Out
```

Ahora ya tiene un tipo, `dbSchema`, que es un tipo de elemento primario que contiene todos los tipos generados que representan tablas de base de datos. También tiene un objeto, `db`, que tenga como miembros de todas las tablas de la base de datos. Los nombres de tabla son propiedades y el tipo de estas propiedades es generado por el compilador de F #. Los tipos en sí aparecen como los tipos anidados en `dbSchema.ServiceTypes`. Por lo tanto, los datos recuperados en las filas de estas tablas son una instancia del tipo adecuado que se generó para la tabla. El nombre del tipo es `ServiceTypes.Table1`.

Para familiarizarse con la forma en que el lenguaje F # interpreta las consultas en consultas SQL, revise la línea que establece el `Log` propiedad en el contexto de datos.

Para explorar más detalladamente los tipos creados mediante el proveedor de tipos, agregue el código siguiente.

```fsharp
let table1 = db.Table1
```

Mantenga el mouse sobre `table1` para ver su tipo. Su tipo es `System.Data.Linq.Table<dbSchema.ServiceTypes.Table1>` y el argumento genérico implica que el tipo de cada fila es el tipo generado, `dbSchema.ServiceTypes.Table1`. El compilador crea un tipo similar para cada tabla en la base de datos.

## <a name="querying-the-data"></a>Consultar los datos
En este paso, se escribe una consulta mediante expresiones de consulta de F #.


#### <a name="to-query-the-data"></a>Para consultar los datos

1. Ahora puede crear una consulta para la tabla en la base de datos. Agregue el código siguiente.

  ```fsharp
   let query1 =
     query {
       for row in db.Table1 do
       select row
     }
   query1 |> Seq.iter (fun row -> printfn "%s %d" row.Name row.TestData1)
```

  La apariencia de la palabra `query` indica que se trata de una expresión de consulta, un tipo de expresión de cálculo que genera un conjunto de resultados similar de una consulta de base de datos típica. Si mantiene el mouse sobre la consulta, verá que es una instancia de [Linq.QueryBuilder clase](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.querybuilder-class-%5bfsharp%5d), un tipo que define la expresión de cálculo de consulta. Si mantiene el mouse sobre `query1`, verá que es una instancia de `System.Linq.IQueryable`. Como sugiere su nombre, `System.Linq.IQueryable` representa los datos que se pueden consultar, no el resultado de una consulta. Una consulta se está sujeto a la evaluación diferida, lo que significa que la base de datos solo consulta cuando se evalúa la consulta. La línea final pasa la consulta a través de `Seq.iter`. Las consultas son enumerables y pueden recorrer en iteración como secuencias. Para obtener más información, consulte [expresiones de consulta](../../language-reference/query-expressions.md).

2. Ahora agregue un operador de consulta a la consulta. Hay una serie de operadores de consulta disponibles que se pueden utilizar para construir consultas más complejas. En este ejemplo también muestra que puede eliminar la variable de consulta y utilice en su lugar un operador de canalización.

  ```fsharp
   query {
     for row in db.Table1 do
     where (row.TestData1 > 2)
     select row
   } |> Seq.iter (fun row -> printfn "%d %s" row.TestData1 row.Name)
```

3. Agregar una consulta más compleja con una combinación de dos tablas.

  ```fsharp
   query {
     for row1 in db.Table1 do
     join row2 in db.Table2 on (row1.Id = row2.Id)
     select (row1, row2)
   } |> Seq.iteri (fun index (row1, row2) ->
                   if (index = 0) then printfn "Table1.Id TestData1 TestData2 Name Table2.Id TestData1 TestData2 Name"
                   printfn "%d %d %f %s %d %d %f %s" row1.Id row1.TestData1 row1.TestData2 row1.Name
                     row2.Id (row2.TestData1.GetValueOrDefault()) (row2.TestData2.GetValueOrDefault()) row2.Name)
```

4. En el código del mundo real, los parámetros de la consulta son normalmente valores o variables, constantes en tiempo de compilación no. Agregue el código siguiente que contiene una consulta en una función que toma un parámetro y, a continuación, llama a esa función con el valor 10.

  ```fsharp
   let findData param =
     query {
       for row in db.Table1 do
       where (row.TestData1 = param)
       select row
     }

   findData 10 |> Seq.iter (fun row -> printfn "Found row: %d %d %f %s" row.Id row.TestData1 row.TestData2 row.Name)
```

## <a name="working-with-nullable-fields"></a>Trabajar con campos que aceptan valores null
En las bases de datos, campos suelen permiten valores null. En el sistema de tipos. NET, no puede usar los tipos de datos numéricos normal para los datos que admita valores NULL porque esos tipos no tienen null como un valor posible. Por lo tanto, estos valores están representados por instancias de `System.Nullable` tipo. En lugar de tener acceso al valor de esos campos directamente con el nombre del campo, debe agregar algunos pasos adicionales. Puede usar el `System.Nullable.Value` propiedad que se va a obtener acceso al valor subyacente de un tipo que acepta valores NULL. El `System.Nullable.Value` propiedad produce una excepción si el objeto es null en lugar de tener un valor. Puede usar el `System.Nullable.HasValue` método booleana para determinar si existe un valor, o use `System.Nullable.GetValueOrDefault()` para asegurarse de que tiene un valor real en todos los casos. Si usa `System.Nullable.GetValueOrDefault()` y hay un valor null en la base de datos, a continuación, se reemplaza con un valor como una cadena vacía para los tipos de cadena, 0 para los tipos enteros o 0,0 flotante para los tipos de puntos.

Cuando necesite realizar pruebas de igualdad o comparaciones de valores que aceptan valores NULL en una `where` cláusula en una consulta, puede usar los operadores que aceptan valores NULL se encuentra en la [Linq.NullableOperators módulo](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.nullableoperators-module-%5bfsharp%5d). Estos son como los operadores de comparación regular `=`, `>`, `<=`, y así sucesivamente, salvo que un signo de interrogación aparece a la izquierda o derecha del operador donde son los valores que aceptan valores NULL. Por ejemplo, el operador `>?` es una mayor-que el operador con un valor que aceptan valores NULL a la derecha. El funcionamiento de estos operadores es que si ambos lados de la expresión es null, la expresión se evalúa como `false`. En un `where` cláusula, esto generalmente significa que las filas que contienen campos null están desactivadas y no se devuelve en los resultados de la consulta.


#### <a name="to-work-with-nullable-fields"></a>Para trabajar con campos que aceptan valores null

El código siguiente muestra cómo trabajar con valores que aceptan valores null; se asume que **TestData1** es un campo de número entero que permite valores NULL.

```fsharp
query {
  for row in db.Table2 do
  where (row.TestData1.HasValue && row.TestData1.Value > 2)
  select row
} |> Seq.iter (fun row -> printfn "%d %s" row.TestData1.Value row.Name)

query {
  for row in db.Table2 do
  // Use a nullable operator ?>
  where (row.TestData1 ?> 2)
  select row
} |> Seq.iter (fun row -> printfn "%d %s" (row.TestData1.GetValueOrDefault()) row.Name)
```

## <a name="calling-a-stored-procedure"></a>Llamar a un procedimiento almacenado
Los procedimientos almacenados en la base de datos pueden llamarse desde F #. Debe establecer el parámetro static `StoredProcedures` a `true` en la creación de instancias del proveedor de tipo. El proveedor de tipo `SqlDataConnection` contiene varios métodos estáticos que puede usar para configurar los tipos que se generan. Para obtener una descripción completa de estos, consulte [proveedor de tipos SqlDataConnection](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqldataconnection-type-provider-%5bfsharp%5d). Un método en el tipo de contexto de datos se genera para cada procedimiento almacenado.


#### <a name="to-call-a-stored-procedure"></a>Para llamar a un procedimiento almacenado

Si los procedimientos almacenados toma parámetros que aceptan valores NULL, debe pasar un adecuado `System.Nullable` valor. El valor devuelto de un método de procedimiento almacenado que devuelve un valor escalar o una tabla es `System.Data.Linq.ISingleResult`, que contiene propiedades que permiten obtener acceso a los datos devueltos. El argumento de tipo para `System.Data.Linq.ISingleResult` depende el procedimiento específico y también es uno de los tipos que genera el proveedor de tipos. Para un procedimiento almacenado denominado `Procedure1`, el tipo es `Procedure1Result`. El tipo `Procedure1Result` contiene los nombres de las columnas en una tabla devuelta, o bien, para un procedimiento almacenado que devuelve un valor escalar, representa el valor devuelto.

El código siguiente se supone que hay un procedimiento `Procedure1` en la base de datos que toma dos enteros que aceptan valores NULL como parámetros, se ejecuta una consulta que devuelve una columna denominada `TestData1`y devuelve un entero.

```fsharp
type schema = SqlDataConnection<"Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;", StoredProcedures = true>

let testdb = schema.GetDataContext()

let nullable value = new System.Nullable<_>(value)

let callProcedure1 a b =
  let results = testdb.Procedure1(nullable a, nullable b)
  for result in results do
    printfn "%d" (result.TestData1.GetValueOrDefault())
  results.ReturnValue :?> int

printfn "Return Value: %d" (callProcedure1 10 20)
```

## <a name="updating-the-database"></a>Actualizar la base de datos
El tipo de LINQ DataContext contiene métodos que resulten más fácil realizar actualizaciones de transacciones de la base de datos de manera totalmente con tipo con los tipos generados.


#### <a name="to-update-the-database"></a>Para actualizar la base de datos

1. En el código siguiente, se agregan varias filas a la base de datos. Si solo va a agregar una fila, puede usar `System.Data.Linq.Table.InsertOnSubmit()` para especificar la nueva fila para agregar. Si va a insertar varias filas, debe colocarlos en una colección y llame a `System.Data.Linq.Table.InsertAllOnSubmit(System.Collections.Generic.IEnumerable)`. Cuando se llama a cualquiera de estos métodos, no se cambia inmediatamente la base de datos. Debe llamar a `System.Data.Linq.DataContext.SubmitChanges` para confirmar los cambios. De forma predeterminada, todo lo que hay que hacer antes de llamar a `System.Data.Linq.DataContext.SubmitChanges` implícitamente forma parte de la misma transacción.

 ```fsharp
   let newRecord = new dbSchema.ServiceTypes.Table1(Id = 100,
                                                    TestData1 = 35, 
                                                    TestData2 = 2.0,
                                                    Name = "Testing123")

   let newValues =
     [ for i in [1 .. 10] ->
       new dbSchema.ServiceTypes.Table3(Id = 700 + i,
         Name = "Testing" + i.ToString(),
         Data = i) ]

   // Insert the new data into the database.
   db.Table1.InsertOnSubmit(newRecord)
   db.Table3.InsertAllOnSubmit(newValues)

   try
     db.DataContext.SubmitChanges()
     printfn "Successfully inserted new rows."
   with
   | exn -> printfn "Exception:\n%s" exn.Message
```

2. Limpiar ahora las filas mediante una llamada a una operación de eliminación.

  ```fsharp
   // Now delete what was added.
   db.Table1.DeleteOnSubmit(newRecord)
   db.Table3.DeleteAllOnSubmit(newValues)

   try
     db.DataContext.SubmitChanges()
     printfn "Successfully deleted all pending rows."
   with
   | exn -> printfn "Exception:\n%s" exn.Message
```

## <a name="executing-transact-sql-code"></a>Ejecutar código de Transact-SQL
También puede especificar Transact-SQL directamente mediante el `System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])` método en la `DataContext` clase.


#### <a name="to-execute-custom-sql-commands"></a>Para ejecutar comandos SQL personalizados

El código siguiente muestra cómo enviar comandos SQL para insertar un registro en una tabla y también para eliminar un registro de una tabla.

```fsharp
try
  db.DataContext.ExecuteCommand("INSERT INTO Table3 (Id, Name, Data) VALUES (102, 'Testing', 55)") |> ignore
with
| exn -> printfn "Exception:\n%s" exn.Message

try //AND Name = 'Testing' AND Data = 55
  db.DataContext.ExecuteCommand("DELETE FROM Table3 WHERE Id = 102 ") |> ignore
with
| exn -> printfn "Exception:\n%s" exn.Message
```

## <a name="using-the-full-data-context"></a>Utilizando el contexto de datos completa
En los ejemplos anteriores, la `GetDataContext` método utilizado para obtener lo que se conoce como el *contexto de datos simplificado* para el esquema de base de datos. El contexto de datos simplificado es más fácil de usar cuando se crean las consultas porque no hay tantos miembros. Por lo tanto, al examinar las propiedades de IntelliSense, puede centrarse en la estructura de base de datos, como las tablas y procedimientos almacenados. Sin embargo, hay un límite a lo que puede hacer con el contexto de datos simplificado. Un contexto de datos completa que proporciona la capacidad para realizar otras acciones. También está disponible se encuentra en la `ServiceTypes` y tiene el nombre de la *DataContext* parámetro estático si se proporcionó. Si no ha proporcionado, el nombre del tipo de contexto de datos se genera automáticamente mediante SqlMetal.exe en función de la otra entrada. Hereda el contexto de datos completa de `System.Data.Linq.DataContext` y expone los miembros de su clase base, incluidas las referencias a tipos de datos ADO.NET, como el `Connection` (objeto), métodos, como `System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])` y `System.Data.Linq.DataContext.ExecuteQuery(System.String,System.Object[])` que puede utilizar para escribir consultas en SQL, y también un medio para trabajar con transacciones de forma explícita.


#### <a name="to-use-the-full-data-context"></a>Utilizar el contexto de datos completa

El código siguiente muestra cómo obtener un objeto de contexto de datos completa y usarlo para ejecutar comandos directamente en la base de datos. En este caso, los dos comandos se ejecutan como parte de la misma transacción.

```fsharp
let dbConnection = testdb.Connection
let fullContext = new dbSchema.ServiceTypes.MyDatabase(dbConnection)

dbConnection.Open()

let transaction = dbConnection.BeginTransaction()
fullContext.Transaction <- transaction

try
  let result1 = fullContext.ExecuteCommand("INSERT INTO Table3 (Id, Name, Data) VALUES (102, 'A', 55)")
  printfn "ExecuteCommand Result: %d" result1
  let result2 = fullContext.ExecuteCommand("INSERT INTO Table3 (Id, Name, Data) VALUES (103, 'B', -2)")
  printfn "ExecuteCommand Result: %d" result2
  if (result1 <> 1 || result2 <> 1) then
    transaction.Rollback()
    printfn "Rolled back creation of two new rows."
  else
    transaction.Commit()
  printfn "Successfully committed two new rows."
with
| exn ->
  transaction.Rollback()
  printfn "Rolled back creation of two new rows due to exception:\n%s" exn.Message

dbConnection.Close()
```

## <a name="deleting-data"></a>Eliminar datos
Este paso muestra cómo eliminar filas de una tabla de datos.


#### <a name="to-delete-rows-from-the-database"></a>Para eliminar filas de la base de datos

Ahora, limpiar cualquiera agrega filas mediante la escritura de una función que elimina las filas de una tabla especificada, una instancia de la `System.Data.Linq.Table` clase. A continuación, escribir una consulta para buscar todas las filas que desea eliminar y canalizar los resultados de la consulta en el `deleteRows` (función). Este código aprovecha las ventajas de la capacidad para proporcionar una aplicación parcial de argumentos de función.

```fsharp
let deleteRowsFrom (table:Table<_>) rows =
  table.DeleteAllOnSubmit(rows)

query {
  for rows in db.Table3 do
  where (rows.Id > 10)
  select rows
} |> deleteRowsFrom db.Table3

db.DataContext.SubmitChanges()
printfn "Successfully deleted rows with Id greater than 10 in Table3."
```

## <a name="creating-a-test-database"></a>Crear una base de datos de prueba
En esta sección se muestra cómo configurar la base de datos de prueba para usarlo en este tutorial.

Tenga en cuenta que si modifica la base de datos de alguna manera, tendrá que restablecer el proveedor de tipos. Para restablecer el proveedor de tipos, volver a generar o limpiar el proyecto que contiene el proveedor de tipos.


#### <a name="to-create-the-test-database"></a>Para crear la base de datos de prueba

1. En **Explorador de servidores**, abra el menú contextual para el **las conexiones de datos** nodo y elija **Agregar conexión**. El **Agregar conexión** aparece el cuadro de diálogo.

2. En el **nombre del servidor** cuadro, especifique el nombre de una instancia de SQL Server que tienen acceso administrativo a o, si no tiene acceso a un servidor, especifique (localdb\v11.0). SQL Express LocalDB proporciona un servidor de base de datos ligera para desarrollo y pruebas en su equipo. Se crea un nuevo nodo en **Explorador de servidores** en **las conexiones de datos**. Para obtener más información acerca de LocalDB, vea [Tutorial: crear un archivo de base de datos Local en Visual Studio](https://msdn.microsoft.com/library/ms233763.aspx).

3. Abra el menú contextual para el nuevo nodo de conexión y seleccione **nueva consulta**.

4. Copie el siguiente script SQL, péguelo en el editor de consultas y, a continuación, elija la **Execute** situado en la barra de herramientas o presione las teclas Ctrl + Mayús + E.

```sql
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO

USE [master];
GO

IF EXISTS (SELECT * FROM sys.databases WHERE name = 'MyDatabase')
  DROP DATABASE MyDatabase;
GO

-- Create the MyDatabase database.
CREATE DATABASE MyDatabase;
GO

-- Specify a simple recovery model 
-- to keep the log growth to a minimum.
ALTER DATABASE MyDatabase 
SET RECOVERY SIMPLE;
GO

USE MyDatabase;
GO

-- Create the Table1 table.
CREATE TABLE [dbo].[Table1] (
  [Id]        INT        NOT NULL,
  [TestData1] INT        NOT NULL,
  [TestData2] FLOAT (53) NOT NULL,
  [Name]      NTEXT      NOT NULL,
  PRIMARY KEY CLUSTERED ([Id] ASC)
);

-- Create the Table2 table.
CREATE TABLE [dbo].[Table2] (
  [Id]        INT        NOT NULL,
  [TestData1] INT        NULL,
  [TestData2] FLOAT (53) NULL,
  [Name]      NTEXT      NOT NULL,
  PRIMARY KEY CLUSTERED ([Id] ASC)
);


-- Create the Table3 table.
CREATE TABLE [dbo].[Table3] (
  [Id]   INT           NOT NULL,
  [Name] NVARCHAR (50) NOT NULL,
  [Data] INT           NOT NULL,
  PRIMARY KEY CLUSTERED ([Id] ASC)
  );
GO

CREATE PROCEDURE [dbo].[Procedure1]
  @param1 int = 0,
  @param2 int
AS
SELECT TestData1 FROM Table1
RETURN 0
GO

USE MyDatabase

-- Insert data into the Table1 table.
INSERT INTO Table1 (Id, TestData1, TestData2, Name)
  VALUES(1, 10, 5.5, 'Testing1');
INSERT INTO Table1 (Id, TestData1, TestData2, Name)
  VALUES(2, 20, -1.2, 'Testing2');

-- Insert data into the Table2 table.
INSERT INTO Table2 (Id, TestData1, TestData2, Name)
  VALUES(1, 10, 5.5, 'Testing1');
INSERT INTO Table2 (Id, TestData1, TestData2, Name)
  VALUES(2, 20, -1.2, 'Testing2');
INSERT INTO Table2 (Id, TestData1, TestData2, Name)
  VALUES(3, NULL, NULL, 'Testing3');

-- Insert data into the Table3 table.
INSERT INTO Table3 (Id, Name, Data)
  VALUES (1, 'Testing1', 10);
INSERT INTO Table3 (Id, Name, Data)
  VALUES (2, 'Testing2', 100);
```


## <a name="see-also"></a>Vea también
[Proveedores de tipos](index.md)

[Proveedor de tipos SqlDataConnection](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqldataconnection-type-provider-%5bfsharp%5d)

[Tutorial: Generar tipos de F # a partir de un archivo DBML](generating-fsharp-types-from-dbml.md)

[Expresiones de consulta](../../language-reference/query-expressions.md)

[LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md)

[SqlMetal.exe &#40; Herramienta de generación de código &#41;](https://msdn.microsoft.com/library/bb386987)
