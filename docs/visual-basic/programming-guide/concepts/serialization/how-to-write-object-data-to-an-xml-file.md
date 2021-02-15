---
description: 'Más información acerca de cómo: escribir datos de objetos en un archivo XML (Visual Basic)'
title: Procedimiento para escribir datos de objeto en un archivo XML
ms.date: 07/20/2015
ms.assetid: f7966480-5ed2-43ac-9894-33427436de2a
ms.openlocfilehash: c6935fa97ed8813528630f5794e0a8e3e7e77b4d
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100486841"
---
# <a name="how-to-write-object-data-to-an-xml-file-visual-basic"></a><span data-ttu-id="616b2-103">How to: Write Object Data to an XML File (Visual Basic) (Escritura de datos de objetos en un archivo XML [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="616b2-103">How to: Write Object Data to an XML File (Visual Basic)</span></span>

<span data-ttu-id="616b2-104">En este ejemplo se escribe el objeto de una clase en un archivo XML con la clase <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="616b2-104">This example writes the object from a class to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="616b2-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="616b2-105">Example</span></span>  
  
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
  
## <a name="compile-the-code"></a><span data-ttu-id="616b2-106">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="616b2-106">Compile the code</span></span>  

 <span data-ttu-id="616b2-107">La clase debe tener un constructor público sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="616b2-107">The class must have a public constructor without parameters.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="616b2-108">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="616b2-108">Robust Programming</span></span>  

 <span data-ttu-id="616b2-109">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="616b2-109">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="616b2-110">La clase que se está serializando no tiene un constructor público sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="616b2-110">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
- <span data-ttu-id="616b2-111">El archivo ya existe y es de solo lectura (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="616b2-111">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="616b2-112">La ruta de acceso del archivo es demasiado larga (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="616b2-112">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="616b2-113">El disco está lleno (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="616b2-113">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="616b2-114">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="616b2-114">.NET Framework Security</span></span>  

 <span data-ttu-id="616b2-115">En este ejemplo se crea un nuevo archivo, si este no existe aún.</span><span class="sxs-lookup"><span data-stu-id="616b2-115">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="616b2-116">Si una aplicación necesita crear un archivo, precisará acceso `Create` para la carpeta.</span><span class="sxs-lookup"><span data-stu-id="616b2-116">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="616b2-117">Si el archivo ya existe, la aplicación necesitará solo acceso `Write`, un privilegio menor.</span><span class="sxs-lookup"><span data-stu-id="616b2-117">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="616b2-118">Siempre que sea posible, resulta más seguro crear el archivo durante la implementación y conceder solo acceso `Read` a un único archivo, en lugar de acceso `Create` para una carpeta.</span><span class="sxs-lookup"><span data-stu-id="616b2-118">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="616b2-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="616b2-119">See also</span></span>

- <xref:System.IO.StreamWriter>
- <span data-ttu-id="616b2-120">[How to: Read Object Data from an XML File (Visual Basic)](how-to-read-object-data-from-an-xml-file.md) (Lectura de datos de objetos de un archivo XML [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="616b2-120">[How to: Read Object Data from an XML File (Visual Basic)](how-to-read-object-data-from-an-xml-file.md)</span></span>
- [<span data-ttu-id="616b2-121">Serialización (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="616b2-121">Serialization (Visual Basic)</span></span>](index.md)
