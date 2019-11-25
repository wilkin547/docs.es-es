---
title: 'Cómo: Escribir objetos de datos en un archivo XML'
ms.date: 07/20/2015
ms.assetid: f7966480-5ed2-43ac-9894-33427436de2a
ms.openlocfilehash: b2181a74c83782cf4737b2a94fc5fb08fee28a10
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345454"
---
# <a name="how-to-write-object-data-to-an-xml-file-visual-basic"></a>How to: Write Object Data to an XML File (Visual Basic)
En este ejemplo se escribe el objeto de una clase en un archivo XML con la clase <xref:System.Xml.Serialization.XmlSerializer>.  
  
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
  
- La clase que se está serializando no tiene un constructor público sin parámetros.  
  
- El archivo ya existe y es de solo lectura (<xref:System.IO.IOException>).  
  
- La ruta de acceso del archivo es demasiado larga (<xref:System.IO.PathTooLongException>).  
  
- El disco está lleno (<xref:System.IO.IOException>).  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 En este ejemplo se crea un nuevo archivo, si este no existe aún. Si una aplicación necesita crear un archivo, precisará acceso `Create` para la carpeta. Si el archivo ya existe, la aplicación necesitará solo acceso `Write`, un privilegio menor. Siempre que sea posible, resulta más seguro crear el archivo durante la implementación y conceder solo acceso `Read` a un único archivo, en lugar de acceso `Create` para una carpeta.  
  
## <a name="see-also"></a>Vea también

- <xref:System.IO.StreamWriter>
- [How to: Read Object Data from an XML File (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md) (Lectura de datos de objetos de un archivo XML [Visual Basic])
- [Serialización (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/index.md)
