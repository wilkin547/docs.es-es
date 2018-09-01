---
title: Insertar una imagen desde un archivo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 35900aa2-5615-4174-8212-ba184c6b82fb
ms.openlocfilehash: d3cbf4fa0eb0b261bb752370c95cdfb2bca0b7e6
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43387469"
---
# <a name="inserting-an-image-from-a-file"></a>Insertar una imagen desde un archivo
Un objeto binario grande (BLOB) se puede escribir en una base de datos en forma de datos binarios o de caracteres, según el tipo de campo del origen de datos. BLOB es un término genérico que hace referencia a los tipos de datos `text`, `ntext` e `image`, que suelen contener documentos e imágenes.  
  
 Para escribir un valor BLOB en la base de datos, utilice la instrucción INSERT o UPDATE correspondiente y pase el valor BLOB como parámetro de entrada (consulte [configurar parámetros y tipos de datos de parámetro](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)). Si el BLOB se almacena como texto, por ejemplo, un campo `text` de SQL Server, puede pasar dicho BLOB como parámetro de cadena. Si el BLOB se almacena en formato binario, por ejemplo, un campo `image` de SQL Server, puede pasar una matriz de tipo `byte` como parámetro binario.  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo de código se agregan datos de los empleados a la tabla Employees de la base de datos Northwind. Se lee una foto del empleado desde un archivo y se agrega al campo Photo de la tabla, que es un campo de imagen.  
  
```vb  
Public Shared Sub AddEmployee( _  
  lastName As String, _  
  firstName As String, _  
  title As String, _  
  hireDate As DateTime, _  
  reportsTo As Integer, _  
  photoFilePath As String, _  
  connectionString As String)  
  
  Dim photo() as Byte = GetPhoto(photoFilePath)  
  
  Using connection As SqlConnection = New SqlConnection( _  
    connectionString)  
  
  Dim command As SqlCommand = New SqlCommand( _  
    "INSERT INTO Employees (LastName, FirstName, Title, " & _  
    "HireDate, ReportsTo, Photo) " & _  
    "Values(@LastName, @FirstName, @Title, " & _  
    "@HireDate, @ReportsTo, @Photo)", connection)   
  
  command.Parameters.Add("@LastName",  _  
    SqlDbType.NVarChar, 20).Value = lastName  
  command.Parameters.Add("@FirstName", _  
    SqlDbType.NVarChar, 10).Value = firstName  
  command.Parameters.Add("@Title", _  
    SqlDbType.NVarChar, 30).Value = title  
  command.Parameters.Add("@HireDate", _  
    SqlDbType.DateTime).Value = hireDate  
  command.Parameters.Add("@ReportsTo", _  
    SqlDbType.Int).Value = reportsTo  
  
  command.Parameters.Add("@Photo", _  
    SqlDbType.Image, photo.Length).Value = photo  
  
  connection.Open()  
  command.ExecuteNonQuery()  
  
  End Using  
End Sub  
  
Public Shared Function GetPhoto(filePath As String) As Byte()  
  Dim stream As FileStream = new FileStream( _  
     filePath, FileMode.Open, FileAccess.Read)  
  Dim reader As BinaryReader = new BinaryReader(stream)  
  
  Dim photo() As Byte = reader.ReadBytes(stream.Length)  
  
  reader.Close()  
  stream.Close()  
  
  Return photo  
End Function  
```  
  
```csharp  
public static void AddEmployee(  
  string lastName,   
  string firstName,   
  string title,   
  DateTime hireDate,   
  int reportsTo,   
  string photoFilePath,   
  string connectionString)  
{  
  byte[] photo = GetPhoto(photoFilePath);  
  
  using (SqlConnection connection = new SqlConnection(  
    connectionString))  
  
  SqlCommand command = new SqlCommand(  
    "INSERT INTO Employees (LastName, FirstName, " +  
    "Title, HireDate, ReportsTo, Photo) " +  
    "Values(@LastName, @FirstName, @Title, " +  
    "@HireDate, @ReportsTo, @Photo)", connection);   
  
  command.Parameters.Add("@LastName",    
     SqlDbType.NVarChar, 20).Value = lastName;  
  command.Parameters.Add("@FirstName",   
      SqlDbType.NVarChar, 10).Value = firstName;  
  command.Parameters.Add("@Title",       
      SqlDbType.NVarChar, 30).Value = title;  
  command.Parameters.Add("@HireDate",   
       SqlDbType.DateTime).Value = hireDate;  
  command.Parameters.Add("@ReportsTo",   
      SqlDbType.Int).Value = reportsTo;  
  
  command.Parameters.Add("@Photo",  
      SqlDbType.Image, photo.Length).Value = photo;  
  
  connection.Open();  
  command.ExecuteNonQuery();  
  }  
}  
  
public static byte[] GetPhoto(string filePath)  
{  
  FileStream stream = new FileStream(  
      filePath, FileMode.Open, FileAccess.Read);  
  BinaryReader reader = new BinaryReader(stream);  
  
  byte[] photo = reader.ReadBytes((int)stream.Length);  
  
  reader.Close();  
  stream.Close();  
  
  return photo;  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Uso de comandos para modificar datos](../../../../../docs/framework/data/adonet/using-commands-to-modify-data.md)  
 [Recuperación de datos binarios](../../../../../docs/framework/data/adonet/retrieving-binary-data.md)  
 [Datos binarios y datos de valores grandes de SQL Server](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 [Asignaciones de tipos de datos de SQL Server](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
