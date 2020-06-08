---
title: Procedimiento para leer datos de objeto de un archivo XML (C#)
ms.date: 07/20/2015
ms.assetid: 6ad60d96-a4d9-48e6-a8b0-d7f6f803cafa
ms.openlocfilehash: e2365d1260d3f6e239f294b2af3399c2fb659575
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241882"
---
# <a name="how-to-read-object-data-from-an-xml-file-c"></a>Procedimiento para leer datos de objeto de un archivo XML (C#)
En este ejemplo se leen los datos de objetos que se han escrito anteriormente en un archivo XML con la clase <xref:System.Xml.Serialization.XmlSerializer>.  
  
## <a name="example"></a>Ejemplo  
  
```csharp  
public class Book  
{  
    public String title;  
}
  
public void ReadXML()  
{  
    // First write something so that there is something to read ...  
    var b = new Book { title = "Serialization Overview" };  
    var writer = new System.Xml.Serialization.XmlSerializer(typeof(Book));  
    var wfile = new System.IO.StreamWriter(@"c:\temp\SerializationOverview.xml");  
    writer.Serialize(wfile, b);  
    wfile.Close();  
  
    // Now we can read the serialized book ...  
    System.Xml.Serialization.XmlSerializer reader =
        new System.Xml.Serialization.XmlSerializer(typeof(Book));  
    System.IO.StreamReader file = new System.IO.StreamReader(  
        @"c:\temp\SerializationOverview.xml");  
    Book overview =  (Book)reader.Deserialize(file);  
    file.Close();  
  
    Console.WriteLine(overview.title);  
  
}  
```  
  
## <a name="compiling-the-code"></a>Compilar el código  
Reemplace el nombre de archivo "c:\temp\SerializationOverview.xml" por el nombre del archivo que contiene los datos serializados. Para más información sobre la serialización de datos, consulte [Procedimiento para escribir datos de objeto en un archivo XML (C#)](./how-to-write-object-data-to-an-xml-file.md).
  
 La clase debe tener un constructor público sin parámetros.  
  
 Solo se deserializan las propiedades y los campos públicos.  
  
## <a name="robust-programming"></a>Programación sólida  
 Las condiciones siguientes pueden provocar una excepción:  
  
- La clase que se está serializando no tiene un constructor público sin parámetros.  
  
- Los datos del archivo no representan los datos de la clase que se va a deserializar.  
  
- El archivo no existe (<xref:System.IO.IOException>).  
  
## <a name="net-security"></a>Seguridad de .NET  
 Compruebe siempre las entradas y nunca deserialice datos de un origen que no sea de confianza. El objeto que se ha vuelto a crear se ejecuta en un equipo local con los permisos del código que lo ha deserializado. Compruebe todas las entradas antes de utilizar los datos en la aplicación.  
  
## <a name="see-also"></a>Vea también

- <xref:System.IO.StreamWriter>
- [Procedimiento para escribir datos de objeto en un archivo XML (C#)](./how-to-write-object-data-to-an-xml-file.md)
- [Serialización (C#)](./index.md)
- [Guía de programación de C#](../../index.md)
