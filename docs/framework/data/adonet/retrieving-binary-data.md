---
title: Recuperar datos binarios
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 56c5a9e3-31f1-482f-bce0-ff1c41a658d0
ms.openlocfilehash: 11f7a81bc0d4b0e2a8d66387410d9a24503c7519
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150666"
---
# <a name="retrieving-binary-data"></a>Recuperar datos binarios

De forma predeterminada, **DataReader** carga los datos entrantes como una fila en cuanto una fila completa de datos está disponible. Sin embargo, los objetos binarios grandes (BLOB) se deben tratar de otra forma, ya que pueden llegar a contener grandes cantidades de datos (del orden de gigabytes) que no pueden almacenarse en una sola fila. El método **Command.ExecuteReader** tiene una sobrecarga que tomará un <xref:System.Data.CommandBehavior> argumento para modificar el comportamiento predeterminado de **DataReader**. Puede pasar <xref:System.Data.CommandBehavior.SequentialAccess> al método **ExecuteReader** para modificar el comportamiento predeterminado de **DataReader** de modo que, en lugar de cargar filas de datos, cargue los datos secuencialmente a medida que se reciben. Este sistema es idóneo para cargar BLOB y otras estructuras de datos grandes. Tenga en cuenta que este comportamiento puede depender del origen de datos. Por ejemplo, si se devuelve un BLOB desde Microsoft Access, el BLOB completo se cargará en memoria, en lugar de hacerlo secuencialmente a medida que se recibe.  
  
 Al establecer **DataReader** para usar **SequentialAccess**, es importante tener en cuenta la secuencia en la que se tiene acceso a los campos devueltos. El comportamiento predeterminado de **DataReader**, que carga una fila completa en cuanto está disponible, permite tener acceso a los campos devueltos en cualquier orden hasta que se lee la siguiente fila. Sin embargo, al usar **SequentialAccess** , debe tener acceso a los campos devueltos por **DataReader** en orden. Por ejemplo, si la consulta devuelve tres columnas y la tercera es un BLOB, debe devolver los valores de los campos primero y segundo antes de tener acceso a los datos BLOB del tercer campo. Si trata de tener acceso al tercer campo antes que al primero o el segundo, puede que éstos dejen de estar disponibles. Esto se debe a que **SequentialAccess** ha modificado **DataReader** para devolver datos en secuencia y los datos no están disponibles después de que **DataReader los haya leído** .  
  
 Al acceder a los datos en el campo BLOB, use los descriptores de acceso con tipo **GetBytes** o **GetChars** de **DataReader**, que rellenan una matriz con datos. También puede usar **GetString** para los datos de caracteres; sin. si desea conservar los recursos del sistema, es mejor que no cargue un valor BLOB completo en una sola variable de cadena. En lugar de ello, puede especificar un tamaño determinado de búfer para los datos que se van a devolver, así como la ubicación de comienzo para leer el primer byte o carácter de los datos devueltos. **GetBytes** y **GetChars** devolverán un `long` valor, que representa el número de bytes o caracteres devueltos. Si pasa una matriz null a **GetBytes** o **GetChars**, el valor Long devuelto será el número total de bytes o caracteres del BLOB. También puede especificar un índice de la matriz como posición de comienzo para la lectura de datos.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se devuelve el identificador y el logotipo del publicador de la base de datos de ejemplo **pubs** en Microsoft SQL Server. El identificador del publicador (`pub_id`) es un campo de caracteres, mientras que el logotipo es una imagen de BLOB. Dado que el campo **logo** es un mapa de bits, el ejemplo devuelve datos binarios mediante **GetBytes**. Tenga en cuenta que la necesidad de tener acceso a los datos de forma secuencial hace que en la fila actual de datos se tenga acceso al identificador de publicador antes que al logotipo.  
  
