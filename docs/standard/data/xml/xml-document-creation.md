---
title: Creación de documentos XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 877e9c62-b082-4bfb-bc5b-f47297eb30ef
ms.openlocfilehash: a12555a02b45a964ff7efcbe00e0d2cb8637474a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709990"
---
# <a name="xml-document-creation"></a>Creación de documentos XML
Hay dos formas de crear un documento XML. Una es crear una clase **XmlDocument** sin parámetros. La otra es crear una clase **XmlDocument** y pasarle una clase XmlNameTable como parámetro. En el ejemplo siguiente se muestra cómo crear una clase **XmlDocument** vacía sin utilizar parámetros.  
  
```vb  
Dim doc As New XmlDocument()  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
```  
  
 Una vez creado un documento, se pueden cargar datos desde una cadena, secuencia, dirección URL, sistema de lectura de texto o una clase derivada de **XmlReader** mediante el método **Load**. Existe también otro método de carga, el método **LoadXML**, que lee XML a partir de una cadena. Para obtener más información acerca de los diversos métodos **Load**, vea [Lectura de un documento XML en el DOM](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md).  
  
 Hay una clase denominada **XmlNameTable**. Esta clase es una tabla de objetos de cadena divididos en átomos. La tabla proporciona un medio eficaz para que el analizador XML utilice el mismo objeto de cadena para todos los nombres de elemento y atributo repetidos en un documento XML. Al crear un documento, se crea un objeto **XmlNameTable** automáticamente, como se muestra a continuación, y al cargar el documento se cargan los nombres de elemento y atributo. Si dispone ya de un documento con una tabla de nombres y dichos nombres serían útiles en otro documento, puede crear un documento nuevo mediante el método **Load**, que acepta una clase **XmlNameTable** como parámetro. Al crear el documento con este método, utiliza la clase **XmlNameTable** existente con todos los atributos y elementos ya cargados desde el otro documento. Se puede utilizar para comparar de forma eficaz nombres de elemento y atributo. Para obtener más información acerca de **XmlNameTable**, vea [Comparación de objetos mediante XmlNameTable](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md). Como referencia, vea <xref:System.Xml.XmlNameTable>.  
  
## <a name="see-also"></a>Vea también

- [Document Object Model (DOM) para XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
