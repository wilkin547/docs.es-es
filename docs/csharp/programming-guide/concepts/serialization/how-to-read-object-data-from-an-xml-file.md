---
title: Procedimiento para leer datos de objeto de un archivo XML (C#)
ms.date: 07/20/2015
ms.assetid: 6ad60d96-a4d9-48e6-a8b0-d7f6f803cafa
ms.openlocfilehash: 2da5919c11ed2d6e43f4f9fc406f43e3ed48060f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346431"
---
# <a name="how-to-read-object-data-from-an-xml-file-c"></a><span data-ttu-id="e3618-102">Procedimiento para leer datos de objeto de un archivo XML (C#)</span><span class="sxs-lookup"><span data-stu-id="e3618-102">How to read object data from an XML file (C#)</span></span>
<span data-ttu-id="e3618-103">En este ejemplo se leen los datos de objetos que se han escrito anteriormente en un archivo XML con la clase <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="e3618-103">This example reads object data that was previously written to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3618-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e3618-104">Example</span></span>  
  
```csharp  
public class Book  
{  
    public String title;  
}         
  
public void ReadXML()  
{  
    // First write something so that there is something to read ...  
    var b = new Book { title = "Serialization Overview" };  
    var writer = new System.Xml.Serialization.XmlSerializer(typeof(Book));  
    var wfile = new System.IO.StreamWriter(@"c:\temp\SerializationOverview.xml");  
    writer.Serialize(wfile, b);  
    wfile.Close();  
  
    // Now we can read the serialized book ...  
    System.Xml.Serialization.XmlSerializer reader =   
        new System.Xml.Serialization.XmlSerializer(typeof(Book));  
    System.IO.StreamReader file = new System.IO.StreamReader(  
        @"c:\temp\SerializationOverview.xml");  
    Book overview =  (Book)reader.Deserialize(file);  
    file.Close();  
  
    Console.WriteLine(overview.title);  
  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e3618-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="e3618-105">Compiling the Code</span></span>  
<span data-ttu-id="e3618-106">Reemplace el nombre de archivo "c:\temp\SerializationOverview.xml" por el nombre del archivo que contiene los datos serializados.</span><span class="sxs-lookup"><span data-stu-id="e3618-106">Replace the file name "c:\temp\SerializationOverview.xml" with the name of the file containing the serialized data.</span></span> <span data-ttu-id="e3618-107">Para más información sobre la serialización de datos, consulte [Procedimiento para escribir datos de objeto en un archivo XML (C#)](./how-to-write-object-data-to-an-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="e3618-107">For more information about serializing data, see [How to write object data to an XML file (C#)](./how-to-write-object-data-to-an-xml-file.md).</span></span>
  
 <span data-ttu-id="e3618-108">La clase debe tener un constructor público sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="e3618-108">The class must have a public constructor without parameters.</span></span>  
  
 <span data-ttu-id="e3618-109">Solo se deserializan las propiedades y los campos públicos.</span><span class="sxs-lookup"><span data-stu-id="e3618-109">Only public properties and fields are deserialized.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="e3618-110">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="e3618-110">Robust Programming</span></span>  
 <span data-ttu-id="e3618-111">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="e3618-111">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="e3618-112">La clase que se está serializando no tiene un constructor público sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="e3618-112">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
- <span data-ttu-id="e3618-113">Los datos del archivo no representan los datos de la clase que se va a deserializar.</span><span class="sxs-lookup"><span data-stu-id="e3618-113">The data in the file does not represent data from the class to be deserialized.</span></span>  
  
- <span data-ttu-id="e3618-114">El archivo no existe (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="e3618-114">The file does not exist (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="e3618-115">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e3618-115">.NET Framework Security</span></span>  
 <span data-ttu-id="e3618-116">Compruebe siempre las entradas y nunca deserialice datos de un origen que no sea de confianza.</span><span class="sxs-lookup"><span data-stu-id="e3618-116">Always verify inputs, and never deserialize data from an untrusted source.</span></span> <span data-ttu-id="e3618-117">El objeto que se ha vuelto a crear se ejecuta en un equipo local con los permisos del código que lo ha deserializado.</span><span class="sxs-lookup"><span data-stu-id="e3618-117">The re-created object runs on a local computer with the permissions of the code that deserialized it.</span></span> <span data-ttu-id="e3618-118">Compruebe todas las entradas antes de utilizar los datos en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e3618-118">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3618-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3618-119">See also</span></span>

- <xref:System.IO.StreamWriter>
- [<span data-ttu-id="e3618-120">Procedimiento para escribir datos de objeto en un archivo XML (C#)</span><span class="sxs-lookup"><span data-stu-id="e3618-120">How to write object data to an XML file (C#)</span></span>](./how-to-write-object-data-to-an-xml-file.md)
- [<span data-ttu-id="e3618-121">Serialización (C#)</span><span class="sxs-lookup"><span data-stu-id="e3618-121">Serialization (C#)</span></span>](./index.md)
- [<span data-ttu-id="e3618-122">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="e3618-122">C# Programming Guide</span></span>](../../index.md)
