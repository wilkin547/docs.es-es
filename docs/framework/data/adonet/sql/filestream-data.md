---
description: 'Más información acerca de: datos de FILESTREAM'
title: Datos FILESTREAM
ms.date: 03/30/2017
ms.assetid: bd8b845c-0f09-4295-b466-97ef106eefa8
ms.openlocfilehash: 0110be6b867a07ec1cd204e2a3de371367bbfa36
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802052"
---
# <a name="filestream-data"></a><span data-ttu-id="1a2aa-103">Datos FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="1a2aa-103">FILESTREAM Data</span></span>

<span data-ttu-id="1a2aa-104">El atributo de almacenamiento FILESTREAM sirve para los datos binarios (BLOB) almacenados en una columna varbinary(max).</span><span class="sxs-lookup"><span data-stu-id="1a2aa-104">The FILESTREAM storage attribute is for binary (BLOB) data stored in a varbinary(max) column.</span></span> <span data-ttu-id="1a2aa-105">Antes de FILESTREAM, el almacenamiento de datos binarios requería un tratamiento especial.</span><span class="sxs-lookup"><span data-stu-id="1a2aa-105">Before FILESTREAM, storing binary data required special handling.</span></span> <span data-ttu-id="1a2aa-106">Los datos no estructurados, como los documentos de texto, las imágenes y el vídeo, se suelen almacenar fuera de la base de datos, por lo que resultan difíciles de administrar.</span><span class="sxs-lookup"><span data-stu-id="1a2aa-106">Unstructured data, such as text documents, images and video, is often stored outside of the database, making it difficult to manage.</span></span>

> [!NOTE]
> <span data-ttu-id="1a2aa-107">Debe instalar .NET Framework 3.5 Service Pack 1 (o posterior) para trabajar con datos de FILESTREAM con SqlClient.</span><span class="sxs-lookup"><span data-stu-id="1a2aa-107">You must install the .NET Framework 3.5 SP1 (or later) to work with FILESTREAM data using SqlClient.</span></span>

<span data-ttu-id="1a2aa-108">La especificación del atributo FILESTREAM en una columna varbinary(max) provoca que SQL Server almacene los datos en el sistema de archivos NTFS local en lugar de hacerlo en el archivo de base de datos.</span><span class="sxs-lookup"><span data-stu-id="1a2aa-108">Specifying the FILESTREAM attribute on a varbinary(max) column causes SQL Server to store the data on the local NTFS file system instead of in the database file.</span></span> <span data-ttu-id="1a2aa-109">Aunque se almacenan por separado, puede usar las mismas instrucciones de Transact-SQL admitidas para trabajar con los datos varbinary(max) almacenados en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1a2aa-109">Although it is stored separately, you can use the same Transact-SQL statements that are supported for working with varbinary(max) data that is stored in the database.</span></span>

## <a name="sqlclient-support-for-filestream"></a><span data-ttu-id="1a2aa-110">Compatibilidad de SqlClient con FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="1a2aa-110">SqlClient Support for FILESTREAM</span></span>

<span data-ttu-id="1a2aa-111">El proveedor de datos de .NET Framework para SQL Server, <xref:System.Data.SqlClient> , admite la lectura y escritura en datos de FileStream mediante la <xref:System.Data.SqlTypes.SqlFileStream> clase definida en el <xref:System.Data.SqlTypes> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="1a2aa-111">The .NET Framework Data Provider for SQL Server, <xref:System.Data.SqlClient>, supports reading and writing to FILESTREAM data using the <xref:System.Data.SqlTypes.SqlFileStream> class defined in the <xref:System.Data.SqlTypes> namespace.</span></span> <span data-ttu-id="1a2aa-112">`SqlFileStream` hereda de la clase <xref:System.IO.Stream>, que proporciona métodos para leer y escribir en flujos de datos.</span><span class="sxs-lookup"><span data-stu-id="1a2aa-112">`SqlFileStream` inherits from the <xref:System.IO.Stream> class, which provides methods for reading and writing to streams of data.</span></span> <span data-ttu-id="1a2aa-113">Al leer de un flujo, se transfieren datos del flujo a una estructura de datos, como una matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="1a2aa-113">Reading from a stream transfers data from the stream into a data structure, such as an array of bytes.</span></span> <span data-ttu-id="1a2aa-114">Al escribir, se transfieren los datos de la estructura de datos a un flujo.</span><span class="sxs-lookup"><span data-stu-id="1a2aa-114">Writing transfers the data from the data structure into a stream.</span></span>

