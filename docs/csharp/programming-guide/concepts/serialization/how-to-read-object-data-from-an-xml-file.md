---
title: 'Cómo: Leer datos de objetos de un archivo XML (C#)'
ms.date: 07/20/2015
ms.assetid: 6ad60d96-a4d9-48e6-a8b0-d7f6f803cafa
ms.openlocfilehash: 7c3bad56c6a0bee51262586aea4ce97ff0491f24
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44083941"
---
# <a name="how-to-read-object-data-from-an-xml-file-c"></a><span data-ttu-id="69729-102">Cómo: Leer datos de objetos de un archivo XML (C#)</span><span class="sxs-lookup"><span data-stu-id="69729-102">How to: Read Object Data from an XML File (C#)</span></span>
<span data-ttu-id="69729-103">En este ejemplo se leen los datos de objetos que se han escrito anteriormente en un archivo XML con la clase <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="69729-103">This example reads object data that was previously written to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69729-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="69729-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="69729-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="69729-105">Compiling the Code</span></span>  
 <span data-ttu-id="69729-106">Reemplace el nombre de archivo "c:\temp\SerializationOverview.xml" por el nombre del archivo que contiene los datos serializados.</span><span class="sxs-lookup"><span data-stu-id="69729-106">Replace the file name "c:\temp\SerializationOverview.xml" with the name of the file containing the serialized data.</span></span> <span data-ttu-id="69729-107">Para obtener más información sobre la serialización de datos, vea [How to: Write Object Data to an XML File (C#)](../../../../csharp/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md) (Cómo: Escribir datos de objetos en un archivo XML (C#)).</span><span class="sxs-lookup"><span data-stu-id="69729-107">For more information about serializing data, see [How to: Write Object Data to an XML File (C#)](../../../../csharp/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md).</span></span>  
  
 <span data-ttu-id="69729-108">La clase debe tener un constructor público sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="69729-108">The class must have a public constructor without parameters.</span></span>  
  
 <span data-ttu-id="69729-109">Solo se deserializan las propiedades y los campos públicos.</span><span class="sxs-lookup"><span data-stu-id="69729-109">Only public properties and fields are deserialized.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="69729-110">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="69729-110">Robust Programming</span></span>  
 <span data-ttu-id="69729-111">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="69729-111">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="69729-112">La clase que se está serializando no tiene un constructor público sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="69729-112">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
-   <span data-ttu-id="69729-113">Los datos del archivo no representan los datos de la clase que se va a deserializar.</span><span class="sxs-lookup"><span data-stu-id="69729-113">The data in the file does not represent data from the class to be deserialized.</span></span>  
  
-   <span data-ttu-id="69729-114">El archivo no existe (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="69729-114">The file does not exist (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="69729-115">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="69729-115">.NET Framework Security</span></span>  
 <span data-ttu-id="69729-116">Compruebe siempre las entradas y nunca deserialice datos de un origen que no sea de confianza.</span><span class="sxs-lookup"><span data-stu-id="69729-116">Always verify inputs, and never deserialize data from an untrusted source.</span></span> <span data-ttu-id="69729-117">El objeto que se ha vuelto a crear se ejecuta en un equipo local con los permisos del código que lo ha deserializado.</span><span class="sxs-lookup"><span data-stu-id="69729-117">The re-created object runs on a local computer with the permissions of the code that deserialized it.</span></span> <span data-ttu-id="69729-118">Compruebe todas las entradas antes de utilizar los datos en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="69729-118">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69729-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="69729-119">See Also</span></span>

- <xref:System.IO.StreamWriter>  
- <span data-ttu-id="69729-120">[How to: Write Object Data to an XML File (C#)](../../../../csharp/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md) (Escritura de datos de objeto en un archivo XML [C#])</span><span class="sxs-lookup"><span data-stu-id="69729-120">[How to: Write Object Data to an XML File (C#)](../../../../csharp/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)</span></span>  
- [<span data-ttu-id="69729-121">Serialización (C#)</span><span class="sxs-lookup"><span data-stu-id="69729-121">Serialization (C#)</span></span>](../../../../csharp/programming-guide/concepts/serialization/index.md)  
- [<span data-ttu-id="69729-122">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="69729-122">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)
