---
title: Datos FILESTREAM
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bd8b845c-0f09-4295-b466-97ef106eefa8
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 77d6dbafc5a7c3afd9998fd8e9ae54ce60f90a45
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="filestream-data"></a>Datos FILESTREAM
El atributo de almacenamiento FILESTREAM es para los datos binarios (BLOB) almacenados en una columna varbinary(max). Antes de FILESTREAM, los datos binarios de almacenamiento necesitaban un control especial. Los datos no estructurados, como los documentos de texto, imágenes y vídeo, se suelen almacenar fuera de la base de datos, con lo que resulta difícil administrarlos.  
  
> [!NOTE]
>  Debe instalar .NET Framework 3.5 Service Pack 1 (o posterior) para trabajar con datos de FILESTREAM con SqlClient.  
  
 La especificación del atributo FILESTREAM en una columna varbinary(max) provoca que [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] almacene los datos en el sistema de archivos NTFS local en lugar de hacerlo en el archivo de base de datos. Aunque se almacenan por separado, puede usar las mismas instrucciones [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] admitidas para trabajar con los datos varbinary(max) almacenados en la base de datos.  
  
## <a name="sqlclient-support-for-filestream"></a>Compatibilidad de SqlClient con FILESTREAM  
 El proveedor de datos [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] para [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)], <xref:System.Data.SqlClient>, admite la lectura y escritura en datos FILESTREAM mediante la clase <xref:System.Data.SqlTypes.SqlFileStream> definida en el espacio de nombres <xref:System.Data.SqlTypes>. `SqlFileStream` hereda de la clase <xref:System.IO.Stream>, que proporciona métodos para leer y escribir en flujos de datos. La lectura de una secuencia transfiere los datos desde la secuencia a una estructura de datos como, por ejemplo, una matriz de bytes. La escritura transfiere los datos desde la estructura de datos hasta una secuencia.  
  
### <a name="creating-the-includessnoversionincludesssnoversion-mdmd-table"></a>Crear la tabla de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]  
 Las siguientes instrucciones [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] crean una tabla denominada employees e insertan una fila de datos. Una vez que ha habilitado el almacenamiento de FILESTREAM, puede usar esta tabla junto con los ejemplos de código que figuran a continuación. Al final de este tema se encuentran los vínculos a los recursos en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  
  
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
  
### <a name="example-reading-overwriting-and-inserting-filestream-data"></a>Ejemplo: leer, sobrescribir e insertar datos de FILESTREAM  
 En el ejemplo siguiente se muestra cómo se leen datos de un FILESTREAM. El código obtiene la ruta de acceso lógica del archivo, y establece `FileAccess` en `Read` y `FileOptions` en `SequentialScan`. El código lee después los bytes del SqlFileStream en el búfer. Después los bytes se escriben en la ventana de la consola.  
  
 En el ejemplo se muestra también cómo se escriben datos en un FILESTREAM en el que se sobrescriben todos los datos existentes. El código obtiene la ruta de acceso lógica del archivo y crea `SqlFileStream`, y establece `FileAccess` en `Write` y `FileOptions` en `SequentialScan`. Se escribe un byte único en `SqlFileStream`, que remplaza los datos del archivo.  
  
 En el ejemplo también se muestra cómo se escriben datos en un FILESTREAM mediante el método Seek para anexar los datos al final del archivo. El código obtiene la ruta de acceso lógica del archivo y crea `SqlFileStream`, y establece `FileAccess` en `ReadWrite` y `FileOptions` en `SequentialScan`. El código usa el método Seek para buscar hasta el final del archivo, y anexa un byte único al archivo existente.  
  
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
  
                        using (Stream fileStream = new SqlFileStream(path, transactionContext, FileAccess.Write, FileOptions.SequentialScan, allocationSize: 0))  
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
} using (SqlConnection connection = new SqlConnection(  
    connStringBuilder.ToString()))  
{  
    connection.Open();  
  
    SqlCommand command = new SqlCommand("", connection);  
    command.CommandText = "select Top(1) Photo.PathName(), "  
    + "GET_FILESTREAM_TRANSACTION_CONTEXT () from employees";  
  
    SqlTransaction tran = connection.BeginTransaction(  
        System.Data.IsolationLevel.ReadCommitted);  
    command.Transaction = tran;  
  
    using (SqlDataReader reader = command.ExecuteReader())  
    {  
        while (reader.Read())  
        {  
            // Get the pointer for file  
            string path = reader.GetString(0);  
            byte[] transactionContext = reader.GetSqlBytes(1).Buffer;  
  
            FileStream fileStream = new SqlFileStream(path,  
                (byte[])reader.GetValue(1),  
                FileAccess.ReadWrite,  
                FileOptions.SequentialScan, 0);  
  
            // Seek to the end of the file  
            fs.Seek(0, SeekOrigin.End);  
  
            // Append a single byte   
            fileStream.WriteByte(0x01);  
            fileStream.Close();  
        }  
    }  
    tran.Commit();  
}  
```  
  
 Para obtener otro ejemplo, vea [cómo almacenar y recuperar datos binarios en una columna de secuencia de archivo](http://www.codeproject.com/Articles/32216/How-to-store-and-fetch-binary-data-into-a-file-str).  
  
## <a name="resources-in-includessnoversionincludesssnoversion-mdmd-books-online"></a>Recursos en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]  
 La documentación completa de FILESTREAM se encuentra en las secciones siguientes de los Libros en pantalla de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  
  
|Tema|Descripción|  
|-----------|-----------------|  
|[Diseñar e implementar almacenamiento FILESTREAM](http://msdn2.microsoft.com/library/bb895234\(SQL.105\).aspx)|Proporciona vínculos a la documentación de FILESTREAM y a los temas relacionados.|  
|[Información general de FILESTREAM](http://msdn2.microsoft.com/library/bb933993\(SQL.105\).aspx)|Describe cuándo se usa el almacenamiento de FILESTREAM y cómo éste integra el Motor de base de datos de SQL Server con un sistema de archivos NTFS.|  
|[Introducción a almacenamiento de FILESTREAM](http://msdn.microsoft.com/library/bb933995\(SQL.105\).aspx)|Describe cómo habilitar FILESTREAM en una instancia de SQL Server, cómo crear una base de datos y una tabla para los datos de un FILESTREAM almacenados y cómo manipular filas que contienen datos de un FILESTREAM.|  
|[Usar el almacenamiento FILESTREAM en aplicaciones cliente](http://msdn.microsoft.com/library/bb933877\(SQL.105\).aspx)|Describe las funciones de la API de Win32 para trabajar con datos de un FILESTREAM.|  
|[FILESTREAM y otras características de SQL Server](http://msdn.microsoft.com/library/bb895334\(SQL.105\).aspx)|Proporciona consideraciones, instrucciones y limitaciones para usar datos de un FILESTREAM con otras características de SQL Server.|  
  
## <a name="see-also"></a>Vea también  
 [Tipos de datos de SQL Server y ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [Recuperar y modificar datos en ADO.NET](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Seguridad de acceso del código y ADO.NET](../../../../../docs/framework/data/adonet/code-access-security.md)  
 [Datos binarios y datos de valores grandes de SQL Server](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