### <a name="creating-the-sql-server-table"></a><span data-ttu-id="1a2aa-115">Crear la tabla de SQL Server</span><span class="sxs-lookup"><span data-stu-id="1a2aa-115">Creating the SQL Server Table</span></span>

<span data-ttu-id="1a2aa-116">Las instrucciones siguientes de Transact-SQL crean una tabla denominada Employees e insertan una fila de datos.</span><span class="sxs-lookup"><span data-stu-id="1a2aa-116">The following Transact-SQL statements creates a table named employees and inserts a row of data.</span></span> <span data-ttu-id="1a2aa-117">Una vez que haya habilitado el almacenamiento de FILESTREAM, puede usar esta tabla junto con los ejemplos de código siguientes.</span><span class="sxs-lookup"><span data-stu-id="1a2aa-117">Once you have enabled FILESTREAM storage, you can use this table in conjunction with the code examples that follow.</span></span> <span data-ttu-id="1a2aa-118">Al final de este tema se encuentran los vínculos a los recursos de los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1a2aa-118">The links to resources in SQL Server Books Online are located at the end of this topic.</span></span>

```sql
CREATE TABLE employees
(
  EmployeeId INT  NOT NULL  PRIMARY KEY,
  Photo VARBINARY(MAX) FILESTREAM  NULL,
  RowGuid UNIQUEIDENTIFIER  NOT NULL  ROWGUIDCOL
  UNIQUE DEFAULT NEWID()
)
GO
Insert into employees
Values(1, 0x00, default)
GO
```

### <a name="example-reading-overwriting-and-inserting-filestream-data"></a><span data-ttu-id="1a2aa-119">Ejemplo: leer, sobrescribir e insertar datos de FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="1a2aa-119">Example: Reading, Overwriting, and Inserting FILESTREAM Data</span></span>

<span data-ttu-id="1a2aa-120">El ejemplo siguiente muestra cómo se leen datos de FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="1a2aa-120">The following sample demonstrates how to read data from a FILESTREAM.</span></span> <span data-ttu-id="1a2aa-121">El código obtiene la ruta de acceso lógica al archivo, estableciendo `FileAccess` en `Read` y `FileOptions` en `SequentialScan`.</span><span class="sxs-lookup"><span data-stu-id="1a2aa-121">The code gets the logical path to the file, setting the `FileAccess` to `Read` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="1a2aa-122">A continuación, el código lee los bytes de SqlFileStream en el búfer.</span><span class="sxs-lookup"><span data-stu-id="1a2aa-122">The code then reads the bytes from the SqlFileStream into the buffer.</span></span> <span data-ttu-id="1a2aa-123">Los bytes se escriben luego en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="1a2aa-123">The bytes are then written to the console window.</span></span>

<span data-ttu-id="1a2aa-124">El ejemplo muestra también cómo se escriben datos en una instancia de FILESTREAM en la que se sobrescriben todos los datos existentes.</span><span class="sxs-lookup"><span data-stu-id="1a2aa-124">The sample also demonstrates how to write data to a FILESTREAM in which all existing data is overwritten.</span></span> <span data-ttu-id="1a2aa-125">El código obtiene la ruta de acceso lógica al archivo y crea `SqlFileStream`, estableciendo `FileAccess` en `Write` y `FileOptions` en `SequentialScan`.</span><span class="sxs-lookup"><span data-stu-id="1a2aa-125">The code gets the logical path to the file and creates the `SqlFileStream`, setting the `FileAccess` to `Write` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="1a2aa-126">Un solo byte se escribe en `SqlFileStream`, reemplazando todos los datos del archivo.</span><span class="sxs-lookup"><span data-stu-id="1a2aa-126">A single byte is written to the `SqlFileStream`, replacing any data in the file.</span></span>

