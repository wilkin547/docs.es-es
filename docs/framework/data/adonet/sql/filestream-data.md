---
title: Datos FILESTREAM
ms.date: 03/30/2017
ms.assetid: bd8b845c-0f09-4295-b466-97ef106eefa8
ms.openlocfilehash: eef03d171d288cb2bc62c3aaa477a95a5ce718c3
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44221979"
---
# <a name="filestream-data"></a><span data-ttu-id="425ad-102">Datos FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="425ad-102">FILESTREAM Data</span></span>
<span data-ttu-id="425ad-103">El atributo de almacenamiento FILESTREAM es para los datos binarios (BLOB) almacenados en una columna varbinary(max).</span><span class="sxs-lookup"><span data-stu-id="425ad-103">The FILESTREAM storage attribute is for binary (BLOB) data stored in a varbinary(max) column.</span></span> <span data-ttu-id="425ad-104">Antes de FILESTREAM, los datos binarios de almacenamiento necesitaban un control especial.</span><span class="sxs-lookup"><span data-stu-id="425ad-104">Before FILESTREAM, storing binary data required special handling.</span></span> <span data-ttu-id="425ad-105">Los datos no estructurados, como los documentos de texto, imágenes y vídeo, se suelen almacenar fuera de la base de datos, con lo que resulta difícil administrarlos.</span><span class="sxs-lookup"><span data-stu-id="425ad-105">Unstructured data, such as text documents, images and video, is often stored outside of the database, making it difficult to manage.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="425ad-106">Debe instalar .NET Framework 3.5 Service Pack 1 (o posterior) para trabajar con datos de FILESTREAM con SqlClient.</span><span class="sxs-lookup"><span data-stu-id="425ad-106">You must install the .NET Framework 3.5 SP1 (or later) to work with FILESTREAM data using SqlClient.</span></span>  
  
 <span data-ttu-id="425ad-107">La especificación del atributo FILESTREAM en una columna varbinary(max) provoca que SQL Server almacene los datos en el sistema de archivos NTFS local en lugar de hacerlo en el archivo de base de datos.</span><span class="sxs-lookup"><span data-stu-id="425ad-107">Specifying the FILESTREAM attribute on a varbinary(max) column causes SQL Server to store the data on the local NTFS file system instead of in the database file.</span></span> <span data-ttu-id="425ad-108">Aunque se almacenan por separado, puede usar las mismas instrucciones [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] admitidas para trabajar con los datos varbinary(max) almacenados en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="425ad-108">Although it is stored separately, you can use the same [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] statements that are supported for working with varbinary(max) data that is stored in the database.</span></span>  
  
## <a name="sqlclient-support-for-filestream"></a><span data-ttu-id="425ad-109">Compatibilidad de SqlClient con FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="425ad-109">SqlClient Support for FILESTREAM</span></span>  
 <span data-ttu-id="425ad-110">El [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] proveedor de datos para SQL Server, <xref:System.Data.SqlClient>, admite la lectura y escritura de datos de FILESTREAM mediante el <xref:System.Data.SqlTypes.SqlFileStream> clase definida en el <xref:System.Data.SqlTypes> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="425ad-110">The [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] Data Provider for SQL Server, <xref:System.Data.SqlClient>, supports reading and writing to FILESTREAM data using the <xref:System.Data.SqlTypes.SqlFileStream> class defined in the <xref:System.Data.SqlTypes> namespace.</span></span> <span data-ttu-id="425ad-111">`SqlFileStream` hereda de la clase <xref:System.IO.Stream>, que proporciona métodos para leer y escribir en flujos de datos.</span><span class="sxs-lookup"><span data-stu-id="425ad-111">`SqlFileStream` inherits from the <xref:System.IO.Stream> class, which provides methods for reading and writing to streams of data.</span></span> <span data-ttu-id="425ad-112">La lectura de una secuencia transfiere los datos desde la secuencia a una estructura de datos como, por ejemplo, una matriz de bytes.</span><span class="sxs-lookup"><span data-stu-id="425ad-112">Reading from a stream transfers data from the stream into a data structure, such as an array of bytes.</span></span> <span data-ttu-id="425ad-113">La escritura transfiere los datos desde la estructura de datos hasta una secuencia.</span><span class="sxs-lookup"><span data-stu-id="425ad-113">Writing transfers the data from the data structure into a stream.</span></span>  
  
