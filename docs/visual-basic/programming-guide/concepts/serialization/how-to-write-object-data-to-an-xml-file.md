---
title: "Cómo: escribir datos de objetos en un archivo XML (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: f7966480-5ed2-43ac-9894-33427436de2a
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 146ccb7b1999049106d5f0be1ce78e740dfcf060
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-write-object-data-to-an-xml-file-visual-basic"></a>Cómo: escribir datos de objetos en un archivo XML (Visual Basic)
En el ejemplo en este ejemplo se escribe el objeto de una clase en un archivo XML mediante la <xref:System.Xml.Serialization.XmlSerializer>clase.</xref:System.Xml.Serialization.XmlSerializer>  
  
## <a name="example"></a>Ejemplo  
  
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
  
## <a name="compiling-the-code"></a>Compilar el código  
 La clase debe tener un constructor público sin parámetros.  
  
## <a name="robust-programming"></a>Programación sólida  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   La clase que se está serializando no tiene un constructor público sin parámetros.  
  
-   El archivo existe y es de sólo lectura (<xref:System.IO.IOException>).</xref:System.IO.IOException>  
  
-   La ruta de acceso es demasiado largo (<xref:System.IO.PathTooLongException>).</xref:System.IO.PathTooLongException>  
  
-   El disco está lleno (<xref:System.IO.IOException>).</xref:System.IO.IOException>  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Este ejemplo crea un nuevo archivo, si el archivo no existe. Si una aplicación necesita crear un archivo, precisará `Create` acceso para la carpeta. Si el archivo ya existe, la aplicación necesita solo `Write` tener acceso a un privilegio menor. Siempre que sea posible, resulta más seguro crear el archivo durante la implementación y conceder sólo `Read` acceso a un solo archivo, en lugar de `Create` acceso para una carpeta.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IO.StreamWriter></xref:System.IO.StreamWriter>   
 [Cómo: leer datos de objetos de un archivo XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md)   
 [Serialización (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/index.md)
