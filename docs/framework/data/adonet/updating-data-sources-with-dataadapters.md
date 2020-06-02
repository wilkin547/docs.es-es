---
title: Actualizar orígenes de datos con objetos DataAdapter
description: Obtenga información sobre cómo el método Update de DataAdapter resuelve los cambios de un conjunto de datos de nuevo en el origen de datos de las aplicaciones de ADO.NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d1bd9a8c-0e29-40e3-bda8-d89176b72fb1
ms.openlocfilehash: e2348a3a89aa1c28856bfc21aaa25f2c8327aac7
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286189"
---
# <a name="updating-data-sources-with-dataadapters"></a>Actualizar orígenes de datos con objetos DataAdapter

El método `Update` de <xref:System.Data.Common.DataAdapter> se llama para reflejar en el origen de datos todos los cambios efectuados en <xref:System.Data.DataSet>. El método `Update`, al igual que el método `Fill`, acepta como argumentos una instancia de `DataSet` y, de forma opcional, un objeto <xref:System.Data.DataTable> o un nombre de `DataTable`. La instancia de `DataSet` es el `DataSet` que contiene los cambios efectuados, y `DataTable` identifica la tabla desde la que se pueden recuperar esos cambios. Si no se especifica `DataTable`, se utiliza el primer `DataTable` de `DataSet`.

Al llamar al método `Update`, `DataAdapter` analiza los cambios efectuados y ejecuta el comando apropiado (INSERT, UPDATE o DELETE). Cuando `DataAdapter` encuentra un cambio en <xref:System.Data.DataRow>, utiliza los comandos <xref:System.Data.Common.DbDataAdapter.InsertCommand%2A>, <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A> o <xref:System.Data.Common.DbDataAdapter.DeleteCommand%2A> para reflejarlo. De esta forma, se obtiene el máximo rendimiento de la aplicación de ADO.NET al especificar la sintaxis del comando en la fase de diseño y utilizar, siempre que es posible, procedimientos almacenados. Antes de llamar a `Update` deben establecerse de forma explícita los comandos. Si se llama a `Update` y el comando correspondiente a una actualización determinada no existe (por ejemplo, no hay un comando `DeleteCommand` para las filas eliminadas), se inicia una excepción.

> [!NOTE]
> Si está utilizando procedimientos almacenados de SQL Server para editar o eliminar datos con `DataAdapter`, asegúrese de que no utiliza SET NOCOUNT ON en la definición del procedimiento almacenado. Esto hace que el recuento de filas afectadas vuelva a cero, lo que `DataAdapter` interpreta como un conflicto de simultaneidad. En este caso, se iniciará una <xref:System.Data.DBConcurrencyException>.

Se pueden usar los parámetros de comando para especificar los valores de entrada y salida de una instrucción SQL o un procedimiento almacenado para cada fila modificada en `DataSet`. Para obtener más información, vea [DataAdapter Parameters](dataadapter-parameters.md).

> [!NOTE]
> Es importante comprender la diferencia entre eliminar una fila de una <xref:System.Data.DataTable> y quitar la fila. Al llamar al método `Remove` o `RemoveAt`, la fila se quita inmediatamente. Cualquier fila correspondiente en el origen de datos back end no se verá afectada si a continuación se pasa `DataTable` o `DataSet` a `DataAdapter` y se llama a `Update`. Al utilizar el método `Delete`, la fila permanece en `DataTable` y se marca para eliminación. Si a continuación se pasa `DataTable` o `DataSet` a `DataAdapter` y se llama a `Update`, la fila correspondiente en el origen de datos back end se elimina.

Si `DataTable` está asignada a una única base de datos o se ha generado a partir de ella, puede utilizar el objeto <xref:System.Data.Common.DbCommandBuilder> para generar automáticamente los objetos `DeleteCommand`, `InsertCommand` y `UpdateCommand` de `DataAdapter`. Para obtener más información, vea [generar comandos con objetos CommandBuilder](generating-commands-with-commandbuilders.md).

## <a name="using-updatedrowsource-to-map-values-to-a-dataset"></a>Utilizar UpdatedRowSource para asignar valores a DataSet

