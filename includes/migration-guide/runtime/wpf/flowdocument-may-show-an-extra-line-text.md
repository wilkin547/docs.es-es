---
ms.openlocfilehash: 0470cefc05fb5da6a6195ee0a96f04feef01fd10
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620689"
---
### <a name="flowdocument-may-show-an-extra-line-of-text"></a>FlowDocument puede mostrar una línea de texto adicional

#### <a name="details"></a>Detalles

En algunos casos, un elemento <xref:System.Windows.Documents.FlowDocument> mostrará una línea de texto adicional cuando se ejecuta en .NET Framework 4.5 en comparación a cómo se mostraba cuando se ejecutaba en .NET Framework 4.0. No hay casos conocidos de que el cambio provoque que un texto se muestre de forma incorrecta o ilegible, pero podría dar la impresión de que el texto se omitió anteriormente de la vista de un <xref:System.Windows.Documents.FlowDocument>.

#### <a name="suggestion"></a>Sugerencia

En algunos casos, reducir la propiedad PageHeight del elemento de visualización en uno puede restaurar el número anterior de líneas mostradas.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Windows.Documents.FlowDocument.%23ctor></li><li><xref:System.Windows.Documents.FlowDocument.%23ctor(System.Windows.Documents.Block)></li><li><xref:System.Windows.Controls.FlowDocumentReader.%23ctor></li><li><xref:System.Windows.Controls.FlowDocumentPageViewer.%23ctor></li><li><xref:System.Windows.Controls.Primitives.DocumentPageView.%23ctor></li></ul>|
