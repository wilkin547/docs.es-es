---
ms.openlocfilehash: fdec6671cbf2dae0d72dfaec07f162058b38cf9d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620728"
---
### <a name="xmltextreader-dtd-entity-expansion-is-limited-to-10000000-characters"></a>La expansión de entidades DTD de XmlTextReader está limitada a 10 000 000 caracteres

#### <a name="details"></a>Detalles

La expansión de entidades DTD ahora está limitada a 10 000 000 caracteres. La carga de archivos XML sin expansión de entidades DTD o con expansión de entidades DTD limitada no se verá afectada. Los archivos con entidades de DTD que se expanden a más de 10.000.000 caracteres no se podrán cargar y ahora iniciarán una excepción.

#### <a name="suggestion"></a>Sugerencia

Si el límite de expansión de entidades DTD de 10 000 000 es demasiado bajo, el valor se puede anular con la propiedad <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities>. Se puede pasar un <xref:System.Xml.XmlReaderSettings?displayProperty=fullName> con el valor <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=fullName> adecuado a <code>XmlReader.Create</code> que toma <xref:System.Xml.XmlReaderSettings?displayProperty=fullName> (por ejemplo, <xref:System.Xml.XmlReader.Create(System.String,System.Xml.XmlReaderSettings)>).

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Xml.XmlTextReader?displayProperty=nameWithType></li><li><xref:System.Xml.XmlTextReader.%23ctor></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream,System.Xml.XmlNameTable)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream,System.Xml.XmlNodeType,System.Xml.XmlParserContext)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.TextReader)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.IO.TextReader,System.Xml.XmlNameTable)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.Stream)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.Stream,System.Xml.XmlNameTable)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.TextReader)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.TextReader,System.Xml.XmlNameTable)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.Xml.XmlNameTable)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.String,System.Xml.XmlNodeType,System.Xml.XmlParserContext)></li><li><xref:System.Xml.XmlTextReader.%23ctor(System.Xml.XmlNameTable)></li></ul>|
