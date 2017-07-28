---
title: "Cómo: Leer y escribir un documento codificado (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 84f64e71-39a6-42c6-ad68-f052bb158a03
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: fc7c21c1aa6f4035bfaee509c7bc542542635313
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-read-and-write-an-encoded-document-c"></a>Cómo: Leer y escribir un documento codificado (C#)
Para crear un documento XML codificado, se agrega un <xref:System.Xml.Linq.XDeclaration> al árbol XML, estableciendo la codificación en el nombre de página de códigos deseado.  
  
 Los valores devueltos por <xref:System.Text.Encoding.WebName%2A> son valores válidos.  
  
 Si lee un documento codificado, la propiedad <xref:System.Xml.Linq.XDeclaration.Encoding%2A> estará establecida en el nombre de la página de códigos.  
  
 Si establece <xref:System.Xml.Linq.XDeclaration.Encoding%2A> en un nombre de página de códigos válido, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] se serializará con la codificación especificada.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crean dos documentos, uno con codificación utf-8 y otro con codificación utf-16. A continuación se cargan los documentos y se imprime la codificación en la consola.  
  
```csharp  
Console.WriteLine("Creating a document with utf-8 encoding");  
XDocument encodedDoc8 = new XDocument(  
    new XDeclaration("1.0", "utf-8", "yes"),  
    new XElement("Root", "Content")  
);  
encodedDoc8.Save("EncodedUtf8.xml");  
Console.WriteLine("Encoding is:{0}", encodedDoc8.Declaration.Encoding);  
Console.WriteLine();  
  
Console.WriteLine("Creating a document with utf-16 encoding");  
XDocument encodedDoc16 = new XDocument(  
    new XDeclaration("1.0", "utf-16", "yes"),  
    new XElement("Root", "Content")  
);  
encodedDoc16.Save("EncodedUtf16.xml");  
Console.WriteLine("Encoding is:{0}", encodedDoc16.Declaration.Encoding);  
Console.WriteLine();  
  
XDocument newDoc8 = XDocument.Load("EncodedUtf8.xml");  
Console.WriteLine("Encoded document:");  
Console.WriteLine(File.ReadAllText("EncodedUtf8.xml"));  
Console.WriteLine();  
Console.WriteLine("Encoding of loaded document is:{0}", newDoc8.Declaration.Encoding);  
Console.WriteLine();  
  
XDocument newDoc16 = XDocument.Load("EncodedUtf16.xml");  
Console.WriteLine("Encoded document:");  
Console.WriteLine(File.ReadAllText("EncodedUtf16.xml"));  
Console.WriteLine();  
Console.WriteLine("Encoding of loaded document is:{0}", newDoc16.Declaration.Encoding);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
Creating a document with utf-8 encoding  
Encoding is:utf-8  
  
Creating a document with utf-16 encoding  
Encoding is:utf-16  
  
Encoded document:  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<Root>Content</Root>  
  
Encoding of loaded document is:utf-8  
  
Encoded document:  
<?xml version="1.0" encoding="utf-16" standalone="yes"?>  
<Root>Content</Root>  
  
Encoding of loaded document is:utf-16  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml.Linq.XDeclaration.Encoding%2A?displayProperty=fullName>   
 [Programación avanzada de LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)