Puede controlar la forma en que los valores devueltos desde el origen de datos se asignan a `DataTable` después de una llamada al método Update de `DataAdapter`, utilizando la propiedad <xref:System.Data.Common.DbCommand.UpdatedRowSource%2A> de un objeto <xref:System.Data.Common.DbCommand>. Al asignar la propiedad `UpdatedRowSource` a uno de los valores de enumeración <xref:System.Data.UpdateRowSource>, puede determinar si los parámetros que devuelven los comandos `DataAdapter` se deben omitir o se deben aplicar a la fila cambiada en `DataSet`. También puede especificar si la primera fila devuelta (si existe) se aplica a la fila modificada en `DataTable`.

En la tabla siguiente se describen los distintos valores de la enumeración `UpdateRowSource` y la forma en que afectan al comportamiento del comando utilizado con `DataAdapter`.

|Enumeración UpdatedRowSource|Descripción|
|----------------------------------|-----------------|
|<xref:System.Data.UpdateRowSource.Both>|Tanto los parámetros de salida como la primera fila del conjunto de resultados devuelto se pueden asignar a la fila modificada en `DataSet`.|
|<xref:System.Data.UpdateRowSource.FirstReturnedRecord>|Solo los datos de la primera fila del conjunto de resultados devuelto se pueden asignar a la fila modificada en el `DataSet`.|
|<xref:System.Data.UpdateRowSource.None>|Se pasan por alto todos los parámetros de salida y las filas del conjunto de resultados devuelto.|
|<xref:System.Data.UpdateRowSource.OutputParameters>|Solo los parámetros de salida se pueden asignar a la fila modificada en `DataSet`.|

El método `Update` vuelve a resolver los cambios en el origen de datos; sin embargo, puede que otros clientes hayan modificado datos en el origen de datos desde la última vez que se llenó `DataSet`. Para actualizar `DataSet` con datos actuales, utilice el `DataAdapter` y el método `Fill`. De esta forma se agregan las filas nuevas a la tabla y se actualiza la información en las filas ya existentes. El método `Fill` determina si se va a agregar una nueva fila o si se va a actualizar una fila existente mediante el examen de los valores de clave principal de las filas de `DataSet` y las filas devueltas por `SelectCommand`. Si el método `Fill` encuentra un valor de clave principal de una fila de `DataSet` que coincide con un valor de clave principal de una fila de los resultados devueltos por `SelectCommand`, éste actualiza la fila existente con la información de la fila devuelta por `SelectCommand` y establece el <xref:System.Data.DataRow.RowState%2A> de la fila existente en `Unchanged`. Si una fila devuelta por `SelectCommand` tiene un valor de clave principal que no coincide con ninguno de los valores de clave principal de las filas de `DataSet`, el método `Fill` agrega una nueva fila con un `RowState` de `Unchanged`.

> [!NOTE]
> Si `SelectCommand` devuelve los resultados de una combinación externa (OUTER JOIN), `DataAdapter` no establecerá un valor `PrimaryKey` para la tabla `DataTable` resultante. Debe definir `PrimaryKey` para asegurarse de que las filas duplicadas se resuelven correctamente. Para obtener más información, vea [definir claves principales](./dataset-datatable-dataview/defining-primary-keys.md).

Para controlar las excepciones que se pueden producir al llamar al `Update` método, puede utilizar el `RowUpdated` evento para responder a los errores de actualización de la fila a medida que se producen (vea [controlar eventos DataAdapter](handling-dataadapter-events.md)), o puede establecer `DataAdapter.ContinueUpdateOnError` en `true` antes de llamar a `Update` y responder a la información de error almacenada en la `RowError` propiedad de una fila determinada cuando se completa la actualización (vea la [información de error de fila](./dataset-datatable-dataview/row-error-information.md)).

