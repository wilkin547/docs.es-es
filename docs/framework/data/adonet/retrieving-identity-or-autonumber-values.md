---
title: Recuperar valores autonuméricos y de identidad
description: Obtenga información acerca de cómo recuperar valores de identidad y de autonumeración de claves principales en bases de datos relacionales y cómo combinar nuevos valores de identidad en ADO.NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d6b7f9cb-81be-44e1-bb94-56137954876d
ms.openlocfilehash: dbbc013a5b6c83391a29109beca44120c68d827f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286577"
---
# <a name="retrieving-identity-or-autonumber-values"></a>Recuperar valores autonuméricos y de identidad

Una clave principal de una base de datos relacional es una columna o combinación de columnas que siempre contienen valores únicos. Conocer el valor de la clave principal permite localizar la fila que la contiene. Los motores de bases de datos relacionales, como SQL Server, Oracle y Microsoft Access/Jet admiten la creación de columnas de incremento automático que pueden designarse como claves principales. Estos valores los genera el servidor cuando se agregan filas a una tabla. En SQL Server se establece la propiedad de identidad de una columna, en Oracle se crea una secuencia y en Microsoft Access se crea una columna Autonumérica.

<xref:System.Data.DataColumn> también se puede utilizar para generar de manera automática valores incrementales estableciendo la propiedad <xref:System.Data.DataColumn.AutoIncrement%2A> en true. No obstante, podría haber valores duplicados en instancias distintas de <xref:System.Data.DataTable> si varias aplicaciones cliente están generando por separado valores incrementales de manera automática. Si se tiene un servidor que genera de manera automática valores incrementales se eliminan posibles conflictos, pues se permite a cada usuario recuperar el valor generado para cada fila insertada.

Durante una llamada al método `Update` de `DataAdapter`, la base de datos puede volver a enviar datos a la aplicación ADO.NET como parámetros de salida o como el primer registro devuelto del conjunto de resultados de una instrucción SELECT ejecutada en el mismo lote que la instrucción INSERT. ADO.NET puede recuperar estos valores y actualizar las columnas correspondientes en el <xref:System.Data.DataRow> que se está actualizando.

Algunos motores de base de datos, como los de Microsoft Access Jet, no admiten parámetros de salida y no pueden procesar varias instrucciones en un único lote. Cuando trabaje con el motor de base de datos de Jet, puede recuperar el nuevo valor Autonumérico generado para una fila insertada ejecutando un comando SELECT distinto en un controlador de eventos para el evento `RowUpdated` de `DataAdapter`.

> [!NOTE]
> Una opción alternativa al uso de un valor de incremento automático es utilizar el método <xref:System.Guid.NewGuid%2A> de un objeto <xref:System.Guid> para generar un GUID (identificador único global) en el equipo cliente que se pueda copiar al servidor cuando se inserte una nueva fila. El método `NewGuid` genera un valor binario de 16 bits que se crea mediante un algoritmo que permite que haya una alta probabilidad de que no se duplique ningún valor. En una base de datos de SQL Server, el GUID se almacena en una columna `uniqueidentifier` que SQL Server puede generar automáticamente mediante la función Transact-SQL `NEWID()`. Utilizar un GUID como clave principal puede afectar de manera negativa al rendimiento. SQL Server proporciona compatibilidad con la `NEWSEQUENTIALID()` función, que genera un GUID secuencial que no se garantiza que sea globalmente único, pero que se puede indizar de forma más eficaz.

## <a name="retrieving-sql-server-identity-column-values"></a>Recuperar valores de columnas de identidad de SQL Server

Cuando trabaje con Microsoft SQL Server, puede crear procedimientos almacenados con un parámetro de salida para devolver el valor de identidad de una fila insertada. La siguiente tabla describe las tres funciones de Transact-SQL en SQL Server que se pueden utilizar para recuperar valores de columna de identidad.