```vb  
' Assumes that connection is a valid SqlConnection object.  
Dim command As SqlCommand = New SqlCommand( _  
  "SELECT pub_id, logo FROM pub_info", connection)  
  
' Writes the BLOB to a file (*.bmp).  
Dim stream As FileStream
' Streams the binary data to the FileStream object.  
Dim writer As BinaryWriter
' The size of the BLOB buffer.  
Dim bufferSize As Integer = 100
' The BLOB byte() buffer to be filled by GetBytes.  
Dim outByte(bufferSize - 1) As Byte
' The bytes returned from GetBytes.  
Dim retval As Long
' The starting position in the BLOB output.  
Dim startIndex As Long = 0
  
' The publisher id to use in the file name.  
Dim pubID As String = ""
  
' Open the connection and read data into the DataReader.  
connection.Open()  
Dim reader As SqlDataReader = command.ExecuteReader(CommandBehavior.SequentialAccess)  
  
Do While reader.Read()  
  ' Get the publisher id, which must occur before getting the logo.  
  pubID = reader.GetString(0)  
  
  ' Create a file to hold the output.  
  stream = New FileStream( _  
    "logo" & pubID & ".bmp", FileMode.OpenOrCreate, FileAccess.Write)  
  writer = New BinaryWriter(stream)  
  
  ' Reset the starting byte for a new BLOB.  
  startIndex = 0  
  
  ' Read bytes into outByte() and retain the number of bytes returned.  
  retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize)  
  
  ' Continue while there are bytes beyond the size of the buffer.  
  Do While retval = bufferSize  
    writer.Write(outByte)  
    writer.Flush()  
  
    ' Reposition start index to end of the last buffer and fill buffer.  
    startIndex += bufferSize  
    retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize)  
  Loop  
  
  ' Write the remaining buffer.  
  writer.Write(outByte, 0 , retval - 1)  
  writer.Flush()  
  
  ' Close the output file.  
  writer.Close()  
  stream.Close()  
Loop  
  
' Close the reader and the connection.  
reader.Close()  
connection.Close()  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection object.  
SqlCommand command = new SqlCommand(  
  "SELECT pub_id, logo FROM pub_info", connection);  
  
// Writes the BLOB to a file (*.bmp).  
FileStream stream;
// Streams the BLOB to the FileStream object.  
BinaryWriter writer;
  
// Size of the BLOB buffer.  
int bufferSize = 100;
// The BLOB byte[] buffer to be filled by GetBytes.  
byte[] outByte = new byte[bufferSize];
// The bytes returned from GetBytes.  
long retval;
// The starting position in the BLOB output.  
long startIndex = 0;
  
// The publisher id to use in the file name.  
string pubID = "";
  
// Open the connection and read data into the DataReader.  
connection.Open();  
SqlDataReader reader = command.ExecuteReader(CommandBehavior.SequentialAccess);  
  
while (reader.Read())  
{  
  // Get the publisher id, which must occur before getting the logo.  
  pubID = reader.GetString(0);
  
  // Create a file to hold the output.  
  stream = new FileStream(  
    "logo" + pubID + ".bmp", FileMode.OpenOrCreate, FileAccess.Write);  
  writer = new BinaryWriter(stream);  
  
  // Reset the starting byte for the new BLOB.  
  startIndex = 0;  
  
  // Read bytes into outByte[] and retain the number of bytes returned.  
  retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize);  
  
  // Continue while there are bytes beyond the size of the buffer.  
  while (retval == bufferSize)  
  {  
    writer.Write(outByte);  
    writer.Flush();  
  
    // Reposition start index to end of last buffer and fill buffer.  
    startIndex += bufferSize;  
    retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize);  
  }  
  
  // Write the remaining buffer.  
  writer.Write(outByte, 0, (int)retval);  
  writer.Flush();  
  
  // Close the output file.  
  writer.Close();  
  stream.Close();  
}  
  
// Close the reader and the connection.  
reader.Close();  
connection.Close();  
```  
  
## <a name="see-also"></a>Vea también

- [SQL Server datos binarios y de valores grandes](./sql/sql-server-binary-and-large-value-data.md)
- [Información general de ADO.NET](ado-net-overview.md)
