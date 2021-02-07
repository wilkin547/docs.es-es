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
# <a name="retrieving-binary-data"></a><span data-ttu-id="046cf-103">Recuperar datos binarios</span><span class="sxs-lookup"><span data-stu-id="046cf-103">Retrieving Binary Data</span></span>

<span data-ttu-id="046cf-104">El objeto **DataReader** carga de forma predeterminada los datos que recibe en una fila, siempre que hay disponibles suficientes datos para llenarla.</span><span class="sxs-lookup"><span data-stu-id="046cf-104">By default, the **DataReader** loads incoming data as a row as soon as an entire row of data is available.</span></span> <span data-ttu-id="046cf-105">Sin embargo, los objetos binarios grandes (BLOB) se deben tratar de otra forma, ya que pueden llegar a contener grandes cantidades de datos (del orden de gigabytes) que no pueden almacenarse en una sola fila.</span><span class="sxs-lookup"><span data-stu-id="046cf-105">Binary large objects (BLOBs) need different treatment, however, because they can contain gigabytes of data that cannot be contained in a single row.</span></span> <span data-ttu-id="046cf-106">El método **Command.ExecuteReader** se puede sobrecargar para aceptar un argumento <xref:System.Data.CommandBehavior> y modificar el comportamiento predeterminado de **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="046cf-106">The **Command.ExecuteReader** method has an overload that will take a <xref:System.Data.CommandBehavior> argument to modify the default behavior of the **DataReader**.</span></span> <span data-ttu-id="046cf-107">Puede pasar <xref:System.Data.CommandBehavior.SequentialAccess> al método **ExecuteReader** para modificar el comportamiento predeterminado de **DataReader** de forma que en lugar de cargar los datos por filas, los vaya cargando secuencialmente a medida que los vaya recibiendo.</span><span class="sxs-lookup"><span data-stu-id="046cf-107">You can pass <xref:System.Data.CommandBehavior.SequentialAccess> to the **ExecuteReader** method to modify the default behavior of the **DataReader** so that instead of loading rows of data, it will load data sequentially as it is received.</span></span> <span data-ttu-id="046cf-108">Este sistema es idóneo para cargar BLOB y otras estructuras de datos grandes.</span><span class="sxs-lookup"><span data-stu-id="046cf-108">This is ideal for loading BLOBs or other large data structures.</span></span> <span data-ttu-id="046cf-109">Tenga en cuenta que este comportamiento puede depender del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="046cf-109">Note that this behavior may depend on your data source.</span></span> <span data-ttu-id="046cf-110">Por ejemplo, si se devuelve un BLOB desde Microsoft Access, el BLOB completo se cargará en memoria, en lugar de hacerlo secuencialmente a medida que se recibe.</span><span class="sxs-lookup"><span data-stu-id="046cf-110">For example, returning a BLOB from Microsoft Access will load the entire BLOB being loaded into memory, rather than sequentially as it is received.</span></span>  
  
 <span data-ttu-id="046cf-111">Al configurar **DataReader** para que utilice **SequentialAccess** debe tener en cuenta la secuencia en que va a tener acceso a los campos devueltos.</span><span class="sxs-lookup"><span data-stu-id="046cf-111">When setting the **DataReader** to use **SequentialAccess**, it is important to note the sequence in which you access the fields returned.</span></span> <span data-ttu-id="046cf-112">El comportamiento predeterminado de **DataReader**, consistente en cargar una fila completa de datos en cuanto hay datos suficientes, permite tener acceso a los campos devueltos en cualquier orden hasta que se lee la fila siguiente.</span><span class="sxs-lookup"><span data-stu-id="046cf-112">The default behavior of the **DataReader**, which loads an entire row as soon as it is available, allows you to access the fields returned in any order until the next row is read.</span></span> <span data-ttu-id="046cf-113">Sin embargo, al utilizar **SequentialAccess** es necesario tener acceso a los campos que devuelve **DataReader** en el orden adecuado.</span><span class="sxs-lookup"><span data-stu-id="046cf-113">When using **SequentialAccess** however, you must access the fields returned by the **DataReader** in order.</span></span> <span data-ttu-id="046cf-114">Por ejemplo, si la consulta devuelve tres columnas y la tercera es un BLOB, debe devolver los valores de los campos primero y segundo antes de tener acceso a los datos BLOB del tercer campo.</span><span class="sxs-lookup"><span data-stu-id="046cf-114">For example, if your query returns three columns, the third of which is a BLOB, you must return the values of the first and second fields before accessing the BLOB data in the third field.</span></span> <span data-ttu-id="046cf-115">Si trata de tener acceso al tercer campo antes que al primero o el segundo, puede que éstos dejen de estar disponibles.</span><span class="sxs-lookup"><span data-stu-id="046cf-115">If you access the third field before the first or second fields, the first and second field values are no longer available.</span></span> <span data-ttu-id="046cf-116">Esto se debe a que **SequentialAccess** cambia la forma en que el **DataReader** devuelve los datos, haciendo que lo haga de forma secuencial con lo que los datos dejan de estar disponibles en el momento en que el **DataReader** lee datos posteriores.</span><span class="sxs-lookup"><span data-stu-id="046cf-116">This is because **SequentialAccess** has modified the **DataReader** to return data in sequence and the data is not available after the **DataReader** has read past it.</span></span>  
  
 <span data-ttu-id="046cf-117">Cuando intente obtener acceso a los datos del campo BLOB, utilice los descriptores de acceso con información de tipos **GetBytes** o **GetChars** del **DataReader**, que llenan una matriz con los datos.</span><span class="sxs-lookup"><span data-stu-id="046cf-117">When accessing the data in the BLOB field, use the **GetBytes** or **GetChars** typed accessors of the **DataReader**, which fill an array with data.</span></span> <span data-ttu-id="046cf-118">También puede usar **GetString** para los datos de caracteres; sin.</span><span class="sxs-lookup"><span data-stu-id="046cf-118">You can also use **GetString** for character data; however.</span></span> <span data-ttu-id="046cf-119">si desea conservar los recursos del sistema, es mejor que no cargue un valor BLOB completo en una sola variable de cadena.</span><span class="sxs-lookup"><span data-stu-id="046cf-119">to conserve system resources you might not want to load an entire BLOB value into a single string variable.</span></span> <span data-ttu-id="046cf-120">En lugar de ello, puede especificar un tamaño determinado de búfer para los datos que se van a devolver, así como la ubicación de comienzo para leer el primer byte o carácter de los datos devueltos.</span><span class="sxs-lookup"><span data-stu-id="046cf-120">You can instead specify a specific buffer size of data to be returned, and a starting location for the first byte or character to be read from the returned data.</span></span> <span data-ttu-id="046cf-121">**GetBytes** y **GetChars** devuelven un valor de tipo `long` que representa el número de bytes o caracteres devueltos.</span><span class="sxs-lookup"><span data-stu-id="046cf-121">**GetBytes** and **GetChars** will return a `long` value, which represents the number of bytes or characters returned.</span></span> <span data-ttu-id="046cf-122">Si pasa una matriz con valores null a **GetBytes** o **GetChars**, el valor de tipo long devuelto contiene el número total de bytes o caracteres del BLOB.</span><span class="sxs-lookup"><span data-stu-id="046cf-122">If you pass a null array to **GetBytes** or **GetChars**, the long value returned will be the total number of bytes or characters in the BLOB.</span></span> <span data-ttu-id="046cf-123">También puede especificar un índice de la matriz como posición de comienzo para la lectura de datos.</span><span class="sxs-lookup"><span data-stu-id="046cf-123">You can optionally specify an index in the array as a starting position for the data being read.</span></span>  
  