|Función|Descripción|
|--------------|-----------------|
|SCOPE_IDENTITY|Devuelve el último valor de identidad en el ámbito de ejecución actual. SCOPE_IDENTITY se recomienda en la mayoría de los casos.|
|@@IDENTITY|Contiene el último valor de identidad generado en cualquier tabla de la sesión actual. @ @IDENTITY puede verse afectado por los desencadenadores y es posible que no devuelva el valor de identidad que espera.|
|IDENT_CURRENT|Devuelve el último valor de identidad generado para una tabla concreta de cualquier sesión y en cualquier ámbito.|

 El siguiente procedimiento almacenado muestra cómo insertar una fila en la tabla **Categories** y cómo utilizar un parámetro de salida para devolver el nuevo valor de identidad generado por la función TRANSACT-SQL SCOPE_IDENTITY ().

```sql
CREATE PROCEDURE dbo.InsertCategory
  @CategoryName nvarchar(15),
  @Identity int OUT
AS
INSERT INTO Categories (CategoryName) VALUES(@CategoryName)
SET @Identity = SCOPE_IDENTITY()
```

El procedimiento almacenado se puede especificar como el origen de <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> de un objeto <xref:System.Data.SqlClient.SqlDataAdapter>. La propiedad <xref:System.Data.SqlClient.SqlCommand.CommandType%2A> de <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> debe establecerse en <xref:System.Data.CommandType.StoredProcedure>. La salida de identidad se recupera creando un <xref:System.Data.SqlClient.SqlParameter> que tiene un <xref:System.Data.ParameterDirection> de <xref:System.Data.ParameterDirection.Output>. Cuando `InsertCommand` se procesa, se devuelve el valor de identidad de incremento automático y se coloca en la columna **CategoryID** de la fila actual si se establece la <xref:System.Data.SqlClient.SqlCommand.UpdatedRowSource%2A> propiedad del comando INSERT en `UpdateRowSource.OutputParameters` o en `UpdateRowSource.Both` .

Si el comando de inserción ejecuta un lote que incluye tanto una instrucción INSERT como una instrucción SELECT que devuelven el nuevo valor de identidad, entonces puede recuperar el nuevo valor estableciendo la propiedad `UpdatedRowSource` del comando de inserción en `UpdateRowSource.FirstReturnedRecord`.