<span data-ttu-id="1a2aa-127">En el ejemplo también se muestra cómo escribir datos en FILESTREAM mediante el método Seek para anexar datos al final del archivo.</span><span class="sxs-lookup"><span data-stu-id="1a2aa-127">The sample also demonstrates how to write data to a FILESTREAM by using the Seek method to append data to the end of the file.</span></span> <span data-ttu-id="1a2aa-128">El código obtiene la ruta de acceso lógica al archivo y crea `SqlFileStream`, estableciendo `FileAccess` en `ReadWrite` y `FileOptions` en `SequentialScan`.</span><span class="sxs-lookup"><span data-stu-id="1a2aa-128">The code gets the logical path to the file and creates the `SqlFileStream`, setting the `FileAccess` to `ReadWrite` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="1a2aa-129">El código usa el método Seek para buscar el final del archivo, anexando un solo byte al archivo existente.</span><span class="sxs-lookup"><span data-stu-id="1a2aa-129">The code uses the Seek method to seek to the end of the file, appending a single byte to the existing file.</span></span>

```csharp
using System;
using System.Data.SqlClient;
using System.Data.SqlTypes;
using System.Data;
using System.IO;

namespace FileStreamTest
{
    class Program
    {
        static void Main(string[] args)
        {
            SqlConnectionStringBuilder builder = new SqlConnectionStringBuilder("server=(local);integrated security=true;database=myDB");
            ReadFileStream(builder);
            OverwriteFileStream(builder);
            InsertFileStream(builder);

            Console.WriteLine("Done");
        }

        private static void ReadFileStream(SqlConnectionStringBuilder connStringBuilder)
        {
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))
            {
                connection.Open();
                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);

                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);
                command.Transaction = tran;

                using (SqlDataReader reader = command.ExecuteReader())
                {
                    while (reader.Read())
                    {
                        // Get the pointer for the file
                        string path = reader.GetString(0);
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;

                        // Create the SqlFileStream
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.Read, FileOptions.SequentialScan, allocationSize: 0))
                        {
                            // Read the contents as bytes and write them to the console
                            for (long index = 0; index < fileStream.Length; index++)
                            {
                                Console.WriteLine(fileStream.ReadByte());
                            }
                        }
                    }
                }
                tran.Commit();
            }
        }

        private static void OverwriteFileStream(SqlConnectionStringBuilder connStringBuilder)
        {
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))
            {
                connection.Open();

                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);

                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);
                command.Transaction = tran;

                using (SqlDataReader reader = command.ExecuteReader())
                {
                    while (reader.Read())
                    {
                        // Get the pointer for file
                        string path = reader.GetString(0);
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;

                        // Create the SqlFileStream
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.Write, FileOptions.SequentialScan, allocationSize: 0))
                        {
                            // Write a single byte to the file. This will
                            // replace any data in the file.
                            fileStream.WriteByte(0x01);
                        }
                    }
                }
                tran.Commit();
            }
        }

        private static void InsertFileStream(SqlConnectionStringBuilder connStringBuilder)
        {
            using (SqlConnection connection = new SqlConnection(connStringBuilder.ToString()))
            {
                connection.Open();

                SqlCommand command = new SqlCommand("SELECT TOP(1) Photo.PathName(), GET_FILESTREAM_TRANSACTION_CONTEXT() FROM employees", connection);

                SqlTransaction tran = connection.BeginTransaction(IsolationLevel.ReadCommitted);
                command.Transaction = tran;

                using (SqlDataReader reader = command.ExecuteReader())
                {
                    while (reader.Read())
                    {
                        // Get the pointer for file
                        string path = reader.GetString(0);
                        byte[] transactionContext = reader.GetSqlBytes(1).Buffer;

                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.ReadWrite, FileOptions.SequentialScan, allocationSize: 0))
                        {
                            // Seek to the end of the file
                            fileStream.Seek(0, SeekOrigin.End);

                            // Append a single byte
                            fileStream.WriteByte(0x01);
                        }
                    }
                }
                tran.Commit();
            }

        }
    }
}
```

