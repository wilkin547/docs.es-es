---
title: "Cómo: leer objetos de datos desde un archivo XML (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e1423bf-74a4-4dde-a3bb-ae1bfc0a68ed
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 47e5c614f2083ec2c595bba9c9454ecc5f61c786
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-read-object-data-from-an-xml-file-visual-basic"></a><span data-ttu-id="b3e33-102">Cómo: leer objetos de datos desde un archivo XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b3e33-102">How to: Read Object Data from an XML File (Visual Basic)</span></span>
<span data-ttu-id="b3e33-103">En este ejemplo se leen los datos de objetos que se han escrito anteriormente en un archivo XML con la clase <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="b3e33-103">This example reads object data that was previously written to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3e33-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b3e33-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="b3e33-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="b3e33-105">Compiling the Code</span></span>  
 <span data-ttu-id="b3e33-106">Reemplace el nombre de archivo "c:\temp\SerializationOverview.xml" por el nombre del archivo que contiene los datos serializados.</span><span class="sxs-lookup"><span data-stu-id="b3e33-106">Replace the file name "c:\temp\SerializationOverview.xml" with the name of the file containing the serialized data.</span></span> <span data-ttu-id="b3e33-107">Para obtener más información sobre la serialización de datos, vea [Cómo: escribir datos de objetos en un archivo XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="b3e33-107">For more information about serializing data, see [How to: Write Object Data to an XML File (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md).</span></span>  
  
 <span data-ttu-id="b3e33-108">La clase debe tener un constructor público sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="b3e33-108">The class must have a public constructor without parameters.</span></span>  
  
 <span data-ttu-id="b3e33-109">Solo se deserializan las propiedades y los campos públicos.</span><span class="sxs-lookup"><span data-stu-id="b3e33-109">Only public properties and fields are deserialized.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="b3e33-110">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="b3e33-110">Robust Programming</span></span>  
 <span data-ttu-id="b3e33-111">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="b3e33-111">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="b3e33-112">La clase que se está serializando no tiene un constructor público sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="b3e33-112">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
-   <span data-ttu-id="b3e33-113">Los datos del archivo no representan los datos de la clase que se va a deserializar.</span><span class="sxs-lookup"><span data-stu-id="b3e33-113">The data in the file does not represent data from the class to be deserialized.</span></span>  
  
-   <span data-ttu-id="b3e33-114">El archivo no existe (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="b3e33-114">The file does not exist (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="b3e33-115">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b3e33-115">.NET Framework Security</span></span>  
 <span data-ttu-id="b3e33-116">Compruebe siempre las entradas y nunca deserialice datos de un origen que no sea de confianza.</span><span class="sxs-lookup"><span data-stu-id="b3e33-116">Always verify inputs, and never deserialize data from an untrusted source.</span></span> <span data-ttu-id="b3e33-117">El objeto que se ha vuelto a crear se ejecuta en un equipo local con los permisos del código que lo ha deserializado.</span><span class="sxs-lookup"><span data-stu-id="b3e33-117">The re-created object runs on a local computer with the permissions of the code that deserialized it.</span></span> <span data-ttu-id="b3e33-118">Compruebe todas las entradas antes de utilizar los datos en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b3e33-118">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3e33-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3e33-119">See Also</span></span>  
 <xref:System.IO.StreamWriter>  
 <span data-ttu-id="b3e33-120">[How to: Write Object Data to an XML File (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md) (Escritura de datos de objetos en un archivo XML [Visual Basic])</span><span class="sxs-lookup"><span data-stu-id="b3e33-120">[How to: Write Object Data to an XML File (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)</span></span>  
 [<span data-ttu-id="b3e33-121">Serialización (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b3e33-121">Serialization (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/serialization/index.md)  
 [<span data-ttu-id="b3e33-122">Guía de programación en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b3e33-122">Visual Basic Programming Guide</span></span>](../../../../visual-basic/programming-guide/index.md)
