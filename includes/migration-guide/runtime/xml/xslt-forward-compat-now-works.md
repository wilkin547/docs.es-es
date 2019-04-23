---
ms.openlocfilehash: 2dd97fcce13ed1ac7baf4cd02f5881d31d7a9c4b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59805043"
---
### <a name="xslt-forward-compat-now-works"></a>Ya funciona la compatibilidad con versiones posteriores de XSLT

|   |   |
|---|---|
|Detalles|En .NET Framework 4, la compatibilidad con versiones posteriores de XSLT 1.0 presentaba los problemas siguientes:<ul><li>La carga de una hoja de estilos no se realizaba correctamente si su versión estaba establecida en 2.0 y el analizador encontraba una construcción de XSLT 1.0 desconocida.</li><li>La construcción <code>xsl:sort</code> no podía ordenar los datos si la versión de la hoja de estilos estaba establecida en 1.1.</li></ul>En .NET Framework 4.5, se han corregido estos problemas y el modo de compatibilidad con versiones posteriores de XSLT 1.0 funciona correctamente.|
|Sugerencia|La mayoría de las aplicaciones no deberían verse afectadas, pero en algunos casos los datos se ordenarán de otra forma ahora que se respeta xsl:sort. Si se usa <code>xsl:sort</code> en hojas de estilo de la versión 1.1, confirme que las aplicaciones no dependían del orden de los datos sin ordenar. Si las aplicaciones se basan en el comportamiento de ordenación de la versión 4.0, quite <code>xsl:sort</code> de la hoja de estilos.|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Xml.Xsl.XslCompiledTransform?displayProperty=nameWithType></li></ul>|
