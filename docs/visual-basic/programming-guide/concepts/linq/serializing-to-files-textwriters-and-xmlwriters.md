---
title: Serializar en archivos, escritores de texto y XmlWriters3
ms.date: 07/20/2015
ms.assetid: 7a0c24df-79ef-41a0-87f5-e6cf79382da9
ms.openlocfilehash: 63577d955da89fde0a2320b4cf84414ccbb69c84
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61786794"
---
# <a name="serializing-to-files-textwriters-and-xmlwriters"></a>Serializar en archivos, escritores de texto y escritores XML

Puede serializar árboles XML en <xref:System.IO.File>, <xref:System.IO.TextWriter> o <xref:System.Xml.XmlWriter>.

Puede serializar cualquier componente XML, entre los que se incluyen <xref:System.Xml.Linq.XDocument> y <xref:System.Xml.Linq.XElement>, en una cadena con el método `ToString`.

Si desea suprimir el formato al serializar en una cadena, puede usar el método <xref:System.Xml.Linq.XNode.ToString%2A?displayProperty=nameWithType>.

El comportamiento predeterminado al serializar en un archivo consiste en formatear el documento XML resultante (aplicarle una sangría). Cuando aplica una sangría, en el árbol XML no se conservan los espacios en blanco más insignificantes. Para serializar con formato, use una de las sobrecargas de los métodos siguientes que no toman <xref:System.Xml.Linq.SaveOptions> como argumento:

- <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>

- <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>

Si desea que la opción no aplique una sangría y conserve los espacios en blanco más insignificantes del árbol XML, use una de las sobrecargas de los métodos siguientes que toman <xref:System.Xml.Linq.SaveOptions> como argumento:

- <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>

- <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType>

Por obtener ejemplos, vea el tema de referencia correspondiente.

## <a name="see-also"></a>Vea también

- [Serializar árboles XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
