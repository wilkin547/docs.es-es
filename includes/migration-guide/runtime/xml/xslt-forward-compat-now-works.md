---
ms.openlocfilehash: 8c8477ae3719cfcc2060459ba85bcc9e76f11c41
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497316"
---
### <a name="xslt-forward-compat-now-works"></a>Ya funciona la compatibilidad con versiones posteriores de XSLT

#### <a name="details"></a>Detalles

En .NET Framework 4, la compatibilidad con versiones posteriores de XSLT 1.0 presentaba los problemas siguientes:<ul><li>La carga de una hoja de estilos no se realizaba correctamente si su versión estaba establecida en 2.0 y el analizador encontraba una construcción de XSLT 1.0 desconocida.</li><li>La construcción <code>xsl:sort</code> no podía ordenar los datos si la versión de la hoja de estilos estaba establecida en 1.1.</li></ul>En .NET Framework 4.5, se han corregido estos problemas y el modo de compatibilidad con versiones posteriores de XSLT 1.0 funciona correctamente.

#### <a name="suggestion"></a>Sugerencia

La mayoría de las aplicaciones no deberían verse afectadas, pero en algunos casos los datos se ordenarán de otra forma ahora que se respeta xsl:sort. Si se usa <code>xsl:sort</code> en hojas de estilo de la versión 1.1, confirme que las aplicaciones no dependían del orden de los datos sin ordenar. Si las aplicaciones se basan en el comportamiento de ordenación de la versión 4.0, quite <code>xsl:sort</code> de la hoja de estilos.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Xml.Xsl.XslCompiledTransform?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Xml.Xsl.XslCompiledTransform`

-->