### <a name="creating-the-sql-server-table"></a><span data-ttu-id="425ad-114">Crear la tabla de SQL Server</span><span class="sxs-lookup"><span data-stu-id="425ad-114">Creating the SQL Server Table</span></span>  
 <span data-ttu-id="425ad-115">Las siguientes instrucciones [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] crean una tabla denominada employees e insertan una fila de datos.</span><span class="sxs-lookup"><span data-stu-id="425ad-115">The following [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] statements creates a table named employees and inserts a row of data.</span></span> <span data-ttu-id="425ad-116">Una vez que ha habilitado el almacenamiento de FILESTREAM, puede usar esta tabla junto con los ejemplos de código que figuran a continuación.</span><span class="sxs-lookup"><span data-stu-id="425ad-116">Once you have enabled FILESTREAM storage, you can use this table in conjunction with the code examples that follow.</span></span> <span data-ttu-id="425ad-117">Los vínculos a recursos en los libros en pantalla de SQL Server se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="425ad-117">The links to resources in SQL Server Books Online are located at the end of this topic.</span></span>  
  
```  
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
  
### <a name="example-reading-overwriting-and-inserting-filestream-data"></a><span data-ttu-id="425ad-118">Ejemplo: leer, sobrescribir e insertar datos de FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="425ad-118">Example: Reading, Overwriting, and Inserting FILESTREAM Data</span></span>  
 <span data-ttu-id="425ad-119">En el ejemplo siguiente se muestra cómo se leen datos de un FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="425ad-119">The following sample demonstrates how to read data from a FILESTREAM.</span></span> <span data-ttu-id="425ad-120">El código obtiene la ruta de acceso lógica del archivo, y establece `FileAccess` en `Read` y `FileOptions` en `SequentialScan`.</span><span class="sxs-lookup"><span data-stu-id="425ad-120">The code gets the logical path to the file, setting the `FileAccess` to `Read` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="425ad-121">El código lee después los bytes del SqlFileStream en el búfer.</span><span class="sxs-lookup"><span data-stu-id="425ad-121">The code then reads the bytes from the SqlFileStream into the buffer.</span></span> <span data-ttu-id="425ad-122">Después los bytes se escriben en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="425ad-122">The bytes are then written to the console window.</span></span>  
  
 <span data-ttu-id="425ad-123">En el ejemplo se muestra también cómo se escriben datos en un FILESTREAM en el que se sobrescriben todos los datos existentes.</span><span class="sxs-lookup"><span data-stu-id="425ad-123">The sample also demonstrates how to write data to a FILESTREAM in which all existing data is overwritten.</span></span> <span data-ttu-id="425ad-124">El código obtiene la ruta de acceso lógica del archivo y crea `SqlFileStream`, y establece `FileAccess` en `Write` y `FileOptions` en `SequentialScan`.</span><span class="sxs-lookup"><span data-stu-id="425ad-124">The code gets the logical path to the file and creates the `SqlFileStream`, setting the `FileAccess` to `Write` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="425ad-125">Se escribe un byte único en `SqlFileStream`, que remplaza los datos del archivo.</span><span class="sxs-lookup"><span data-stu-id="425ad-125">A single byte is written to the `SqlFileStream`, replacing any data in the file.</span></span>  
  
 <span data-ttu-id="425ad-126">En el ejemplo también se muestra cómo se escriben datos en un FILESTREAM mediante el método Seek para anexar los datos al final del archivo.</span><span class="sxs-lookup"><span data-stu-id="425ad-126">The sample also demonstrates how to write data to a FILESTREAM by using the Seek method to append data to the end of the file.</span></span> <span data-ttu-id="425ad-127">El código obtiene la ruta de acceso lógica del archivo y crea `SqlFileStream`, y establece `FileAccess` en `ReadWrite` y `FileOptions` en `SequentialScan`.</span><span class="sxs-lookup"><span data-stu-id="425ad-127">The code gets the logical path to the file and creates the `SqlFileStream`, setting the `FileAccess` to `ReadWrite` and the `FileOptions` to `SequentialScan`.</span></span> <span data-ttu-id="425ad-128">El código usa el método Seek para buscar hasta el final del archivo, y anexa un byte único al archivo existente.</span><span class="sxs-lookup"><span data-stu-id="425ad-128">The code uses the Seek method to seek to the end of the file, appending a single byte to the existing file.</span></span>  
  
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
            ReadFilestream(builder);  
            OverwriteFilestream(builder);  
            InsertFilestream(builder);  
  
            Console.WriteLine("Done");  
        }  
  
        private static void ReadFilestream(SqlConnectionStringBuilder connStringBuilder)  
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
  
        private static void OverwriteFilestream(SqlConnectionStringBuilder connStringBuilder)  
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
  
        private static void InsertFilestream(SqlConnectionStringBuilder connStringBuilder)  
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
  
 <span data-ttu-id="425ad-129">Para obtener otro ejemplo, vea [cómo almacenar y recuperar datos binarios en una columna de secuencia de archivo](http://www.codeproject.com/Articles/32216/How-to-store-and-fetch-binary-data-into-a-file-str).</span><span class="sxs-lookup"><span data-stu-id="425ad-129">For another sample, see [How to store and fetch binary data into a file stream column](http://www.codeproject.com/Articles/32216/How-to-store-and-fetch-binary-data-into-a-file-str).</span></span>  
  
## <a name="resources-in-sql-server-books-online"></a><span data-ttu-id="425ad-130">Recursos en los Libros en pantalla de SQL Server</span><span class="sxs-lookup"><span data-stu-id="425ad-130">Resources in SQL Server Books Online</span></span>  
 <span data-ttu-id="425ad-131">La documentación completa de FILESTREAM se encuentra en las secciones siguientes en los libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="425ad-131">The complete documentation for FILESTREAM is located in the following sections in SQL Server Books Online.</span></span>  
  
|<span data-ttu-id="425ad-132">Tema</span><span class="sxs-lookup"><span data-stu-id="425ad-132">Topic</span></span>|<span data-ttu-id="425ad-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="425ad-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="425ad-134">[Diseñar e implementar almacenamiento FILESTREAM](http://msdn2.microsoft.com/library/bb895234\(SQL.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="425ad-134">[Designing and Implementing FILESTREAM Storage](http://msdn2.microsoft.com/library/bb895234\(SQL.105\).aspx)</span></span>|<span data-ttu-id="425ad-135">Proporciona vínculos a la documentación de FILESTREAM y a los temas relacionados.</span><span class="sxs-lookup"><span data-stu-id="425ad-135">Provides links to FILESTREAM documentation and related topics.</span></span>|  
|<span data-ttu-id="425ad-136">[Información general de FILESTREAM](http://msdn2.microsoft.com/library/bb933993\(SQL.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="425ad-136">[FILESTREAM Overview](http://msdn2.microsoft.com/library/bb933993\(SQL.105\).aspx)</span></span>|<span data-ttu-id="425ad-137">Describe cuándo se usa el almacenamiento de FILESTREAM y cómo éste integra el Motor de base de datos de SQL Server con un sistema de archivos NTFS.</span><span class="sxs-lookup"><span data-stu-id="425ad-137">Describes when to use FILESTREAM storage and how it integrates the SQL Server Database Engine with an NTFS file system.</span></span>|  
|<span data-ttu-id="425ad-138">[Introducción al almacenamiento FILESTREAM](https://msdn.microsoft.com/library/bb933995\(SQL.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="425ad-138">[Getting Started with FILESTREAM Storage](https://msdn.microsoft.com/library/bb933995\(SQL.105\).aspx)</span></span>|<span data-ttu-id="425ad-139">Describe cómo habilitar FILESTREAM en una instancia de SQL Server, cómo crear una base de datos y una tabla para los datos de un FILESTREAM almacenados y cómo manipular filas que contienen datos de un FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="425ad-139">Describes how to enable FILESTREAM on an instance of SQL Server, how to create a database and a table to stored FILESTREAM data, and how to manipulate rows containing FILESTREAM data.</span></span>|  
|<span data-ttu-id="425ad-140">[Usar el almacenamiento FILESTREAM en aplicaciones cliente](https://msdn.microsoft.com/library/bb933877\(SQL.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="425ad-140">[Using FILESTREAM Storage in Client Applications](https://msdn.microsoft.com/library/bb933877\(SQL.105\).aspx)</span></span>|<span data-ttu-id="425ad-141">Describe las funciones de la API de Win32 para trabajar con datos de un FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="425ad-141">Describes the Win32 API functions for working with FILESTREAM data.</span></span>|  
|[<span data-ttu-id="425ad-142">FILESTREAM y otras características de SQL Server</span><span class="sxs-lookup"><span data-stu-id="425ad-142">FILESTREAM and Other SQL Server Features</span></span>](/sql/relational-databases/blob/filestream-compatibility-with-other-sql-server-features)|<span data-ttu-id="425ad-143">Proporciona consideraciones, instrucciones y limitaciones para usar datos de un FILESTREAM con otras características de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="425ad-143">Provides considerations, guidelines and limitations for using FILESTREAM data with other features of SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="425ad-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="425ad-144">See Also</span></span>  
 [<span data-ttu-id="425ad-145">Tipos de datos de SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="425ad-145">SQL Server Data Types and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [<span data-ttu-id="425ad-146">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="425ad-146">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="425ad-147">Seguridad de acceso del código y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="425ad-147">Code Access Security and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/code-access-security.md)  
 [<span data-ttu-id="425ad-148">Datos binarios y datos de valores grandes de SQL Server</span><span class="sxs-lookup"><span data-stu-id="425ad-148">SQL Server Binary and Large-Value Data</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 [<span data-ttu-id="425ad-149">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="425ad-149">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
