---
title: Serializar en archivos, escritores de texto y escritores XML
ms.date: 07/20/2015
ms.assetid: bd3ea6f7-895b-4ff4-a625-fe2bb55b1886
ms.openlocfilehash: 20cb84a9f79ca8de3e86a996f18c388dc53340ae
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "68868857"
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

- [Serializar árboles XML (C#)](serializing-to-files-textwriters-and-xmlwriters.md)
