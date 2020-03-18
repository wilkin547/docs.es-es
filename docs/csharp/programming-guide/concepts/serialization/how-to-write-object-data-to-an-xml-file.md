---
title: Procedimiento para escribir datos de objeto en un archivo XML (C#)
ms.date: 07/20/2015
ms.assetid: 7681eb98-703d-4005-a369-26a7bca0f894
ms.openlocfilehash: f7ffb47a22d3cd94cd7cb6f702b64180a8790eb4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79167523"
---
# <a name="how-to-write-object-data-to-an-xml-file-c"></a><span data-ttu-id="9c47c-102">Procedimiento para escribir datos de objeto en un archivo XML (C#)</span><span class="sxs-lookup"><span data-stu-id="9c47c-102">How to write object data to an XML file (C#)</span></span>
<span data-ttu-id="9c47c-103">En este ejemplo se escribe el objeto de una clase en un archivo XML con la clase <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="9c47c-103">This example writes the object from a class to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c47c-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9c47c-104">Example</span></span>  
  
```csharp  
public class XMLWrite  
{  
  
   static void Main(string[] args)  
    {  
        WriteXML();  
    }  
  
    public class Book  
    {  
        public String title;
    }  
  
    public static void WriteXML()  
    {  
        Book overview = new Book();  
        overview.title = "Serialization Overview";  
        System.Xml.Serialization.XmlSerializer writer =
            new System.Xml.Serialization.XmlSerializer(typeof(Book));  
  
        var path = Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments) + "//SerializationOverview.xml";  
        System.IO.FileStream file = System.IO.File.Create(path);  
  
        writer.Serialize(file, overview);  
        file.Close();  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9c47c-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="9c47c-105">Compiling the Code</span></span>  
 <span data-ttu-id="9c47c-106">La clase que se serializa debe tener un constructor público sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="9c47c-106">The class being serialized must have a public constructor without parameters.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="9c47c-107">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="9c47c-107">Robust Programming</span></span>  
 <span data-ttu-id="9c47c-108">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="9c47c-108">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="9c47c-109">La clase que se está serializando no tiene un constructor público sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="9c47c-109">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
- <span data-ttu-id="9c47c-110">El archivo ya existe y es de solo lectura (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="9c47c-110">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="9c47c-111">La ruta de acceso del archivo es demasiado larga (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="9c47c-111">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="9c47c-112">El disco está lleno (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="9c47c-112">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="9c47c-113">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9c47c-113">.NET Framework Security</span></span>  
 <span data-ttu-id="9c47c-114">En este ejemplo se crea un nuevo archivo, si este no existe aún.</span><span class="sxs-lookup"><span data-stu-id="9c47c-114">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="9c47c-115">Si una aplicación necesita crear un archivo, precisará acceso `Create` para la carpeta.</span><span class="sxs-lookup"><span data-stu-id="9c47c-115">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="9c47c-116">Si el archivo ya existe, la aplicación necesitará solo acceso `Write`, un privilegio menor.</span><span class="sxs-lookup"><span data-stu-id="9c47c-116">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="9c47c-117">Siempre que sea posible, resulta más seguro crear el archivo durante la implementación y conceder solo acceso `Read` a un único archivo, en lugar de acceso `Create` para una carpeta.</span><span class="sxs-lookup"><span data-stu-id="9c47c-117">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c47c-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c47c-118">See also</span></span>

- <xref:System.IO.StreamWriter>
- [<span data-ttu-id="9c47c-119">Procedimiento para leer datos de objeto de un archivo XML (C#)</span><span class="sxs-lookup"><span data-stu-id="9c47c-119">How to read object data from an XML file (C#)</span></span>](./how-to-read-object-data-from-an-xml-file.md)
- [<span data-ttu-id="9c47c-120">Serialización (C#)</span><span class="sxs-lookup"><span data-stu-id="9c47c-120">Serialization (C#)</span></span>](./index.md)
