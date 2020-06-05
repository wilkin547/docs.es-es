---
title: Procedimiento para leer y escribir un documento codificado
ms.date: 07/20/2015
ms.assetid: 159d868f-5ac8-40f2-95ca-07dd925f35c6
ms.openlocfilehash: f66737429950e04f447dfbd58cf47b6434a22976
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397913"
---
# <a name="how-to-read-and-write-an-encoded-document-visual-basic"></a>Cómo: leer y escribir un documento codificado (Visual Basic)

Para crear un documento XML codificado, se agrega un <xref:System.Xml.Linq.XDeclaration> al árbol XML, estableciendo la codificación en el nombre de página de códigos deseado.

Los valores devueltos por <xref:System.Text.Encoding.WebName%2A> son valores válidos.

Si lee un documento codificado, la propiedad <xref:System.Xml.Linq.XDeclaration.Encoding%2A> estará establecida en el nombre de la página de códigos.

Si establece <xref:System.Xml.Linq.XDeclaration.Encoding%2A> en un nombre de página de códigos válido, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] se serializará con la codificación especificada.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se crean dos documentos, uno con codificación utf-8 y otro con codificación utf-16. A continuación se cargan los documentos y se imprime la codificación en la consola.

```vb
Console.WriteLine("Creating a document with utf-8 encoding")
Dim encodedDoc8 As XDocument = _
        <?xml version='1.0' encoding='utf-8' standalone='yes'?>
        <Root>Content</Root>

encodedDoc8.Save("EncodedUtf8.xml")
Console.WriteLine("Encoding is:{0}", encodedDoc8.Declaration.Encoding)
Console.WriteLine()

Console.WriteLine("Creating a document with utf-16 encoding")
Dim encodedDoc16 As XDocument = _
        <?xml version='1.0' encoding='utf-16' standalone='yes'?>
        <Root>Content</Root>

encodedDoc16.Save("EncodedUtf16.xml")
Console.WriteLine("Encoding is:{0}", encodedDoc16.Declaration.Encoding)
Console.WriteLine()

Dim newDoc8 As XDocument = XDocument.Load("EncodedUtf8.xml")
Console.WriteLine("Encoded document:")
Console.WriteLine(File.ReadAllText("EncodedUtf8.xml"))
Console.WriteLine()
Console.WriteLine("Encoding of loaded document is:{0}", newDoc8.Declaration.Encoding)
Console.WriteLine()

Dim newDoc16 As XDocument = XDocument.Load("EncodedUtf16.xml")
Console.WriteLine("Encoded document:")
Console.WriteLine(File.ReadAllText("EncodedUtf16.xml"))
Console.WriteLine()
Console.WriteLine("Encoding of loaded document is:{0}", newDoc16.Declaration.Encoding)
```

Este ejemplo produce el siguiente resultado:

```console
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

- <xref:System.Xml.Linq.XDeclaration.Encoding%2A?displayProperty=nameWithType>
- [Programación de LINQ to XML avanzada (Visual Basic)](advanced-linq-to-xml-programming.md)