> [!NOTE]
> Llamar a `AcceptChanges` en `DataSet` , `DataTable` o hará `DataRow` que todos los `Original` valores de `DataRow` se sobrescriban con los `Current` valores de `DataRow` . Si se han modificado los valores de campo que identifican de forma única a una fila, los valores `AcceptChanges` dejarán de coincidir con los valores del origen de datos después de llamar a `Original`. Se llama automáticamente a `AcceptChanges` para cada fila durante una llamada al método Update de `DataAdapter`. Puede conservar los valores originales durante una llamada al método Update estableciendo primero la propiedad `AcceptChangesDuringUpdate` de `DataAdapter` en false o creando un controlador de eventos para el evento `RowUpdated` y estableciendo <xref:System.Data.Common.RowUpdatedEventArgs.Status%2A> en <xref:System.Data.UpdateStatus.SkipCurrentRow>. Para obtener más información, vea [combinar el contenido](./dataset-datatable-dataview/merging-dataset-contents.md) de un conjunto de datos y [controlar eventos DataAdapter](handling-dataadapter-events.md).

## <a name="example"></a>Ejemplo

En los siguientes ejemplos se muestra cómo realizar actualizaciones de las filas modificadas estableciendo explícitamente el valor `UpdateCommand` de `DataAdapter` y llamando a su `Update` método. Observe cómo el parámetro especificado en la cláusula WHERE de la instrucción UPDATE tiene el valor adecuado para usar el valor `Original` de `SourceColumn`. Este hecho es muy importante ya que el valor `Current` puede haber sido modificado de forma que ya no coincida con el valor del origen de datos. El valor `Original` es el que se usó para rellenar la tabla `DataTable` a partir del origen de datos.