[!code-csharp[DataWorks SqlClient.RetrieveIdentityStoredProcedure#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.RetrieveIdentityStoredProcedure/CS/source.cs#1)]
[!code-vb[DataWorks SqlClient.RetrieveIdentityStoredProcedure#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.RetrieveIdentityStoredProcedure/VB/source.vb#1)]

## <a name="merging-new-identity-values"></a>Combinar nuevos valores de identidad

Un caso frecuente es llamar al método `GetChanges` de `DataTable` para crear una copia que contiene únicamente filas modificadas y utilizar la nueva copia al llamar al método `Update` de `DataAdapter`. Esto es especialmente útil cuando hay que serializar las filas modificadas en un componente independiente que realiza la actualización. Después de la actualización, la copia puede contener nuevos valores de identidad que se deben volver a combinar en el `DataTable` original. Probablemente los nuevos valores de identidad son diferentes a los valores originales de `DataTable`. Para realizar la combinación, deben conservarse los valores originales de las columnas de **incremento automático** de la copia, con el fin de poder localizar y actualizar las filas existentes en el original `DataTable` , en lugar de anexar nuevas filas que contengan los nuevos valores de identidad. No obstante, de manera predeterminada estos valores se pierden después de una llamada al método `Update` de `DataAdapter`, debido a que se llama implícitamente a `AcceptChanges` en cada `DataRow` actualizada.

Hay dos maneras de mantener los valores originales de `DataColumn` en `DataRow` durante una actualización de `DataAdapter`:

- El primer método para mantener los valores originales consiste en establecer la propiedad `AcceptChangesDuringUpdate` de `DataAdapter` en `false`. Esto afecta a cada `DataRow` de `DataTable` que se está actualizando. Para más información y ver un código de ejemplo, vea <xref:System.Data.Common.DataAdapter.AcceptChangesDuringUpdate%2A>.

- El segundo método consiste en escribir código en el controlador de eventos `RowUpdated` de `DataAdapter` para establecer <xref:System.Data.Common.RowUpdatedEventArgs.Status%2A> en <xref:System.Data.UpdateStatus.SkipCurrentRow>. `DataRow` se actualiza pero se mantiene el valor original de cada `DataColumn`. Este método permite mantener los valores originales en algunas filas y no en otras. Por ejemplo, el código puede mantener los valores originales de filas agregadas y no los de filas editadas o eliminadas comprobando primero <xref:System.Data.Common.RowUpdatedEventArgs.StatementType%2A> y, a continuación, estableciendo <xref:System.Data.Common.RowUpdatedEventArgs.Status%2A> en <xref:System.Data.UpdateStatus.SkipCurrentRow> únicamente para filas con un `StatementType` de `Insert`.

Cuando se utiliza alguno de estos métodos para mantener los valores originales de `DataRow` durante una actualización de `DataAdapter`, ADO.NET realiza una serie de acciones para establecer los valores actuales de `DataRow` a los nuevos valores devueltos por parámetros de salida o por la primera fila devuelta de un conjunto de resultados, al tiempo que se mantiene el valor original de cada `DataColumn`. Primero, se llama al método `AcceptChanges` de `DataRow` para mantener los valores actuales como valores originales y, a continuación, se asignan los nuevos valores. Después de estas acciones, las `DataRows` que tienen la propiedad <xref:System.Data.DataRow.RowState%2A> establecida en <xref:System.Data.DataRowState.Added> tendrán su propiedad `RowState` establecida en <xref:System.Data.DataRowState.Modified>, lo que puede ser inesperado.

El modo en que se aplican los resultados del comando a cada <xref:System.Data.DataRow> que se actualiza lo determina la propiedad <xref:System.Data.Common.DbCommand.UpdatedRowSource%2A> de cada <xref:System.Data.Common.DbCommand>. Esta propiedad se establece en un valor desde la enumeración `UpdateRowSource`.

La siguiente tabla describe cómo afectan los valores de enumeración `UpdateRowSource` a la propiedad <xref:System.Data.DataRow.RowState%2A> de las filas actualizadas.

|Nombre del miembro|Descripción|
|-----------------|-----------------|
|<xref:System.Data.UpdateRowSource.Both>|Se llama a `AcceptChanges` y tanto los parámetros de salida como los valores de la primera fila de cualquier conjunto de resultados devuelto se colocan en la `DataRow` que se está actualizando. Si no hay valores que aplicar, `RowState` será <xref:System.Data.DataRowState.Unchanged>.|
|<xref:System.Data.UpdateRowSource.FirstReturnedRecord>|Si se devuelve una fila, se llama a `AcceptChanges` y la fila se asigna a la fila modificada en `DataTable`, estableciendo `RowState` en `Modified`. Si no se devuelve ninguna fila, entonces no se llama a `AcceptChanges` y `RowState` permanece en `Added`.|
|<xref:System.Data.UpdateRowSource.None>|Se pasan por alto todos los parámetros o filas devueltos. No hay llamada a `AcceptChanges` y `RowState` permanece en `Added`.|
|<xref:System.Data.UpdateRowSource.OutputParameters>|Se llama a `AcceptChanges` y todos los parámetros de salida se asignan a la fila modificada en `DataTable`, estableciendo `RowState` en `Modified`. Si no hay parámetros de salida, `RowState` será `Unchanged`.|

### <a name="example"></a>Ejemplo

Este ejemplo muestra la extracción de filas modificadas desde `DataTable` y el uso de <xref:System.Data.SqlClient.SqlDataAdapter> para actualizar el origen de datos y recuperar un nuevo valor de columna de identidad. <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> ejecuta dos instrucciones Transact-SQL; la primera es la instrucción INSERT y la segunda es la instrucción SELECT.

```sql
INSERT INTO dbo.Shippers (CompanyName)
VALUES (@CompanyName);
SELECT ShipperID, CompanyName FROM dbo.Shippers
WHERE ShipperID = SCOPE_IDENTITY();
```

La propiedad `UpdatedRowSource` del comando de inserción se establece en `UpdateRowSource.FirstReturnedRow` y la propiedad <xref:System.Data.MissingSchemaAction> de `DataAdapter` se establece en `MissingSchemaAction.AddWithKey`. `DataTable` se rellena y el código agrega una nueva fila a `DataTable`. A continuación, las filas modificadas se extraen en un nuevo `DataTable`, que se pasa a `DataAdapter`, el cual actualiza el servidor.

[!code-csharp[DataWorks SqlClient.MergeIdentity#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.MergeIdentity/CS/source.cs#1)]
[!code-vb[DataWorks SqlClient.MergeIdentity#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.MergeIdentity/VB/source.vb#1)]

El controlador de eventos `OnRowUpdated` comprueba <xref:System.Data.Common.RowUpdatedEventArgs.StatementType%2A> de <xref:System.Data.SqlClient.SqlRowUpdatedEventArgs> para determinar si la fila es una inserción. Si lo es, entonces la propiedad se establece <xref:System.Data.Common.RowUpdatedEventArgs.Status%2A> en <xref:System.Data.UpdateStatus.SkipCurrentRow>. La fila está actualizada, pero los valores originales de la fila se mantienen. En el cuerpo principal del procedimiento, se llama al método <xref:System.Data.DataSet.Merge%2A> para fusión mediante combinación el nuevo valor de identidad en el `DataTable` original y, finalmente, se llama a `AcceptChanges`.

[!code-csharp[DataWorks SqlClient.MergeIdentity#2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.MergeIdentity/CS/source.cs#2)]
[!code-vb[DataWorks SqlClient.MergeIdentity#2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.MergeIdentity/VB/source.vb#2)]

## <a name="retrieving-microsoft-access-autonumber-values"></a>Recuperar valores de autonumeración de Microsoft Access

Esta sección incluye un ejemplo que muestra cómo recuperar valores de `Autonumber` desde una base de datos de Jet 4.0. El motor de la base de datos de Jet no admite la ejecución de varias instrucciones en un lote o el uso de parámetros de salida, por lo que no es posible utilizar ninguna de estas técnicas para devolver el nuevo valor `Autonumber` asignado a una fila insertada. Sin embargo, puede agregar código al `RowUpdated` controlador de eventos que ejecuta una instrucción SELECT @ independiente @IDENTITY para recuperar el nuevo `Autonumber` valor.

### <a name="example"></a>Ejemplo

En lugar de agregar información de esquema utilizando `MissingSchemaAction.AddWithKey`, este ejemplo configura `DataTable` con el esquema adecuado antes de llamar a <xref:System.Data.OleDb.OleDbDataAdapter> para rellenar `DataTable`. En este caso, la columna **CategoryID** se configura para disminuir el valor asignado a cada fila insertada a partir de cero, estableciendo <xref:System.Data.DataColumn.AutoIncrement%2A> en `true` , <xref:System.Data.DataColumn.AutoIncrementSeed%2A> en 0 y <xref:System.Data.DataColumn.AutoIncrementStep%2A> en-1. Entonces, el código agrega dos filas nuevas y utiliza `GetChanges` para agregar las filas modificadas a un nuevo `DataTable` que se pasa al método `Update`.

[!code-csharp[DataWorks OleDb.JetAutonumberMerge#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks OleDb.JetAutonumberMerge/CS/source.cs#1)]
[!code-vb[DataWorks OleDb.JetAutonumberMerge#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks OleDb.JetAutonumberMerge/VB/source.vb#1)]

El controlador de eventos `RowUpdated` utiliza el mismo <xref:System.Data.OleDb.OleDbConnection> abierto que la instrucción `Update` de `OleDbDataAdapter`. Comprueba el `StatementType` de <xref:System.Data.OleDb.OleDbRowUpdatedEventArgs> de las filas insertadas. Para cada fila insertada <xref:System.Data.OleDb.OleDbCommand> , se crea un nuevo para ejecutar la @IDENTITY instrucción SELECT @ en la conexión, devolviendo el nuevo `Autonumber` valor, que se coloca en la columna **CategoryID** de `DataRow` . La propiedad `Status` se establece luego en `UpdateStatus.SkipCurrentRow` para suprimir la llamada oculta a `AcceptChanges`. En el cuerpo principal del procedimiento, se llama al método `Merge` para fusionar mediante combinación los dos objetos `DataTable` y, finalmente, se llama a `AcceptChanges`.

[!code-csharp[DataWorks OleDb.JetAutonumberMerge#2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks OleDb.JetAutonumberMerge/CS/source.cs#2)]
[!code-vb[DataWorks OleDb.JetAutonumberMerge#2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks OleDb.JetAutonumberMerge/VB/source.vb#2)]

### <a name="retrieving-identity-values"></a>Recuperar valores de identidad

A menudo se establece la columna como identidad cuando los valores de la columna deben ser únicos. A veces se necesita el valor de identidad de los nuevos datos. En este ejemplo se muestra cómo recuperar los valores de identidad:

- Crea un procedimiento almacenado para insertar los datos y devolver un valor de identidad.

- Ejecuta un comando para insertar los nuevos datos y mostrar el resultado.

- Usa <xref:System.Data.SqlClient.SqlDataAdapter> para insertar nuevos datos y mostrar el resultado.

Antes de compilar y ejecutar el ejemplo, debe crear la base de datos de ejemplo mediante el script siguiente:

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
CREATE procedure [dbo].[CourseExtInfo] @CourseId int
as
select c.CourseID,c.Title,c.Credits,d.Name as DepartmentName
from Course as c left outer join Department as d on c.DepartmentID=d.DepartmentID
where c.CourseID=@CourseId

GO

SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
create procedure [dbo].[DepartmentInfo] @DepartmentId int,@CourseCount int output
as
select @CourseCount=Count(c.CourseID)
from course as c
where c.DepartmentID=@DepartmentId

select d.DepartmentID,d.Name,d.Budget,d.StartDate,d.Administrator
from Department as d
where d.DepartmentID=@DepartmentId

GO

SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
Create PROCEDURE [dbo].[GetDepartmentsOfSpecifiedYear]
@Year int,@BudgetSum money output
AS
BEGIN
        SELECT @BudgetSum=SUM([Budget])
  FROM [MySchool].[dbo].[Department]
  Where YEAR([StartDate])=@Year

SELECT [DepartmentID]
      ,[Name]
      ,[Budget]
      ,[StartDate]
      ,[Administrator]
  FROM [MySchool].[dbo].[Department]
  Where YEAR([StartDate])=@Year

END
GO

SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE PROCEDURE [dbo].[GradeOfStudent]
-- Add the parameters for the stored procedure here
@CourseTitle nvarchar(100),@FirstName nvarchar(50),
@LastName nvarchar(50),@Grade decimal(3,2) output
AS
BEGIN
select @Grade=Max(Grade)
from [dbo].[StudentGrade] as s join [dbo].[Course] as c on
s.CourseID=c.CourseID join [dbo].[Person] as p on s.StudentID=p.PersonID
where c.Title=@CourseTitle and p.FirstName=@FirstName
and p.LastName= @LastName
END
GO

SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE PROCEDURE [dbo].[InsertPerson]
-- Add the parameters for the stored procedure here
@FirstName nvarchar(50),@LastName nvarchar(50),
@PersonID int output
AS
BEGIN
    insert [dbo].[Person](LastName,FirstName) Values(@LastName,@FirstName)

    set @PersonID=SCOPE_IDENTITY()
END
Go

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

SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
SET ANSI_PADDING ON
GO
CREATE TABLE [dbo].[Person]([PersonID] [int] IDENTITY(1,1) NOT NULL,
[LastName] [nvarchar](50) NOT NULL,
[FirstName] [nvarchar](50) NOT NULL,
[HireDate] [datetime] NULL,
[EnrollmentDate] [datetime] NULL,
[Picture] [varbinary](max) NULL,
 CONSTRAINT [PK_School.Student] PRIMARY KEY CLUSTERED
(
[PersonID] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]) ON [PRIMARY] TEXTIMAGE_ON [PRIMARY]

GO

SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE TABLE [dbo].[StudentGrade]([EnrollmentID] [int] IDENTITY(1,1) NOT NULL,
[CourseID] [nvarchar](10) NOT NULL,
[StudentID] [int] NOT NULL,
[Grade] [decimal](3, 2) NOT NULL,
 CONSTRAINT [PK_StudentGrade] PRIMARY KEY CLUSTERED
(
[EnrollmentID] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]) ON [PRIMARY]

GO

SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
create view [dbo].[EnglishCourse]
as
select c.CourseID,c.Title,c.Credits,c.DepartmentID
from Course as c join Department as d on c.DepartmentID=d.DepartmentID
where d.Name=N'English'

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
SET IDENTITY_INSERT [dbo].[Person] ON

INSERT [dbo].[Person] ([PersonID], [LastName], [FirstName], [HireDate], [EnrollmentDate]) VALUES (1, N'Hu', N'Nan', NULL, CAST(0x0000A0BF00000000 AS DateTime))
INSERT [dbo].[Person] ([PersonID], [LastName], [FirstName], [HireDate], [EnrollmentDate]) VALUES (2, N'Norman', N'Laura', NULL, CAST(0x0000A0BF00000000 AS DateTime))
INSERT [dbo].[Person] ([PersonID], [LastName], [FirstName], [HireDate], [EnrollmentDate]) VALUES (3, N'Olivotto', N'Nino', NULL, CAST(0x0000A0BF00000000 AS DateTime))
INSERT [dbo].[Person] ([PersonID], [LastName], [FirstName], [HireDate], [EnrollmentDate]) VALUES (4, N'Anand', N'Arturo', NULL, CAST(0x0000A0BF00000000 AS DateTime))
INSERT [dbo].[Person] ([PersonID], [LastName], [FirstName], [HireDate], [EnrollmentDate]) VALUES (5, N'Jai', N'Damien', NULL, CAST(0x0000A0BF00000000 AS DateTime))
INSERT [dbo].[Person] ([PersonID], [LastName], [FirstName], [HireDate], [EnrollmentDate]) VALUES (6, N'Holt', N'Roger', CAST(0x000097F100000000 AS DateTime), NULL)
INSERT [dbo].[Person] ([PersonID], [LastName], [FirstName], [HireDate], [EnrollmentDate]) VALUES (7, N'Martin', N'Randall', CAST(0x00008B1A00000000 AS DateTime), NULL)
SET IDENTITY_INSERT [dbo].[Person] OFF
SET IDENTITY_INSERT [dbo].[StudentGrade] ON

INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (1, N'C1045', 1, CAST(3.50 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (2, N'C1045', 2, CAST(3.00 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (3, N'C1045', 3, CAST(2.50 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (4, N'C1045', 4, CAST(4.00 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (5, N'C1045', 5, CAST(3.50 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (6, N'C1061', 1, CAST(4.00 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (7, N'C1061', 3, CAST(3.50 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (8, N'C1061', 4, CAST(2.50 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (9, N'C1061', 5, CAST(1.50 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (10, N'C2021', 1, CAST(2.50 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (11, N'C2021', 2, CAST(3.50 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (12, N'C2021', 4, CAST(3.00 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (13, N'C2021', 5, CAST(3.00 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (14, N'C2042', 1, CAST(2.00 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (15, N'C2042', 2, CAST(3.50 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (16, N'C2042', 3, CAST(4.00 AS Decimal(3, 2)))
INSERT [dbo].[StudentGrade] ([EnrollmentID], [CourseID], [StudentID], [Grade]) VALUES (17, N'C2042', 5, CAST(3.00 AS Decimal(3, 2)))
SET IDENTITY_INSERT [dbo].[StudentGrade] OFF
ALTER TABLE [dbo].[Course]  WITH CHECK ADD  CONSTRAINT [FK_Course_Department] FOREIGN KEY([DepartmentID])
REFERENCES [dbo].[Department] ([DepartmentID])
GO
ALTER TABLE [dbo].[Course] CHECK CONSTRAINT [FK_Course_Department]
GO
ALTER TABLE [dbo].[StudentGrade]  WITH CHECK ADD  CONSTRAINT [FK_StudentGrade_Student] FOREIGN KEY([StudentID])
REFERENCES [dbo].[Person] ([PersonID])
GO
ALTER TABLE [dbo].[StudentGrade] CHECK CONSTRAINT [FK_StudentGrade_Student]
GO
```

A continuación se incluye la lista de código:

> [!TIP]
> La lista de código hace referencia a un archivo de base de datos de Access denominado MySchool.mdb. Puede descargar el. mdb (como parte del proyecto de ejemplo completo de C# o Visual Basic) de [code.msdn.Microsoft.com](https://code.msdn.microsoft.com/How-to-Retrieve-the-511acece).

```csharp
using System;
using System.Data;
using System.Data.OleDb;
using System.Data.SqlClient;

class Program {
   static void Main(string[] args) {
      String SqlDbConnectionString = "Data Source=(local);Initial Catalog=MySchool;Integrated Security=True;Asynchronous Processing=true;";

      InsertPerson(SqlDbConnectionString, "Janice", "Galvin");
      Console.WriteLine();

      InsertPersonInAdapter(SqlDbConnectionString, "Peter", "Krebs");
      Console.WriteLine();

      String oledbConnectionString = "Provider=Microsoft.Jet.OLEDB.4.0; Data Source=Database\\MySchool.mdb";
      InsertPersonInJet4Database(oledbConnectionString, "Janice", "Galvin");
      Console.WriteLine();

      Console.WriteLine("Please press any key to exit.....");
      Console.ReadKey();
   }

   // Using stored procedure to insert a new row and retrieve the identity value
   static void InsertPerson(String connectionString, String firstName, String lastName) {
      String commandText = "dbo.InsertPerson";

      using (SqlConnection conn = new SqlConnection(connectionString)) {
         using (SqlCommand cmd = new SqlCommand(commandText, conn)) {
            cmd.CommandType = CommandType.StoredProcedure;

            cmd.Parameters.Add(new SqlParameter("@FirstName", firstName));
            cmd.Parameters.Add(new SqlParameter("@LastName", lastName));
            SqlParameter personId = new SqlParameter("@PersonID", SqlDbType.Int);
            personId.Direction = ParameterDirection.Output;
            cmd.Parameters.Add(personId);

            conn.Open();
            cmd.ExecuteNonQuery();

            Console.WriteLine("Person Id of new person:{0}", personId.Value);
         }
      }
   }

   // Using stored procedure in adapter to insert new rows and update the identity value.
   static void InsertPersonInAdapter(String connectionString, String firstName, String lastName) {
      String commandText = "dbo.InsertPerson";
      using (SqlConnection conn = new SqlConnection(connectionString)) {
         SqlDataAdapter mySchool = new SqlDataAdapter("Select PersonID,FirstName,LastName from [dbo].[Person]", conn);

         mySchool.InsertCommand = new SqlCommand(commandText, conn);
         mySchool.InsertCommand.CommandType = CommandType.StoredProcedure;

         mySchool.InsertCommand.Parameters.Add(
             new SqlParameter("@FirstName", SqlDbType.NVarChar, 50, "FirstName"));
         mySchool.InsertCommand.Parameters.Add(
             new SqlParameter("@LastName", SqlDbType.NVarChar, 50, "LastName"));

         SqlParameter personId = mySchool.InsertCommand.Parameters.Add(new SqlParameter("@PersonID", SqlDbType.Int, 0, "PersonID"));
         personId.Direction = ParameterDirection.Output;

         DataTable persons = new DataTable();
         mySchool.Fill(persons);

         DataRow newPerson = persons.NewRow();
         newPerson["FirstName"] = firstName;
         newPerson["LastName"] = lastName;
         persons.Rows.Add(newPerson);

         mySchool.Update(persons);
         Console.WriteLine("Show all persons:");
         ShowDataTable(persons, 14);
      }
   }

   /// For a Jet 4.0 database, we need use the single statement and event handler to insert new rows and retrieve the identity value.
   static void InsertPersonInJet4Database(String connectionString, String firstName, String lastName) {
      String commandText = "Insert into Person(FirstName,LastName) Values(?,?)";
      using (OleDbConnection conn = new OleDbConnection(connectionString)) {
         OleDbDataAdapter mySchool = new OleDbDataAdapter("Select PersonID,FirstName,LastName from Person", conn);

         // Create Insert Command
         mySchool.InsertCommand = new OleDbCommand(commandText, conn);
         mySchool.InsertCommand.CommandType = CommandType.Text;

         mySchool.InsertCommand.Parameters.Add(new OleDbParameter("@FirstName", OleDbType.VarChar, 50, "FirstName"));
         mySchool.InsertCommand.Parameters.Add(new OleDbParameter("@LastName", OleDbType.VarChar, 50, "LastName"));
         mySchool.InsertCommand.UpdatedRowSource = UpdateRowSource.Both;

         DataTable persons = CreatePersonsTable();

         mySchool.Fill(persons);

         DataRow newPerson = persons.NewRow();
         newPerson["FirstName"] = firstName;
         newPerson["LastName"] = lastName;
         persons.Rows.Add(newPerson);

         DataTable dataChanges = persons.GetChanges();

         mySchool.RowUpdated += OnRowUpdated;

         mySchool.Update(dataChanges);

         Console.WriteLine("Data before merging:");
         ShowDataTable(persons, 14);
         Console.WriteLine();

         persons.Merge(dataChanges);
         persons.AcceptChanges();

         Console.WriteLine("Data after merging");
         ShowDataTable(persons, 14);
      }
   }

   static void OnRowUpdated(object sender, OleDbRowUpdatedEventArgs e) {
      if (e.StatementType == StatementType.Insert) {
         // Retrieve the identity value
         OleDbCommand cmdNewId = new OleDbCommand("Select @@IDENTITY", e.Command.Connection);
         e.Row["PersonID"] = (Int32)cmdNewId.ExecuteScalar();

         // After the status is changed, the original values in the row are preserved. And the
         // Merge method will be called to merge the new identity value into the original DataTable.
         e.Status = UpdateStatus.SkipCurrentRow;
      }
   }

   // Create the Persons table before filling.
   private static DataTable CreatePersonsTable() {
      DataTable persons = new DataTable();

      DataColumn personId = new DataColumn();
      personId.DataType = Type.GetType("System.Int32");
      personId.ColumnName = "PersonID";
      personId.AutoIncrement = true;
      personId.AutoIncrementSeed = 0;
      personId.AutoIncrementStep = -1;
      persons.Columns.Add(personId);

      DataColumn firstName = new DataColumn();
      firstName.DataType = Type.GetType("System.String");
      firstName.ColumnName = "FirstName";
      persons.Columns.Add(firstName);

      DataColumn lastName = new DataColumn();
      lastName.DataType = Type.GetType("System.String");
      lastName.ColumnName = "LastName";
      persons.Columns.Add(lastName);

      DataColumn[] pkey = { personId };
      persons.PrimaryKey = pkey;

      return persons;
   }

   private static void ShowDataTable(DataTable table, Int32 length) {
      foreach (DataColumn col in table.Columns) {
         Console.Write("{0,-" + length + "}", col.ColumnName);
      }
      Console.WriteLine();

      foreach (DataRow row in table.Rows) {
         foreach (DataColumn col in table.Columns) {
            if (col.DataType.Equals(typeof(DateTime)))
               Console.Write("{0,-" + length + ":d}", row[col]);
            else if (col.DataType.Equals(typeof(Decimal)))
               Console.Write("{0,-" + length + ":C}", row[col]);
            else
               Console.Write("{0,-" + length + "}", row[col]);
         }

         Console.WriteLine();
      }
   }
}
```

## <a name="see-also"></a>Consulte también

- [Recuperar y modificar datos en ADO.NET](retrieving-and-modifying-data.md)
- [Objetos DataAdapter y DataReader](dataadapters-and-datareaders.md)
- [Estados y versiones de filas](./dataset-datatable-dataview/row-states-and-row-versions.md)
- [Objetos AcceptChange y RejectChange](./dataset-datatable-dataview/acceptchanges-and-rejectchanges.md)
- [Combinar contenido de DataSet](./dataset-datatable-dataview/merging-dataset-contents.md)
- [Actualizar orígenes de datos con objetos DataAdapter](updating-data-sources-with-dataadapters.md)
- [Información general de ADO.NET](ado-net-overview.md)
