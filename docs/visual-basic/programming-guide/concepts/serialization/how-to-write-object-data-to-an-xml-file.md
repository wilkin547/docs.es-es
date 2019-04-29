---
title: Procedimiento Escribir datos de objetos en un archivo XML (Visual Basic)
ms.date: 07/20/2015
ms.assetid: f7966480-5ed2-43ac-9894-33427436de2a
ms.openlocfilehash: 52b896b0191f29f68cc31e02fc325638ca6341b4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783505"
---
# <a name="how-to-write-object-data-to-an-xml-file-visual-basic"></a><span data-ttu-id="af5bd-102">Procedimiento Escribir datos de objetos en un archivo XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="af5bd-102">How to: Write Object Data to an XML File (Visual Basic)</span></span>
<span data-ttu-id="af5bd-103">En este ejemplo se escribe el objeto de una clase en un archivo XML con la clase <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="af5bd-103">This example writes the object from a class to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af5bd-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="af5bd-104">Example</span></span>  
  
```vb  
Public Module XMLWrite  
  
    Sub Main()  
        WriteXML()  
    End Sub  
  
    Public Class Book  
        Public Title As String  
    End Class  
  
    Public Sub WriteXML()  
        Dim overview As New Book  
        overview.Title = "Serialization Overview"  
        Dim writer As New System.Xml.Serialization.XmlSerializer(GetType(Book))  
        Dim file As New System.IO.StreamWriter(  
            "c:\temp\SerializationOverview.xml")  
        writer.Serialize(file, overview)  
        file.Close()  
    End Sub  
End Module  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="af5bd-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="af5bd-105">Compiling the Code</span></span>  
 <span data-ttu-id="af5bd-106">La clase debe tener un constructor público sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="af5bd-106">The class must have a public constructor without parameters.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="af5bd-107">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="af5bd-107">Robust Programming</span></span>  
 <span data-ttu-id="af5bd-108">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="af5bd-108">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="af5bd-109">La clase que se está serializando no tiene un constructor público sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="af5bd-109">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
- <span data-ttu-id="af5bd-110">El archivo ya existe y es de solo lectura (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="af5bd-110">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="af5bd-111">La ruta de acceso del archivo es demasiado larga (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="af5bd-111">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="af5bd-112">El disco está lleno (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="af5bd-112">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="af5bd-113">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="af5bd-113">.NET Framework Security</span></span>  
 <span data-ttu-id="af5bd-114">En este ejemplo se crea un nuevo archivo, si este no existe aún.</span><span class="sxs-lookup"><span data-stu-id="af5bd-114">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="af5bd-115">Si una aplicación necesita crear un archivo, precisará acceso `Create` para la carpeta.</span><span class="sxs-lookup"><span data-stu-id="af5bd-115">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="af5bd-116">Si el archivo ya existe, la aplicación necesitará solo acceso `Write`, un privilegio menor.</span><span class="sxs-lookup"><span data-stu-id="af5bd-116">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="af5bd-117">Siempre que sea posible, resulta más seguro crear el archivo durante la implementación y conceder solo acceso `Read` a un único archivo, en lugar de acceso `Create` para una carpeta.</span><span class="sxs-lookup"><span data-stu-id="af5bd-117">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af5bd-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="af5bd-118">See also</span></span>

- <xref:System.IO.StreamWriter>
- [<span data-ttu-id="af5bd-119">Cómo: Leer datos de objetos de un archivo XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="af5bd-119">How to: Read Object Data from an XML File (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md)
- [<span data-ttu-id="af5bd-120">Serialización (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="af5bd-120">Serialization (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/serialization/index.md)
