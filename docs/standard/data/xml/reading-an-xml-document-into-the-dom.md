---
title: Lectura de un documento XML en el DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: a4fb291f-5630-49ba-a49a-5b66c3b71e49
ms.openlocfilehash: 02338d72f51d3a7507c0dfa030383399b9e213f6
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84282407"
---
# <a name="reading-an-xml-document-into-the-dom"></a>Lectura de un documento XML en el DOM
La información XML se lee en memoria desde diferentes formatos. Se puede leer desde una cadena, una secuencia, una URL, un sistema de lectura de texto o una clase derivada de <xref:System.Xml.XmlReader>.  
  
 El método <xref:System.Xml.XmlDocument.Load%2A> pone el documento en memoria y dispone de métodos sobrecargados para tomar datos de cada uno de los diferentes formatos. También hay un método <xref:System.Xml.XmlDocument.LoadXml%2A> que lee XML de una cadena.  
  
 Los diferentes métodos <xref:System.Xml.XmlDocument.Load%2A> influyen en qué nodos se crean cuando se carga el Modelo de objetos de documento (DOM). En la siguiente tabla se enumeran las diferencias entre algunos de los métodos <xref:System.Xml.XmlDocument.Load%2A> y los temas en los que se tratan.  
  
|Contenido|Tema|  
|-------------|-----------|  
|Creación de nodos de espacios en blanco|El objeto utilizado para cargar el DOM tiene un efecto en los nodos de espacios en blanco y espacios en blanco significativos que se generan en el DOM. Para obtener más información, vea [Control de espacios en blanco y de espacios en blanco significativos al cargar DOM](white-space-and-significant-white-space-handling-when-loading-the-dom.md).|  
|Carga de XML comenzando en un nodo específico o carga de todo el documento XML|Si se utiliza el método <xref:System.Xml.XmlDocument.Load%2A?displayProperty=nameWithType>, los datos se pueden cargar desde un nodo específico en el DOM. Para obtener más información, vea [Carga de datos desde un sistema de lectura](load-data-from-a-reader.md).|  
|Validación de XML a medida que se carga|Los datos XML cargados en el DOM se pueden validar a medida que se cargan. Para ello, se utiliza un <xref:System.Xml.XmlReader> de validación. Para obtener más información sobre la validación de documentos XML a medida que se cargan, vea [Validación de un documento XML en el DOM](validating-an-xml-document-in-the-dom.md).|  
  
 En los siguientes ejemplos se muestra cómo se carga el XML con el método <xref:System.Xml.XmlDocument.LoadXml%2A> y cómo se guardan posteriormente los datos en un archivo de texto denominado `data.xml`.  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
Public Class Sample  
  
    Public Shared Sub Main()  
        ' Create the XmlDocument.  
        Dim doc As New XmlDocument()  
        doc.LoadXml(("<book genre='novel' ISBN='1-861001-57-5'>" & _  
                    "<title>Pride And Prejudice</title>" & _  
                    "</book>"))  
        ' Save the document to a file.  
        doc.Save("data.xml")  
    End Sub 'Main  
End Class 'Sample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
public class Sample  
{  
    public static void Main()  
    {  
        // Create the XmlDocument.  
        XmlDocument doc = new XmlDocument();  
        doc.LoadXml("<book genre='novel' ISBN='1-861001-57-5'>" +  
                    "<title>Pride And Prejudice</title>" +  
                    "</book>");  
  
        // Save the document to a file.  
        doc.Save("data.xml");  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también

- [Document Object Model (DOM) para XML](xml-document-object-model-dom.md)
