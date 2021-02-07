---
description: Más información acerca de cómo recuperar datos binarios
title: Recuperar datos binarios
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 56c5a9e3-31f1-482f-bce0-ff1c41a658d0
ms.openlocfilehash: 4304dd19b8a861baf936686edb858d7cf4da5757
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99663448"
---
# <a name="retrieving-binary-data"></a>Recuperar datos binarios

El objeto **DataReader** carga de forma predeterminada los datos que recibe en una fila, siempre que hay disponibles suficientes datos para llenarla. Sin embargo, los objetos binarios grandes (BLOB) se deben tratar de otra forma, ya que pueden llegar a contener grandes cantidades de datos (del orden de gigabytes) que no pueden almacenarse en una sola fila. El método **Command.ExecuteReader** se puede sobrecargar para aceptar un argumento <xref:System.Data.CommandBehavior> y modificar el comportamiento predeterminado de **DataReader**. Puede pasar <xref:System.Data.CommandBehavior.SequentialAccess> al método **ExecuteReader** para modificar el comportamiento predeterminado de **DataReader** de forma que en lugar de cargar los datos por filas, los vaya cargando secuencialmente a medida que los vaya recibiendo. Este sistema es idóneo para cargar BLOB y otras estructuras de datos grandes. Tenga en cuenta que este comportamiento puede depender del origen de datos. Por ejemplo, si se devuelve un BLOB desde Microsoft Access, el BLOB completo se cargará en memoria, en lugar de hacerlo secuencialmente a medida que se recibe.  
  
 Al configurar **DataReader** para que utilice **SequentialAccess** debe tener en cuenta la secuencia en que va a tener acceso a los campos devueltos. El comportamiento predeterminado de **DataReader**, consistente en cargar una fila completa de datos en cuanto hay datos suficientes, permite tener acceso a los campos devueltos en cualquier orden hasta que se lee la fila siguiente. Sin embargo, al utilizar **SequentialAccess** es necesario tener acceso a los campos que devuelve **DataReader** en el orden adecuado. Por ejemplo, si la consulta devuelve tres columnas y la tercera es un BLOB, debe devolver los valores de los campos primero y segundo antes de tener acceso a los datos BLOB del tercer campo. Si trata de tener acceso al tercer campo antes que al primero o el segundo, puede que éstos dejen de estar disponibles. Esto se debe a que **SequentialAccess** cambia la forma en que el **DataReader** devuelve los datos, haciendo que lo haga de forma secuencial con lo que los datos dejan de estar disponibles en el momento en que el **DataReader** lee datos posteriores.  
  
 Cuando intente obtener acceso a los datos del campo BLOB, utilice los descriptores de acceso con información de tipos **GetBytes** o **GetChars** del **DataReader**, que llenan una matriz con los datos. También puede usar **GetString** para los datos de caracteres; sin. si desea conservar los recursos del sistema, es mejor que no cargue un valor BLOB completo en una sola variable de cadena. En lugar de ello, puede especificar un tamaño determinado de búfer para los datos que se van a devolver, así como la ubicación de comienzo para leer el primer byte o carácter de los datos devueltos. **GetBytes** y **GetChars** devuelven un valor de tipo `long` que representa el número de bytes o caracteres devueltos. Si pasa una matriz con valores null a **GetBytes** o **GetChars**, el valor de tipo long devuelto contiene el número total de bytes o caracteres del BLOB. También puede especificar un índice de la matriz como posición de comienzo para la lectura de datos.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se devuelve el identificador y el logotipo del publicador de la base de datos de ejemplo **pubs** en Microsoft SQL Server. El identificador del publicador (`pub_id`) es un campo de caracteres, mientras que el logotipo es una imagen de BLOB. Como el campo **logo** es un mapa de bits, el ejemplo devuelve datos binarios mediante **GetBytes**. Tenga en cuenta que la necesidad de tener acceso a los datos de forma secuencial hace que en la fila actual de datos se tenga acceso al identificador de publicador antes que al logotipo.  
  
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
  
## <a name="see-also"></a>Consulte también

- [Datos binarios y datos de valores grandes de SQL Server](./sql/sql-server-binary-and-large-value-data.md)
- [Información general de ADO.NET](ado-net-overview.md)
