---
title: Procedimiento para leer datos de objetos en un archivo XML
ms.date: 07/20/2015
ms.assetid: 1e1423bf-74a4-4dde-a3bb-ae1bfc0a68ed
ms.openlocfilehash: 7677b32f76bee3fe579f96715b6c748c08c83a82
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077246"
---
# <a name="how-to-read-object-data-from-an-xml-file-visual-basic"></a>How to: Read Object Data from an XML File (Visual Basic) (Lectura de datos de objetos de un archivo XML [Visual Basic])

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
  
## <a name="compile-the-code"></a>Compilar el código  

 Reemplace el nombre de archivo "c:\temp\SerializationOverview.xml" por el nombre del archivo que contiene los datos serializados. Para obtener más información sobre la serialización de datos, vea [Cómo: escribir datos de objetos en un archivo XML (Visual Basic)](how-to-write-object-data-to-an-xml-file.md).  
  
 La clase debe tener un constructor público sin parámetros.  
  
 Solo se deserializan las propiedades y los campos públicos.  
  
## <a name="robust-programming"></a>Programación sólida  

 Las condiciones siguientes pueden provocar una excepción:  
  
- La clase que se está serializando no tiene un constructor público sin parámetros.  
  
- Los datos del archivo no representan los datos de la clase que se va a deserializar.  
  
- El archivo no existe (<xref:System.IO.IOException>).  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  

 Compruebe siempre las entradas y nunca deserialice datos de un origen que no sea de confianza. El objeto que se ha vuelto a crear se ejecuta en un equipo local con los permisos del código que lo ha deserializado. Compruebe todas las entradas antes de utilizar los datos en la aplicación.  
  
## <a name="see-also"></a>Vea también

- <xref:System.IO.StreamWriter>
- [How to: Write Object Data to an XML File (Visual Basic)](how-to-write-object-data-to-an-xml-file.md) (Escritura de datos de objetos en un archivo XML [Visual Basic])
- [Serialización (Visual Basic)](index.md)
- [Guía de programación en Visual Basic](../../index.md)
