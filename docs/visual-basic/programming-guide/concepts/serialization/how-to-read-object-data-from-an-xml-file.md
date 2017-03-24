---
title: "Cómo: leer datos de objetos de un archivo XML (Visual Basic) | Documentos de Microsoft"
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
ms.assetid: 1e1423bf-74a4-4dde-a3bb-ae1bfc0a68ed
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
ms.openlocfilehash: c448d79a88517925712f79ed061aa90933e3f6d1
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-read-object-data-from-an-xml-file-visual-basic"></a>Cómo: leer datos de objetos de un archivo XML (Visual Basic)
Este ejemplo lee datos de objetos escritos previamente a un archivo XML mediante la <xref:System.Xml.Serialization.XmlSerializer>clase.</xref:System.Xml.Serialization.XmlSerializer>  
  
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
 Reemplace el nombre de archivo "c:\temp\SerializationOverview.xml" por el nombre del archivo que contiene los datos serializados. Para obtener más información sobre la serialización de datos, consulte [Cómo: escribir datos de objeto en un archivo XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md).  
  
 La clase debe tener un constructor público sin parámetros.  
  
 Sólo las propiedades públicas y campos se deserializan.  
  
## <a name="robust-programming"></a>Programación sólida  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   La clase que se está serializando no tiene un constructor público sin parámetros.  
  
-   Los datos en el archivo no representan datos de la clase que se deserializará.  
  
-   El archivo no existe (<xref:System.IO.IOException>).</xref:System.IO.IOException>  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Compruebe siempre las entradas y nunca deserialice datos desde un origen de confianza. El objeto recreado se ejecuta en un equipo local con los permisos del código que lo deserializó. Compruebe todas las entradas antes de utilizar los datos en la aplicación.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IO.StreamWriter></xref:System.IO.StreamWriter>   
 [Cómo: escribir datos de objetos en un archivo XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)   
 [Serialización (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/index.md)   
 [Guía de programación de Visual Basic](../../../../visual-basic/programming-guide/index.md)
