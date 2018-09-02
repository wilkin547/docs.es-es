---
title: Recuperar datos binarios
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 56c5a9e3-31f1-482f-bce0-ff1c41a658d0
ms.openlocfilehash: ec4ef17687e4e1bf2cc18182a64fc7361fe3b6f7
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43421988"
---
# <a name="retrieving-binary-data"></a><span data-ttu-id="acddc-102">Recuperar datos binarios</span><span class="sxs-lookup"><span data-stu-id="acddc-102">Retrieving Binary Data</span></span>
<span data-ttu-id="acddc-103">De forma predeterminada, el **DataReader** carga los datos entrantes como una fila tan pronto como una fila completa de datos está disponible.</span><span class="sxs-lookup"><span data-stu-id="acddc-103">By default, the **DataReader** loads incoming data as a row as soon as an entire row of data is available.</span></span> <span data-ttu-id="acddc-104">Sin embargo, los objetos binarios grandes (BLOB) se deben tratar de otra forma, ya que pueden llegar a contener grandes cantidades de datos (del orden de gigabytes) que no pueden almacenarse en una sola fila.</span><span class="sxs-lookup"><span data-stu-id="acddc-104">Binary large objects (BLOBs) need different treatment, however, because they can contain gigabytes of data that cannot be contained in a single row.</span></span> <span data-ttu-id="acddc-105">El **Command.ExecuteReader** método tiene una sobrecarga que tomará un <xref:System.Data.CommandBehavior> argumento para modificar el comportamiento predeterminado de la **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="acddc-105">The **Command.ExecuteReader** method has an overload that will take a <xref:System.Data.CommandBehavior> argument to modify the default behavior of the **DataReader**.</span></span> <span data-ttu-id="acddc-106">Puede pasar <xref:System.Data.CommandBehavior.SequentialAccess> a la **ExecuteReader** método para modificar el comportamiento predeterminado de la **DataReader** para que en lugar de cargar las filas de datos, los vaya cargando secuencialmente a medida que se recibe.</span><span class="sxs-lookup"><span data-stu-id="acddc-106">You can pass <xref:System.Data.CommandBehavior.SequentialAccess> to the **ExecuteReader** method to modify the default behavior of the **DataReader** so that instead of loading rows of data, it will load data sequentially as it is received.</span></span> <span data-ttu-id="acddc-107">Este sistema es idóneo para cargar BLOB y otras estructuras de datos grandes.</span><span class="sxs-lookup"><span data-stu-id="acddc-107">This is ideal for loading BLOBs or other large data structures.</span></span> <span data-ttu-id="acddc-108">Tenga en cuenta que este comportamiento puede depender del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="acddc-108">Note that this behavior may depend on your data source.</span></span> <span data-ttu-id="acddc-109">Por ejemplo, si se devuelve un BLOB desde Microsoft Access, el BLOB completo se cargará en memoria, en lugar de hacerlo secuencialmente a medida que se recibe.</span><span class="sxs-lookup"><span data-stu-id="acddc-109">For example, returning a BLOB from Microsoft Access will load the entire BLOB being loaded into memory, rather than sequentially as it is received.</span></span>  
  
 <span data-ttu-id="acddc-110">Al establecer el **DataReader** usar **SequentialAccess**, es importante tener en cuenta la secuencia en la que obtener acceso a los campos devueltos.</span><span class="sxs-lookup"><span data-stu-id="acddc-110">When setting the **DataReader** to use **SequentialAccess**, it is important to note the sequence in which you access the fields returned.</span></span> <span data-ttu-id="acddc-111">El comportamiento predeterminado de la **DataReader**, lo que carga una fila completa en cuanto esté disponible, permite obtener acceso a los campos devueltos en cualquier orden hasta que se lee la fila siguiente.</span><span class="sxs-lookup"><span data-stu-id="acddc-111">The default behavior of the **DataReader**, which loads an entire row as soon as it is available, allows you to access the fields returned in any order until the next row is read.</span></span> <span data-ttu-id="acddc-112">Cuando se usa **SequentialAccess** sin embargo, debe tener acceso a los campos devueltos por la **DataReader** en orden.</span><span class="sxs-lookup"><span data-stu-id="acddc-112">When using **SequentialAccess** however, you must access the fields returned by the **DataReader** in order.</span></span> <span data-ttu-id="acddc-113">Por ejemplo, si la consulta devuelve tres columnas y la tercera es un BLOB, debe devolver los valores de los campos primero y segundo antes de tener acceso a los datos BLOB del tercer campo.</span><span class="sxs-lookup"><span data-stu-id="acddc-113">For example, if your query returns three columns, the third of which is a BLOB, you must return the values of the first and second fields before accessing the BLOB data in the third field.</span></span> <span data-ttu-id="acddc-114">Si trata de tener acceso al tercer campo antes que al primero o el segundo, puede que éstos dejen de estar disponibles.</span><span class="sxs-lookup"><span data-stu-id="acddc-114">If you access the third field before the first or second fields, the first and second field values are no longer available.</span></span> <span data-ttu-id="acddc-115">Esto es porque **SequentialAccess** modificó el **DataReader** devolver datos de secuencia y los datos no está disponible después de la **DataReader** leyó más allá de lo.</span><span class="sxs-lookup"><span data-stu-id="acddc-115">This is because **SequentialAccess** has modified the **DataReader** to return data in sequence and the data is not available after the **DataReader** has read past it.</span></span>  
  
 <span data-ttu-id="acddc-116">Al acceder a los datos del campo BLOB, use el **GetBytes** o **GetChars** escrito descriptores de acceso de la **DataReader**, que llenan una matriz con los datos.</span><span class="sxs-lookup"><span data-stu-id="acddc-116">When accessing the data in the BLOB field, use the **GetBytes** or **GetChars** typed accessors of the **DataReader**, which fill an array with data.</span></span> <span data-ttu-id="acddc-117">También puede usar **GetString** para datos de caracteres; sin embargo.</span><span class="sxs-lookup"><span data-stu-id="acddc-117">You can also use **GetString** for character data; however.</span></span> <span data-ttu-id="acddc-118">si desea conservar los recursos del sistema, es mejor que no cargue un valor BLOB completo en una sola variable de cadena.</span><span class="sxs-lookup"><span data-stu-id="acddc-118">to conserve system resources you might not want to load an entire BLOB value into a single string variable.</span></span> <span data-ttu-id="acddc-119">En lugar de ello, puede especificar un tamaño determinado de búfer para los datos que se van a devolver, así como la ubicación de comienzo para leer el primer byte o carácter de los datos devueltos.</span><span class="sxs-lookup"><span data-stu-id="acddc-119">You can instead specify a specific buffer size of data to be returned, and a starting location for the first byte or character to be read from the returned data.</span></span> <span data-ttu-id="acddc-120">**GetBytes** y **GetChars** devolverá un `long` valor, que representa el número de bytes o caracteres devueltos.</span><span class="sxs-lookup"><span data-stu-id="acddc-120">**GetBytes** and **GetChars** will return a `long` value, which represents the number of bytes or characters returned.</span></span> <span data-ttu-id="acddc-121">Si se pasa una matriz nula para **GetBytes** o **GetChars**, el valor de tipo long devuelto será el número total de bytes o caracteres del BLOB.</span><span class="sxs-lookup"><span data-stu-id="acddc-121">If you pass a null array to **GetBytes** or **GetChars**, the long value returned will be the total number of bytes or characters in the BLOB.</span></span> <span data-ttu-id="acddc-122">También puede especificar un índice de la matriz como posición de comienzo para la lectura de datos.</span><span class="sxs-lookup"><span data-stu-id="acddc-122">You can optionally specify an index in the array as a starting position for the data being read.</span></span>  
  
