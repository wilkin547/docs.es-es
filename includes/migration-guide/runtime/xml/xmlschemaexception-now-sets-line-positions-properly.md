---
ms.openlocfilehash: a5b3e325c13d2f56532ebc6ebb5c259d565a4952
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235937"
---
### <a name="xmlschemaexception-now-sets-line-positions-properly"></a>XmlSchemaException ahora establece correctamente las posiciones de las líneas

|   |   |
|---|---|
|Detalles|Si el valor de <xref:System.Xml.Linq.LoadOptions.SetLineInfo> se pasa al método Load y se produce un error de validación, las propiedades <xref:System.Xml.Schema.XmlSchemaException.LineNumber> y <xref:System.Xml.Schema.XmlSchemaException.LinePosition> contendrán ahora la información de línea.|
|Sugerencia|Se debe actualizar el código de control de excepciones que suponga que <xref:System.Xml.Schema.XmlSchemaException.LineNumber> y <xref:System.Xml.Schema.XmlSchemaException.LinePosition> no se van a establecer, ya que ahora estas propiedades se establecerán correctamente al usar SetLineInfo durante la carga de XML.|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Xml.Linq.LoadOptions.SetLineInfo?displayProperty=nameWithType></li></ul>|