<span data-ttu-id="1a2aa-130">Para obtener otro ejemplo, vea [Cómo almacenar y recuperar datos binarios en una columna de flujo de archivo](https://www.codeproject.com/Articles/32216/How-to-store-and-fetch-binary-data-into-a-file-str).</span><span class="sxs-lookup"><span data-stu-id="1a2aa-130">For another sample, see [How to store and fetch binary data into a file stream column](https://www.codeproject.com/Articles/32216/How-to-store-and-fetch-binary-data-into-a-file-str).</span></span>

## <a name="resources-in-sql-server-books-online"></a><span data-ttu-id="1a2aa-131">Recursos en los Libros en pantalla de SQL Server</span><span class="sxs-lookup"><span data-stu-id="1a2aa-131">Resources in SQL Server Books Online</span></span>

<span data-ttu-id="1a2aa-132">La documentación completa de FILESTREAM se encuentra en las secciones siguientes de los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1a2aa-132">The complete documentation for FILESTREAM is located in the following sections in SQL Server Books Online.</span></span>

|<span data-ttu-id="1a2aa-133">Tema</span><span class="sxs-lookup"><span data-stu-id="1a2aa-133">Topic</span></span>|<span data-ttu-id="1a2aa-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="1a2aa-134">Description</span></span>|
|-----------|-----------------|
|[<span data-ttu-id="1a2aa-135">FILESTREAM (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1a2aa-135">FILESTREAM (SQL Server)</span></span>](/sql/relational-databases/blob/filestream-sql-server)|<span data-ttu-id="1a2aa-136">Describe cuándo usar el almacenamiento de FILESTREAM y cómo se integra el motor de base de datos de SQL Server con un sistema de archivos NTFS.</span><span class="sxs-lookup"><span data-stu-id="1a2aa-136">Describes when to use FILESTREAM storage and how it integrates the SQL Server Database Engine with an NTFS file system.</span></span>|
|[<span data-ttu-id="1a2aa-137">Crear aplicaciones cliente para datos FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="1a2aa-137">Create Client Applications for FILESTREAM Data</span></span>](/sql/relational-databases/blob/create-client-applications-for-filestream-data)|<span data-ttu-id="1a2aa-138">Describe las funciones de la API de Windows para trabajar con datos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="1a2aa-138">Describes the Windows API functions for working with FILESTREAM data.</span></span>|
|[<span data-ttu-id="1a2aa-139">FILESTREAM y otras características de SQL Server</span><span class="sxs-lookup"><span data-stu-id="1a2aa-139">FILESTREAM and Other SQL Server Features</span></span>](/sql/relational-databases/blob/filestream-compatibility-with-other-sql-server-features)|<span data-ttu-id="1a2aa-140">Proporciona consideraciones, directrices y limitaciones para usar datos FILESTREAM con otras características de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1a2aa-140">Provides considerations, guidelines and limitations for using FILESTREAM data with other features of SQL Server.</span></span>|

## <a name="see-also"></a><span data-ttu-id="1a2aa-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a2aa-141">See also</span></span>

- [<span data-ttu-id="1a2aa-142">Tipos de datos de SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1a2aa-142">SQL Server Data Types and ADO.NET</span></span>](sql-server-data-types.md)
- [<span data-ttu-id="1a2aa-143">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1a2aa-143">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="1a2aa-144">Seguridad de acceso del código y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1a2aa-144">Code Access Security and ADO.NET</span></span>](../code-access-security.md)
- [<span data-ttu-id="1a2aa-145">Datos binarios y datos de valores grandes de SQL Server</span><span class="sxs-lookup"><span data-stu-id="1a2aa-145">SQL Server Binary and Large-Value Data</span></span>](sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="1a2aa-146">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1a2aa-146">ADO.NET Overview</span></span>](../ado-net-overview.md)