## <a name="example"></a><span data-ttu-id="acddc-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="acddc-123">Example</span></span>  
 <span data-ttu-id="acddc-124">El ejemplo siguiente devuelve el Id. de publicador y el logotipo de la **pubs** base de datos de ejemplo en Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="acddc-124">The following example returns the publisher ID and logo from the **pubs** sample database in Microsoft SQL Server.</span></span> <span data-ttu-id="acddc-125">El identificador del publicador (`pub_id`) es un campo de caracteres, mientras que el logotipo es una imagen de BLOB.</span><span class="sxs-lookup"><span data-stu-id="acddc-125">The publisher ID (`pub_id`) is a character field, and the logo is an image, which is a BLOB.</span></span> <span data-ttu-id="acddc-126">Dado que el **logotipo** campo es un mapa de bits, el ejemplo devuelve datos binarios mediante **GetBytes**.</span><span class="sxs-lookup"><span data-stu-id="acddc-126">Because the **logo** field is a bitmap, the example returns binary data using **GetBytes**.</span></span> <span data-ttu-id="acddc-127">Tenga en cuenta que la necesidad de tener acceso a los datos de forma secuencial hace que en la fila actual de datos se tenga acceso al identificador de publicador antes que al logotipo.</span><span class="sxs-lookup"><span data-stu-id="acddc-127">Notice that the publisher ID is accessed for the current row of data before the logo, because the fields must be accessed sequentially.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="acddc-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="acddc-128">See Also</span></span>  
 [<span data-ttu-id="acddc-129">Trabajar con DataReaders</span><span class="sxs-lookup"><span data-stu-id="acddc-129">Working with DataReaders</span></span>](https://msdn.microsoft.com/library/126a966a-d08d-4d22-a19f-f432908b2b54)  
 [<span data-ttu-id="acddc-130">Datos binarios y datos de valores grandes de SQL Server</span><span class="sxs-lookup"><span data-stu-id="acddc-130">SQL Server Binary and Large-Value Data</span></span>](../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)  
 [<span data-ttu-id="acddc-131">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="acddc-131">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