## <a name="example"></a><span data-ttu-id="046cf-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="046cf-124">Example</span></span>  

 <span data-ttu-id="046cf-125">En el ejemplo siguiente se devuelve el identificador y el logotipo del publicador de la base de datos de ejemplo **pubs** en Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="046cf-125">The following example returns the publisher ID and logo from the **pubs** sample database in Microsoft SQL Server.</span></span> <span data-ttu-id="046cf-126">El identificador del publicador (`pub_id`) es un campo de caracteres, mientras que el logotipo es una imagen de BLOB.</span><span class="sxs-lookup"><span data-stu-id="046cf-126">The publisher ID (`pub_id`) is a character field, and the logo is an image, which is a BLOB.</span></span> <span data-ttu-id="046cf-127">Como el campo **logo** es un mapa de bits, el ejemplo devuelve datos binarios mediante **GetBytes**.</span><span class="sxs-lookup"><span data-stu-id="046cf-127">Because the **logo** field is a bitmap, the example returns binary data using **GetBytes**.</span></span> <span data-ttu-id="046cf-128">Tenga en cuenta que la necesidad de tener acceso a los datos de forma secuencial hace que en la fila actual de datos se tenga acceso al identificador de publicador antes que al logotipo.</span><span class="sxs-lookup"><span data-stu-id="046cf-128">Notice that the publisher ID is accessed for the current row of data before the logo, because the fields must be accessed sequentially.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="046cf-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="046cf-129">See also</span></span>

- [<span data-ttu-id="046cf-130">Datos binarios y datos de valores grandes de SQL Server</span><span class="sxs-lookup"><span data-stu-id="046cf-130">SQL Server Binary and Large-Value Data</span></span>](./sql/sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="046cf-131">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="046cf-131">ADO.NET Overview</span></span>](ado-net-overview.md)
