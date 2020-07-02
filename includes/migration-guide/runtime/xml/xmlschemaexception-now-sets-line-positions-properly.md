---
ms.openlocfilehash: c3e39e49747be709977d7fba3c39b59f5575c40d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620725"
---
### <a name="xmlschemaexception-now-sets-line-positions-properly"></a>XmlSchemaException ahora establece correctamente las posiciones de las líneas

#### <a name="details"></a>Detalles

Si el valor de <xref:System.Xml.Linq.LoadOptions.SetLineInfo> se pasa al método Load y se produce un error de validación, las propiedades <xref:System.Xml.Schema.XmlSchemaException.LineNumber> y <xref:System.Xml.Schema.XmlSchemaException.LinePosition> contendrán ahora la información de línea.

#### <a name="suggestion"></a>Sugerencia

Se debe actualizar el código de control de excepciones que suponga que <xref:System.Xml.Schema.XmlSchemaException.LineNumber> y <xref:System.Xml.Schema.XmlSchemaException.LinePosition> no se van a establecer, ya que ahora estas propiedades se establecerán correctamente al usar SetLineInfo durante la carga de XML.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Xml.Linq.LoadOptions.SetLineInfo?displayProperty=nameWithType></li></ul>|
