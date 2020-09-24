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
# <a name="retrieving-binary-data"></a><span data-ttu-id="8376d-102">Recuperar datos binarios</span><span class="sxs-lookup"><span data-stu-id="8376d-102">Retrieving Binary Data</span></span>

<span data-ttu-id="8376d-103">De forma predeterminada, **DataReader** carga los datos entrantes como una fila en cuanto una fila completa de datos está disponible.</span><span class="sxs-lookup"><span data-stu-id="8376d-103">By default, the **DataReader** loads incoming data as a row as soon as an entire row of data is available.</span></span> <span data-ttu-id="8376d-104">Sin embargo, los objetos binarios grandes (BLOB) se deben tratar de otra forma, ya que pueden llegar a contener grandes cantidades de datos (del orden de gigabytes) que no pueden almacenarse en una sola fila.</span><span class="sxs-lookup"><span data-stu-id="8376d-104">Binary large objects (BLOBs) need different treatment, however, because they can contain gigabytes of data that cannot be contained in a single row.</span></span> <span data-ttu-id="8376d-105">El método **Command.ExecuteReader** tiene una sobrecarga que tomará un <xref:System.Data.CommandBehavior> argumento para modificar el comportamiento predeterminado de **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="8376d-105">The **Command.ExecuteReader** method has an overload that will take a <xref:System.Data.CommandBehavior> argument to modify the default behavior of the **DataReader**.</span></span> <span data-ttu-id="8376d-106">Puede pasar <xref:System.Data.CommandBehavior.SequentialAccess> al método **ExecuteReader** para modificar el comportamiento predeterminado de **DataReader** de modo que, en lugar de cargar filas de datos, cargue los datos secuencialmente a medida que se reciben.</span><span class="sxs-lookup"><span data-stu-id="8376d-106">You can pass <xref:System.Data.CommandBehavior.SequentialAccess> to the **ExecuteReader** method to modify the default behavior of the **DataReader** so that instead of loading rows of data, it will load data sequentially as it is received.</span></span> <span data-ttu-id="8376d-107">Este sistema es idóneo para cargar BLOB y otras estructuras de datos grandes.</span><span class="sxs-lookup"><span data-stu-id="8376d-107">This is ideal for loading BLOBs or other large data structures.</span></span> <span data-ttu-id="8376d-108">Tenga en cuenta que este comportamiento puede depender del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="8376d-108">Note that this behavior may depend on your data source.</span></span> <span data-ttu-id="8376d-109">Por ejemplo, si se devuelve un BLOB desde Microsoft Access, el BLOB completo se cargará en memoria, en lugar de hacerlo secuencialmente a medida que se recibe.</span><span class="sxs-lookup"><span data-stu-id="8376d-109">For example, returning a BLOB from Microsoft Access will load the entire BLOB being loaded into memory, rather than sequentially as it is received.</span></span>  
  
 <span data-ttu-id="8376d-110">Al establecer **DataReader** para usar **SequentialAccess**, es importante tener en cuenta la secuencia en la que se tiene acceso a los campos devueltos.</span><span class="sxs-lookup"><span data-stu-id="8376d-110">When setting the **DataReader** to use **SequentialAccess**, it is important to note the sequence in which you access the fields returned.</span></span> <span data-ttu-id="8376d-111">El comportamiento predeterminado de **DataReader**, que carga una fila completa en cuanto está disponible, permite tener acceso a los campos devueltos en cualquier orden hasta que se lee la siguiente fila.</span><span class="sxs-lookup"><span data-stu-id="8376d-111">The default behavior of the **DataReader**, which loads an entire row as soon as it is available, allows you to access the fields returned in any order until the next row is read.</span></span> <span data-ttu-id="8376d-112">Sin embargo, al usar **SequentialAccess** , debe tener acceso a los campos devueltos por **DataReader** en orden.</span><span class="sxs-lookup"><span data-stu-id="8376d-112">When using **SequentialAccess** however, you must access the fields returned by the **DataReader** in order.</span></span> <span data-ttu-id="8376d-113">Por ejemplo, si la consulta devuelve tres columnas y la tercera es un BLOB, debe devolver los valores de los campos primero y segundo antes de tener acceso a los datos BLOB del tercer campo.</span><span class="sxs-lookup"><span data-stu-id="8376d-113">For example, if your query returns three columns, the third of which is a BLOB, you must return the values of the first and second fields before accessing the BLOB data in the third field.</span></span> <span data-ttu-id="8376d-114">Si trata de tener acceso al tercer campo antes que al primero o el segundo, puede que éstos dejen de estar disponibles.</span><span class="sxs-lookup"><span data-stu-id="8376d-114">If you access the third field before the first or second fields, the first and second field values are no longer available.</span></span> <span data-ttu-id="8376d-115">Esto se debe a que **SequentialAccess** ha modificado **DataReader** para devolver datos en secuencia y los datos no están disponibles después de que **DataReader los haya leído** .</span><span class="sxs-lookup"><span data-stu-id="8376d-115">This is because **SequentialAccess** has modified the **DataReader** to return data in sequence and the data is not available after the **DataReader** has read past it.</span></span>  
  
 <span data-ttu-id="8376d-116">Al acceder a los datos en el campo BLOB, use los descriptores de acceso con tipo **GetBytes** o **GetChars** de **DataReader**, que rellenan una matriz con datos.</span><span class="sxs-lookup"><span data-stu-id="8376d-116">When accessing the data in the BLOB field, use the **GetBytes** or **GetChars** typed accessors of the **DataReader**, which fill an array with data.</span></span> <span data-ttu-id="8376d-117">También puede usar **GetString** para los datos de caracteres; sin.</span><span class="sxs-lookup"><span data-stu-id="8376d-117">You can also use **GetString** for character data; however.</span></span> <span data-ttu-id="8376d-118">si desea conservar los recursos del sistema, es mejor que no cargue un valor BLOB completo en una sola variable de cadena.</span><span class="sxs-lookup"><span data-stu-id="8376d-118">to conserve system resources you might not want to load an entire BLOB value into a single string variable.</span></span> <span data-ttu-id="8376d-119">En lugar de ello, puede especificar un tamaño determinado de búfer para los datos que se van a devolver, así como la ubicación de comienzo para leer el primer byte o carácter de los datos devueltos.</span><span class="sxs-lookup"><span data-stu-id="8376d-119">You can instead specify a specific buffer size of data to be returned, and a starting location for the first byte or character to be read from the returned data.</span></span> <span data-ttu-id="8376d-120">**GetBytes** y **GetChars** devolverán un `long` valor, que representa el número de bytes o caracteres devueltos.</span><span class="sxs-lookup"><span data-stu-id="8376d-120">**GetBytes** and **GetChars** will return a `long` value, which represents the number of bytes or characters returned.</span></span> <span data-ttu-id="8376d-121">Si pasa una matriz null a **GetBytes** o **GetChars**, el valor Long devuelto será el número total de bytes o caracteres del BLOB.</span><span class="sxs-lookup"><span data-stu-id="8376d-121">If you pass a null array to **GetBytes** or **GetChars**, the long value returned will be the total number of bytes or characters in the BLOB.</span></span> <span data-ttu-id="8376d-122">También puede especificar un índice de la matriz como posición de comienzo para la lectura de datos.</span><span class="sxs-lookup"><span data-stu-id="8376d-122">You can optionally specify an index in the array as a starting position for the data being read.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8376d-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8376d-123">Example</span></span>  

 <span data-ttu-id="8376d-124">En el ejemplo siguiente se devuelve el identificador y el logotipo del publicador de la base de datos de ejemplo **pubs** en Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8376d-124">The following example returns the publisher ID and logo from the **pubs** sample database in Microsoft SQL Server.</span></span> <span data-ttu-id="8376d-125">El identificador del publicador (`pub_id`) es un campo de caracteres, mientras que el logotipo es una imagen de BLOB.</span><span class="sxs-lookup"><span data-stu-id="8376d-125">The publisher ID (`pub_id`) is a character field, and the logo is an image, which is a BLOB.</span></span> <span data-ttu-id="8376d-126">Dado que el campo **logo** es un mapa de bits, el ejemplo devuelve datos binarios mediante **GetBytes**.</span><span class="sxs-lookup"><span data-stu-id="8376d-126">Because the **logo** field is a bitmap, the example returns binary data using **GetBytes**.</span></span> <span data-ttu-id="8376d-127">Tenga en cuenta que la necesidad de tener acceso a los datos de forma secuencial hace que en la fila actual de datos se tenga acceso al identificador de publicador antes que al logotipo.</span><span class="sxs-lookup"><span data-stu-id="8376d-127">Notice that the publisher ID is accessed for the current row of data before the logo, because the fields must be accessed sequentially.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8376d-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="8376d-128">See also</span></span>

- [<span data-ttu-id="8376d-129">SQL Server datos binarios y de valores grandes</span><span class="sxs-lookup"><span data-stu-id="8376d-129">SQL Server Binary and Large-Value Data</span></span>](./sql/sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="8376d-130">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8376d-130">ADO.NET Overview</span></span>](ado-net-overview.md)
