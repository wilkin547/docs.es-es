---
title: "C&#243;mo: Calificar el elemento XML y los nombres del atributo XML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "calificar elementos XML"
  - "calificar nombres XML"
  - "espacios de nombres XML, calificar elementos y nombres en"
ms.assetid: 44719f90-7e15-42e8-a9e2-282287e2b5bf
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# C&#243;mo: Calificar el elemento XML y los nombres del atributo XML
[Ejemplo de código](#cpconworkingwithxmlnamespacesanchor1)  
  
 Los espacios de nombres XML contenidos por instancias de la clase [XmlSerializerNamespaces](frlrfSystemXmlSerializationXmlSerializerNamespacesClassTopic) deben ser conformes a la especificación de World Wide Web Consortium \(www.w3.org\) denominada "Espacios de nombres en XML".  
  
 Los espacios de nombres XML proporcionan una método para calificar los nombres de elementos y atributos XML en documentos XML.Un nombre calificado se compone de un prefijo y un nombre local, separados por dos puntos.El prefijo funciona únicamente como marcador de posición y está asignado a un identificador URI que especifica un espacio de nombres.La combinación del espacio de nombres del URI, universalmente administrado, y el nombre local genera un nombre del que se garantiza que es universalmente único.  
  
 Creando una instancia de **XmlSerializerNamespaces** y agregando los pares de espacio de nombres al objeto, puede especificar los prefijos utilizados en un documento XML.  
  
### Para crear nombres calificados en un documento XML  
  
1.  Cree una instancia de la clase **XmlSerializerNamespaces**.  
  
2.  Agregue todos los prefijos y pares de espacio de nombres a **XmlSerializerNamespaces**.  
  
3.  Aplique el atributo apropiado **System.Xml.Serialization** a cada método o clase que [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx) vaya a serializar en un documento XML.  
  
     Los atributos disponibles son: [XmlAnyElementAttribute](frlrfSystemXmlSerializationXmlAnyElementAttributeClassTopic), [XmlArrayAttribute](frlrfSystemXmlSerializationXmlArrayAttributeClassTopic), [XmlArrayItemAttribute](frlrfSystemXmlSerializationXmlArrayItemAttributeClassTopic), [XmlAttributeAttribute](frlrfSystemXmlSerializationXmlAttributeAttributeClassTopic), [XmlElementAttribute](frlrfSystemXmlSerializationXmlElementAttributeClassTopic), [XmlRootAttribute](frlrfSystemXmlSerializationXmlRootAttributeClassTopic), y [XmlTypeAttribute](frlrfSystemXmlSerializationXmlTypeAttributeClassTopic).  
  
4.  Establezca la propiedad **Namespace** de cada atributo en uno de los valores de espacio de nombres del **XmlSerializerNamespaces**.  
  
5.  Pase **XmlSerializerNamespaces** al método **Serialize** de **XmlSerializer**.  
  
## Ejemplo  
 En el siguiente ejemplo, se crea un **XmlSerializerNamespaces** al que se agregan dos prefijos y pares de espacio de nombres al objeto.El código crea **XmlSerializer** que se utiliza para serializar una instancia de la clase `Books`.El código llama al método **Serialize** con **XmlSerializerNamespaces**, permitiéndole al XML contener los espacios de nombres prefijados.  
  
```vb  
Option Explicit   
public class Price  
{  
    [XmlAttribute(Namespace = "http://www.cpandl.com")]  
    public string currency;  
    [XmlElement(Namespace = "http://www.cohowinery.com")]  
    public decimal price;  
}  
  
Option Strict  
  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.Serialization  
  
Public Class Run  
  
    Public Shared Sub Main()  
        Dim test As New Run()  
        test.SerializeObject("XmlNamespaces.xml")  
    End Sub 'Main  
  
    Public Sub SerializeObject(filename As String)  
        Dim mySerializer As New XmlSerializer(GetType(Books))  
        ' Writing a file requires a TextWriter.  
        Dim myWriter As New StreamWriter(filename)  
  
        ' Creates an XmlSerializerNamespaces and adds two  
        ' prefix-namespace pairs.   
        Dim myNamespaces As New XmlSerializerNamespaces()  
        myNamespaces.Add("books", "http://www.cpandl.com")  
        myNamespaces.Add("money", "http://www.cohowinery.com")  
  
        ' Creates a Book.  
        Dim myBook As New Book()  
        myBook.TITLE = "A Book Title"  
        Dim myPrice As New Price()  
        myPrice.price = CDec(9.95)  
        myPrice.currency = "US Dollar"  
        myBook.PRICE = myPrice  
        Dim myBooks As New Books()  
        myBooks.Book = myBook  
        mySerializer.Serialize(myWriter, myBooks, myNamespaces)  
        myWriter.Close()  
    End Sub  
End Class  
  
Public Class Books  
    <XmlElement([Namespace] := "http://www.cohowinery.com")> _  
    Public Book As Book  
End Class 'Books  
  
<XmlType([Namespace] := "http://www.cpandl.com")> _  
Public Class Book  
  
    <XmlElement([Namespace] := "http://www.cpandl.com")> _  
    Public TITLE As String  
    <XmlElement([Namespace] := "http://www.cohowinery.com")> _  
    Public PRICE As Price  
End Class  
  
Public Class Price  
    <XmlAttribute([Namespace] := "http://www.cpandl.com")> _  
    Public currency As String  
    Public <XmlElement([Namespace] := "http://www.cohowinery.com")> _  
        price As Decimal  
End Class  
  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.Serialization;  
  
public class Run  
{  
    public static void Main()  
    {  
        Run test = new Run();  
        test.SerializeObject("XmlNamespaces.xml");  
    }  
    public void SerializeObject(string filename)  
    {  
        XmlSerializer mySerializer = new XmlSerializer(typeof(Books));  
        // Writing a file requires a TextWriter.  
        TextWriter myWriter = new StreamWriter(filename);  
  
        // Creates an XmlSerializerNamespaces and adds two  
        // prefix-namespace pairs.  
        XmlSerializerNamespaces myNamespaces =   
        new XmlSerializerNamespaces();  
        myNamespaces.Add("books", "http://www.cpandl.com");  
        myNamespaces.Add("money", "http://www.cohowinery.com");  
  
        // Creates a Book.  
        Book myBook = new Book();  
        myBook.TITLE = "A Book Title";  
        Price myPrice = new Price();  
        myPrice.price = (decimal) 9.95;  
        myPrice.currency = "US Dollar";  
        myBook.PRICE = myPrice;  
        Books myBooks = new Books();  
        myBooks.Book = myBook;  
        mySerializer.Serialize(myWriter,myBooks,myNamespaces);  
        myWriter.Close();  
    }  
}  
  
public class Books  
{  
    [XmlElement(Namespace = "http://www.cohowinery.com")]  
    public Book Book;  
}  
  
[XmlType(Namespace ="http://www.cpandl.com")]  
public class Book  
{  
    [XmlElement(Namespace = "http://www.cpandl.com")]  
    public string TITLE;  
    [XmlElement(Namespace ="http://www.cohowinery.com")]  
    public Price PRICE;  
}  
```  
  
## Vea también  
 [Herramienta de definición de esquema XML y serialización XML](../../../docs/framework/serialization/the-xml-schema-definition-tool-and-xml-serialization.md)   
 [Introducir la serialización XML](../../../docs/framework/serialization/introducing-xml-serialization.md)   
 [XmlSerializer Class](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx)   
 [Atributos que controlan la serialización XML](../../../docs/framework/serialization/attributes-that-control-xml-serialization.md)   
 [XmlSerializerNamespaces Class](frlrfSystemXmlSerializationXmlSerializerNamespacesClassTopic)   
 [Cómo: Especificar un nombre de elemento alternativo para una secuencia XML](../../../docs/framework/serialization/how-to-specify-an-alternate-element-name-for-an-xml-stream.md)   
 [Cómo: Serializar un objeto](../../../docs/framework/serialization/how-to-serialize-an-object.md)   
 [Cómo: Deserializar un objeto](../../../docs/framework/serialization/how-to-deserialize-an-object.md)