---
description: 'Más información acerca de cómo: leer datos de objetos de un archivo XML (Visual Basic)'
title: Procedimiento para leer datos de objetos en un archivo XML
ms.date: 07/20/2015
ms.assetid: 1e1423bf-74a4-4dde-a3bb-ae1bfc0a68ed
ms.openlocfilehash: d281997a0dd96ad6263fe03cea84b3e84005a3ad
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100486828"
---
# <a name="how-to-read-object-data-from-an-xml-file-visual-basic"></a><span data-ttu-id="5d821-103">How to: Read Object Data from an XML File (Visual Basic) (Lectura de datos de objetos de un archivo XML [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="5d821-103">How to: Read Object Data from an XML File (Visual Basic)</span></span>

<span data-ttu-id="5d821-104">En este ejemplo se leen los datos de objetos que se han escrito anteriormente en un archivo XML con la clase <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="5d821-104">This example reads object data that was previously written to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d821-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5d821-105">Example</span></span>  
  
```vb  
Public Class Book  
    Public Title As String  
End Class  
  
Public Sub ReadXML()  
    Dim reader As New System.Xml.Serialization.XmlSerializer(GetType(Book))  
    Dim file As New System.IO.StreamReader(  
        "c:\temp\SerializationOverview.xml")  
    Dim overview As Book  
    overview = CType(reader.Deserialize(file), Book)  
    Console.WriteLine(overview.Title)  
End Sub  
```  
  
## <a name="compile-the-code"></a><span data-ttu-id="5d821-106">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="5d821-106">Compile the code</span></span>  

 <span data-ttu-id="5d821-107">Reemplace el nombre de archivo "c:\temp\SerializationOverview.xml" por el nombre del archivo que contiene los datos serializados.</span><span class="sxs-lookup"><span data-stu-id="5d821-107">Replace the file name "c:\temp\SerializationOverview.xml" with the name of the file containing the serialized data.</span></span> <span data-ttu-id="5d821-108">Para obtener más información sobre la serialización de datos, vea [Cómo: escribir datos de objetos en un archivo XML (Visual Basic)](how-to-write-object-data-to-an-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="5d821-108">For more information about serializing data, see [How to: Write Object Data to an XML File (Visual Basic)](how-to-write-object-data-to-an-xml-file.md).</span></span>  
  
 <span data-ttu-id="5d821-109">La clase debe tener un constructor público sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="5d821-109">The class must have a public constructor without parameters.</span></span>  
  
 <span data-ttu-id="5d821-110">Solo se deserializan las propiedades y los campos públicos.</span><span class="sxs-lookup"><span data-stu-id="5d821-110">Only public properties and fields are deserialized.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="5d821-111">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="5d821-111">Robust Programming</span></span>  

 <span data-ttu-id="5d821-112">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="5d821-112">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="5d821-113">La clase que se está serializando no tiene un constructor público sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="5d821-113">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
- <span data-ttu-id="5d821-114">Los datos del archivo no representan los datos de la clase que se va a deserializar.</span><span class="sxs-lookup"><span data-stu-id="5d821-114">The data in the file does not represent data from the class to be deserialized.</span></span>  
  
- <span data-ttu-id="5d821-115">El archivo no existe (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="5d821-115">The file does not exist (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="5d821-116">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5d821-116">.NET Framework Security</span></span>  

 <span data-ttu-id="5d821-117">Compruebe siempre las entradas y nunca deserialice datos de un origen que no sea de confianza.</span><span class="sxs-lookup"><span data-stu-id="5d821-117">Always verify inputs, and never deserialize data from an untrusted source.</span></span> <span data-ttu-id="5d821-118">El objeto que se ha vuelto a crear se ejecuta en un equipo local con los permisos del código que lo ha deserializado.</span><span class="sxs-lookup"><span data-stu-id="5d821-118">The re-created object runs on a local computer with the permissions of the code that deserialized it.</span></span> <span data-ttu-id="5d821-119">Compruebe todas las entradas antes de utilizar los datos en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5d821-119">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d821-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d821-120">See also</span></span>

- <xref:System.IO.StreamWriter>
- <span data-ttu-id="5d821-121">[How to: Write Object Data to an XML File (Visual Basic)](how-to-write-object-data-to-an-xml-file.md) (Escritura de datos de objetos en un archivo XML [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="5d821-121">[How to: Write Object Data to an XML File (Visual Basic)](how-to-write-object-data-to-an-xml-file.md)</span></span>
- [<span data-ttu-id="5d821-122">Serialización (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d821-122">Serialization (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="5d821-123">Guía de programación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5d821-123">Visual Basic Programming Guide</span></span>](../../index.md)
