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
# <a name="how-to-read-object-data-from-an-xml-file-visual-basic"></a>Cómo: leer objetos de datos desde un archivo XML (Visual Basic)
En este ejemplo se leen los datos de objetos que se han escrito anteriormente en un archivo XML con la clase <xref:System.Xml.Serialization.XmlSerializer>.  
  
## <a name="example"></a>Ejemplo  
  
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
  
## <a name="compiling-the-code"></a>Compilar el código  
 Reemplace el nombre de archivo "c:\temp\SerializationOverview.xml" por el nombre del archivo que contiene los datos serializados. Para obtener más información sobre la serialización de datos, vea [Cómo: escribir datos de objetos en un archivo XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md).  
  
 La clase debe tener un constructor público sin parámetros.  
  
 Solo se deserializan las propiedades y los campos públicos.  
  
## <a name="robust-programming"></a>Programación sólida  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   La clase que se está serializando no tiene un constructor público sin parámetros.  
  
-   Los datos del archivo no representan los datos de la clase que se va a deserializar.  
  
-   El archivo no existe (<xref:System.IO.IOException>).  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Compruebe siempre las entradas y nunca deserialice datos de un origen que no sea de confianza. El objeto que se ha vuelto a crear se ejecuta en un equipo local con los permisos del código que lo ha deserializado. Compruebe todas las entradas antes de utilizar los datos en la aplicación.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IO.StreamWriter>  
 [How to: Write Object Data to an XML File (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md) (Escritura de datos de objetos en un archivo XML [Visual Basic])  
 [Serialización (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/index.md)  
 [Guía de programación en Visual Basic](../../../../visual-basic/programming-guide/index.md)