[!code-csharp[DataWorks SqlClient.DataAdapterUpdate#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.DataAdapterUpdate/CS/source.cs#1)]
[!code-vb[DataWorks SqlClient.DataAdapterUpdate#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.DataAdapterUpdate/VB/source.vb#1)]

## <a name="autoincrement-columns"></a>Columnas AutoIncrement

Si las tablas del origen de datos tienen columnas con incremento automático, puede rellenar las columnas de `DataSet` devolviendo el valor de incremento automático como un parámetro de salida de un procedimiento almacenado y asignándolo a una columna de la tabla, o devolviendo el valor de incremento automático de la primera fila de un conjunto de resultados devuelto por un procedimiento almacenado o una instrucción SQL, o mediante el evento `RowUpdated` de `DataAdapter` para ejecutar una instrucción SELECT adicional. Para obtener más información y un ejemplo, vea [recuperar valores de identidad o Autonumérico](retrieving-identity-or-autonumber-values.md).

## <a name="ordering-of-inserts-updates-and-deletes"></a>Orden de las inserciones, actualizaciones y eliminaciones

En algunas circunstancias, es importante el orden en que se envían al origen de datos los cambios realizados en el `DataSet`. Por ejemplo, si se actualiza el valor de una clave principal de una fila existente y se ha agregado una nueva fila con el nuevo valor de la clave principal como una clave externa, es importante que la actualización de la fila se procese antes que la inserción.

Puede usar el método `Select` de `DataTable` para devolver una matriz `DataRow` que solo haga referencia a filas con un estado `RowState` determinado. A continuación, puede pasar la matriz `DataRow` al método `Update` de `DataAdapter` para procesar las filas modificadas. Al especificar un subconjunto de filas que modificar, puede controlar el orden en que se procesan las inserciones, actualizaciones y eliminaciones.

## <a name="example"></a>Ejemplo

Por ejemplo, en el código siguiente se garantiza que en primer lugar se realizan en la tabla las eliminaciones de filas, después las actualizaciones y finalmente las inserciones.

```vb
Dim table As DataTable = dataSet.Tables("Customers")

' First process deletes.
dataSet.Update(table.Select(Nothing, Nothing, _
  DataViewRowState.Deleted))

' Next process updates.
adapter.Update(table.Select(Nothing, Nothing, _
  DataViewRowState.ModifiedCurrent))

' Finally, process inserts.
adapter.Update(table.Select(Nothing, Nothing, _
  DataViewRowState.Added))
```

```csharp
DataTable table = dataSet.Tables["Customers"];

// First process deletes.
adapter.Update(table.Select(null, null, DataViewRowState.Deleted));

// Next process updates.
adapter.Update(table.Select(null, null,
  DataViewRowState.ModifiedCurrent));

// Finally, process inserts.
adapter.Update(table.Select(null, null, DataViewRowState.Added));
```

## <a name="use-a-dataadapter-to-retrieve-and-update-data"></a>Usar un objeto DataAdapter para recuperar y actualizar datos

Puede usar un objeto DataAdapter para recuperar y actualizar los datos.

- El ejemplo usa DataAdapter.AcceptChangesDuringFill para clonar los datos en la base de datos. Si la propiedad se establece como false, no se llama a AcceptChanges al rellenar la tabla y las filas que se acaban de agregar se tratan como filas insertadas. Por lo tanto, el ejemplo usa estas filas para insertar las filas nuevas en la base de datos.

- Los ejemplos usan DataAdapter.TableMappings para definir la asignación entre la tabla de origen y DataTable.

- El ejemplo usa DataAdapter.FillLoadOption para determinar cómo rellena el adaptador el objeto DataTable de DbDataReader. Al crear un objeto DataTable, solo puede escribir los datos de la base de datos en la versión actual o en la versión original si establece la propiedad como LoadOption.Upsert o LoadOption.PreserveChanges.

- El ejemplo también actualizará la tabla mediante DbDataAdapter.UpdateBatchSize para realizar operaciones por lotes.

Antes de compilar y ejecutar el ejemplo, debe crear la base de datos de ejemplo:

```sql
USE [master]
GO

CREATE DATABASE [MySchool]

GO

USE [MySchool]
GO

SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Course]([CourseID] [nvarchar](10) NOT NULL,
[Year] [smallint] NOT NULL,
[Title] [nvarchar](100) NOT NULL,
[Credits] [int] NOT NULL,
[DepartmentID] [int] NOT NULL,
 CONSTRAINT [PK_Course] PRIMARY KEY CLUSTERED
(
[CourseID] ASC,
[Year] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]) ON [PRIMARY]

GO

SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[Department]([DepartmentID] [int] IDENTITY(1,1) NOT NULL,
[Name] [nvarchar](50) NOT NULL,
[Budget] [money] NOT NULL,
[StartDate] [datetime] NOT NULL,
[Administrator] [int] NULL,
 CONSTRAINT [PK_Department] PRIMARY KEY CLUSTERED
(
[DepartmentID] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]) ON [PRIMARY]

GO

INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C1045', 2012, N'Calculus', 4, 7)
INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C1061', 2012, N'Physics', 4, 1)
INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C2021', 2012, N'Composition', 3, 2)
INSERT [dbo].[Course] ([CourseID], [Year], [Title], [Credits], [DepartmentID]) VALUES (N'C2042', 2012, N'Literature', 4, 2)

SET IDENTITY_INSERT [dbo].[Department] ON

INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (1, N'Engineering', 350000.0000, CAST(0x0000999C00000000 AS DateTime), 2)
INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (2, N'English', 120000.0000, CAST(0x0000999C00000000 AS DateTime), 6)
INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (4, N'Economics', 200000.0000, CAST(0x0000999C00000000 AS DateTime), 4)
INSERT [dbo].[Department] ([DepartmentID], [Name], [Budget], [StartDate], [Administrator]) VALUES (7, N'Mathematics', 250024.0000, CAST(0x0000999C00000000 AS DateTime), 3)
SET IDENTITY_INSERT [dbo].[Department] OFF

ALTER TABLE [dbo].[Course]  WITH CHECK ADD  CONSTRAINT [FK_Course_Department] FOREIGN KEY([DepartmentID])
REFERENCES [dbo].[Department] ([DepartmentID])
GO
ALTER TABLE [dbo].[Course] CHECK CONSTRAINT [FK_Course_Department]
GO
```

Los proyectos de C# y Visual Basic con este ejemplo de código se pueden encontrar en [ejemplos de código para desarrolladores](https://code.msdn.microsoft.com/site/search?f%5B0%5D.Type=SearchText&f%5B0%5D.Value=How%20to%20use%20DataAdapter%20to%20retrieve%20and%20update%20data&f%5B1%5D).

```csharp
using System;
using System.Data;
using System.Data.Common;
using System.Data.SqlClient;
using System.Linq;
using CSDataAdapterOperations.Properties;

namespace CSDataAdapterOperations.Properties {
   internal sealed partial class Settings : global::System.Configuration.ApplicationSettingsBase {

      private static Settings defaultInstance = ((Settings)(global::System.Configuration.ApplicationSettingsBase.Synchronized(new Settings())));

      public static Settings Default {
         get {
            return defaultInstance;
         }
      }

      [global::System.Configuration.ApplicationScopedSettingAttribute()]
      [global::System.Configuration.DefaultSettingValueAttribute("Data Source=(local);Initial Catalog=MySchool;Integrated Security=True")]
      public string MySchoolConnectionString {
         get {
            return ((string)(this["MySchoolConnectionString"]));
         }
      }
   }
}

class Program {
   static void Main(string[] args) {
      Settings settings = new Settings();

      // Copy the data from the database.  Get the table Department and Course from the database.
      String selectString = @"SELECT [DepartmentID],[Name],[Budget],[StartDate],[Administrator]
                                     FROM [MySchool].[dbo].[Department];

                                   SELECT [CourseID],@Year as [Year],Max([Title]) as [Title],
                                   Max([Credits]) as [Credits],Max([DepartmentID]) as [DepartmentID]
                                   FROM [MySchool].[dbo].[Course]
                                   Group by [CourseID]";

      DataSet mySchool = new DataSet();

      SqlCommand selectCommand = new SqlCommand(selectString);
      SqlParameter parameter = selectCommand.Parameters.Add("@Year", SqlDbType.SmallInt, 2);
      parameter.Value = new Random(DateTime.Now.Millisecond).Next(9999);

      // Use DataTableMapping to map the source tables and the destination tables.
      DataTableMapping[] tableMappings = {new DataTableMapping("Table", "Department"), new DataTableMapping("Table1", "Course")};
      CopyData(mySchool, settings.MySchoolConnectionString, selectCommand, tableMappings);

      Console.WriteLine("The following tables are from the database.");
      foreach (DataTable table in mySchool.Tables) {
         Console.WriteLine(table.TableName);
         ShowDataTable(table);
      }

      // Roll back the changes
      DataTable department = mySchool.Tables["Department"];
      DataTable course = mySchool.Tables["Course"];

      department.Rows[0]["Name"] = "New" + department.Rows[0][1];
      course.Rows[0]["Title"] = "New" + course.Rows[0]["Title"];
      course.Rows[0]["Credits"] = 10;

      Console.WriteLine("After we changed the tables:");
      foreach (DataTable table in mySchool.Tables) {
         Console.WriteLine(table.TableName);
         ShowDataTable(table);
      }

      department.RejectChanges();
      Console.WriteLine("After use the RejectChanges method in Department table to roll back the changes:");
      ShowDataTable(department);

      DataColumn[] primaryColumns = { course.Columns["CourseID"] };
      DataColumn[] resetColumns = { course.Columns["Title"] };
      ResetCourse(course, settings.MySchoolConnectionString, primaryColumns, resetColumns);
      Console.WriteLine("After use the ResetCourse method in Course table to roll back the changes:");
      ShowDataTable(course);

      // Batch update the table.
      String insertString = @"Insert into [MySchool].[dbo].[Course]([CourseID],[Year],[Title],
                                   [Credits],[DepartmentID])
             values (@CourseID,@Year,@Title,@Credits,@DepartmentID)";
      SqlCommand insertCommand = new SqlCommand(insertString);
      insertCommand.Parameters.Add("@CourseID", SqlDbType.NVarChar, 10, "CourseID");
      insertCommand.Parameters.Add("@Year", SqlDbType.SmallInt, 2, "Year");
      insertCommand.Parameters.Add("@Title", SqlDbType.NVarChar, 100, "Title");
      insertCommand.Parameters.Add("@Credits", SqlDbType.Int, 4, "Credits");
      insertCommand.Parameters.Add("@DepartmentID", SqlDbType.Int, 4, "DepartmentID");

      const Int32 batchSize = 10;
      BatchInsertUpdate(course, settings.MySchoolConnectionString, insertCommand, batchSize);
   }

   private static void CopyData(DataSet dataSet, String connectionString, SqlCommand selectCommand, DataTableMapping[] tableMappings) {
      using (SqlConnection connection = new SqlConnection(connectionString)) {
         selectCommand.Connection = connection;

         connection.Open();

         using (SqlDataAdapter adapter = new SqlDataAdapter(selectCommand)) {adapter.TableMappings.AddRange(tableMappings);
            // If set the AcceptChangesDuringFill as the false, AcceptChanges will not be called on a
            // DataRow after it is added to the DataTable during any of the Fill operations.
            adapter.AcceptChangesDuringFill = false;

            adapter.Fill(dataSet);
         }
      }
   }

   // Roll back only one column or several columns data of the Course table by call ResetDataTable method.
   private static void ResetCourse(DataTable table, String connectionString,
       DataColumn[] primaryColumns, DataColumn[] resetColumns) {
      table.PrimaryKey = primaryColumns;

      // Build the query string
      String primaryCols = String.Join(",", primaryColumns.Select(col => col.ColumnName));
      String resetCols = String.Join(",", resetColumns.Select(col => $"Max({col.ColumnName}) as {col.ColumnName}"));

      String selectString = $"Select {primaryCols},{resetCols} from Course Group by {primaryCols}");

      SqlCommand selectCommand = new SqlCommand(selectString);

      ResetDataTable(table, connectionString, selectCommand);
   }

   // RejectChanges will roll back all changes made to the table since it was loaded, or the last time AcceptChanges
   // was called. When you copy from the database, you can lose all the data after calling RejectChanges
   // The ResetDataTable method rolls back one or more columns of data.
   private static void ResetDataTable(DataTable table, String connectionString,
       SqlCommand selectCommand) {
      using (SqlConnection connection = new SqlConnection(connectionString)) {
         selectCommand.Connection = connection;

         connection.Open();

         using (SqlDataAdapter adapter = new SqlDataAdapter(selectCommand)) {
            // The incoming values for this row will be written to the current version of each
            // column. The original version of each column's data will not be changed.
            adapter.FillLoadOption = LoadOption.Upsert;

            adapter.Fill(table);
         }
      }
   }

   private static void BatchInsertUpdate(DataTable table, String connectionString,
       SqlCommand insertCommand, Int32 batchSize) {
      using (SqlConnection connection = new SqlConnection(connectionString)) {
         insertCommand.Connection = connection;
         // When setting UpdateBatchSize to a value other than 1, all the commands
         // associated with the SqlDataAdapter have to have their UpdatedRowSource
         // property set to None or OutputParameters. An exception is thrown otherwise.
         insertCommand.UpdatedRowSource = UpdateRowSource.None;

         connection.Open();

         using (SqlDataAdapter adapter = new SqlDataAdapter()) {
            adapter.InsertCommand = insertCommand;
            // Gets or sets the number of rows that are processed in each round-trip to the server.
            // Setting it to 1 disables batch updates, as rows are sent one at a time.
            adapter.UpdateBatchSize = batchSize;

            adapter.Update(table);

            Console.WriteLine("Successfully to update the table.");
         }
      }
   }

   private static void ShowDataTable(DataTable table) {
      foreach (DataColumn col in table.Columns) {
         Console.Write("{0,-14}", col.ColumnName);
      }
      Console.WriteLine("{0,-14}", "RowState");

      foreach (DataRow row in table.Rows) {
         foreach (DataColumn col in table.Columns) {
            if (col.DataType.Equals(typeof(DateTime)))
               Console.Write("{0,-14:d}", row[col]);
            else if (col.DataType.Equals(typeof(Decimal)))
               Console.Write("{0,-14:C}", row[col]);
            else
               Console.Write("{0,-14}", row[col]);
         }
         Console.WriteLine("{0,-14}", row.RowState);
      }
   }
}
```

## <a name="see-also"></a>Consulte también

- [Objetos DataAdapter y DataReader](dataadapters-and-datareaders.md)
- [Estados y versiones de filas](./dataset-datatable-dataview/row-states-and-row-versions.md)
- [Objetos AcceptChange y RejectChange](./dataset-datatable-dataview/acceptchanges-and-rejectchanges.md)
- [Combinar contenido de DataSet](./dataset-datatable-dataview/merging-dataset-contents.md)
- [Recuperar valores autonuméricos y de identidad](retrieving-identity-or-autonumber-values.md)
- [Información general de ADO.NET](ado-net-overview.md)
